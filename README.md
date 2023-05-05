Download Link: https://assignmentchef.com/product/solved-csi2120-lab-11-list-processing-with-error-checking
<br>
Write a top-level define absDiff that calculates the absolute difference of the corresponding elements of two lists. The function also evaluates to a list. Check if the list have the same length otherwise return an error. You are given the auxiliary routine loop.

(define (loop LA LB)  (if (or (null? LA) (null? LB))      ‘()      (cons (abs (- (car LA) (car LB))) (loop (cdr LA) (cdr LB))))) ; Examples:;; (absDiff ‘(1 3 5 6) ‘(3 5 2 1));  =&gt;   (2 2 3 5);; (absDiff ‘(1 3 5 6 7) ‘(3 5 2 1)) ; =&gt; “List have different length”;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

<h3>Exercise 2: Advanced List Processing</h3>

Change the above top-level define and auxillary function such that it also works when the two input lists are not the same length by assuming that the missing elements in the shorter list have the value of 0. The result will be of length equal to the longer list.

; Example:;; (absDiffA ‘(1 3 5 6 2 5) ‘(3 5 2 1)); =&gt;    (2 2 3 5 2 5) ;; (absDiffA ‘(1 3 5 6) ‘(3 5 2 1 2 5)); =&gt;    (2 2 3 5 2 5) ;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

<h3>Exercise 3: Local Definitions</h3>

Change the definition of the following function min-list to not use any auxillary helper function. Hint: Use local definitions.

; Example:;; (min-list ‘(4 8 9 2 8)); =&gt; 2;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;(define (min-list x)  (if (null? x)      x      (min-list-aux (car x)(cdr x)))) (define (min-list-aux e l)  (cond   ((null? l) e)   ((&gt; e (car l))    (min-list-aux (car l)(cdr l)))   (else (min-list-aux e (cdr l)))))

<h3>Exercise 4 and Quiz: Let Bindings</h3>

<em>Please hand-in the answer to this question on Virtual Campus during your lab session but at the latest by Friday 6:00pm! Remember, your submission will only count if you have signed the lab attendance sheet.</em>

Fill the gaps in the following expression with the appropriate form of let.

; (____________ ((f (lambda (a b);       (_____________ ((b (* b b)));              (_____________ ((a (* a a)) (b (- b a)));                      (if (&lt; a b);                   (f b a));                   (list a b))))))) (f 1 2));; =&gt; ‘(9 -8);;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;