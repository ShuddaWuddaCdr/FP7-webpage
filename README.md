# Lambda 


##Authors

* **Brian Carlson**
* **Joshua Caravetta**
* **Norman Mutunga**


##Overview

To provide the user with an Expressive Graphing Calculator that takes in regular infix expression and spits out the simplified solution to the Expression.


##Screenshot
(insert a screenshot here. You may opt to get rid of the title for it. You need at least one screenshot. Make it actually appear here, don't just add a link.)

Here's a demonstration of how to display an image that's uploaded to this repo:
![screenshot showing env diagram](withdraw.png)

##Concepts Demonstrated
Identify the OPL concepts demonstrated in your project. Be brief. A simple list and example is sufficient. 
* **Data abstraction** is used to provide access to Simplify,KeyWordDefinitions,Derivative,Keypair.
* The objects in the OpenGL world are represented with **recursive data structures.**
* **Symbolic language processing techniques** are used in the parser.

##External Technology and Libraries
Briefly describe the existing technology you utilized, and how you used it. Provide a link to that technology(ies).

##Favorite Lines of Code
####Mark (a team member)
Each team member should identify a favorite line of code, expression, or procedure written by them, and explain what it does. Why is it your favorite? What OPL philosophy does it embody?
Remember code looks something like this:
```scheme
(map (lambda (x) (foldr compose functions)) data)
```
####Norman 
This procedure reads in a regular expression packages it into a string hands it over to a parser procedure that handles the expression and hands back the solution to an output-field which the user can see or have it plotted on the canvas depending on the expression.
```
;(init-value "Expression")
      (callback (λ (input-field event)
            (cond
             ; If a user hits enter to compute an equation
            ((equal? (send event get-event-type) 'text-field-enter) 
             (begin
             ; Clear canvas
             (send pb erase)
             ; Set outputString to solved equation
             (set! outputString (main-parser (send input-field get-value)))
             ; Send outputString to output-field
            (send output-field set-value outputString))))))
```
####Brian Carlson
```
code
```
####Joshua Caravetta
```
code
```
####Lillian (another team member)
This expression reads in a regular expression and elegantly matches it against a pre-existing hashmap....
```scheme
(let* ((expr (convert-to-regexp (read-line my-in-port)))
             (matches (flatten
                       (hash-map *words*
                                 (lambda (key value)
                                   (if (regexp-match expr key) key '()))))))
  matches)
```

##Additional Remarks
Anything else you want to say in your report. Can rename or remove this section.

#How to Download and Run
You may want to link to your latest release for easy downloading by people (such as Mark).

Include what file to run, what to do with that file, how to interact with the app when its running, etc. 

