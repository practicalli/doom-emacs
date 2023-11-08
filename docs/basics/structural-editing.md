# Structural Editing with Smartparens


??? INFO "Smartparens enabled by default"
    Smartparens package is enabled by default in Doom emacs
    ```emacs title=".config/doom/init.el
    :config
    (default +bindings +smartparens)
    ```


## Key bindins

> TODO: documentation copied from Spacemacs to be reviewed


### Navigation

| Key binding | Description                                                             |
|-------------+-------------------------------------------------------------------------|
|             | Forward + Backward pairs                                                |
|-------------+-------------------------------------------------------------------------|
| ~SPC k j~   | go forward to next closing parenthesis                                  |
| ~SPC k k~   | go backward to previous opening parenthesis                             |
| ~SPC k l~   | go forward to next symbol                                               |
| ~SPC k h~   | go backward to previous symbol                                          |
| ~SPC k L~   | go forward to next sexp                                                 |
| ~SPC k H~   | go backward to previous sexp                                            |
| ~SPC k $~   | go forward to the end of current sexp                                   |
| ~SPC k 0~   | go backward to the beginning of current sexp                            |
|-------------+-------------------------------------------------------------------------|
|             | Other                                                                   |
|-------------+-------------------------------------------------------------------------|
| ~SPC k U~   | go "up": to parent sexp backward                                        |
| ~SPC k %~   | go to other paren of the same pair                                      |
| ~SPC k I~   | go back to beginning of current expression and switch to =insert= state |

### Manipulation:

| Key binding | Description                                                  |
|-------------+--------------------------------------------------------------|
| ~SPC k s~   | slurp forward: ~a (bs) c~ -> ~a (bs c)~                      |
| ~SPC k S~   | slurp backward: ~a (bs) c~ -> ~(a bs) c~                     |
| ~SPC k b~   | barf forward: ~(a bs c)~ -> ~(a bs) c~                       |
| ~SPC k B~   | barf backward: ~(a bs c)~ -> ~a (bs c)~                      |
| ~SPC k a~   | absorb: ~(a (bs <point> ..))~ -> ~((bs a <point> ..))~       |
| ~SPC k c~   | convolute: ~(as (bs <point> ..))~ -> ~(bs (as <point> ..))~  |
| ~SPC k t~   | transpose: ~(as <point> bs)~ -> ~(bs <point> as)~            |
| ~SPC k J~   | join: ~(as) <point> (bs)~ -> ~(as <point> bs)~               |
|-------------+--------------------------------------------------------------|
|             | Hybrid (= better for non-Lisp languages) commands            |
|-------------+--------------------------------------------------------------|
| ~SPC k ` s~ | hybrid slurp forward                                         |
| ~SPC k ` p~ | hybrid push: ~<point>as bs~ -> ~<point>bs as~                |
| ~SPC k ` t~ | hybrid transpose: ~as <point> bs~ -> ~bs <point> as~         |
|-------------+--------------------------------------------------------------|
| Note 1:     | ~xs~ is one or multiple sexp, ~x~ is a single sexp           |
| Note 2:     | point is at <point> when presented, or in the list otherwise |

### Insertion:

| Key binding | Description                    |
|-------------+--------------------------------|
| ~SPC k (~   | insert sexp before current one |
| ~SPC k )~   | insert sexp after current one  |
| ~SPC k w~   | wrap a symbol with parenthesis |

### Deletion:

| Key binding | Description                                                         |
|-------------+---------------------------------------------------------------------|
| ~SPC k ds~  | delete symbol                                                       |
| ~SPC k Ds~  | delete symbol backward                                              |
| ~SPC k dw~  | delete word                                                         |
| ~SPC k Dw~  | delete word backward                                                |
| ~SPC k dx~  | delete sexp: ~(as <point> a ..)~ -> ~(as <point> ..)~               |
| ~SPC k Dx~  | delete sexp backward: ~(as a <point> ..)~ -> ~(as <point> ..)~      |
| ~SPC k e~   | splice, killing forward: ~(as (bs <point> cs) ds)~ -> ~(as bs ds)~  |
| ~SPC k E~   | splice, killing backward: ~(as (bs <point> cs) ds)~ -> ~(as cs ds)~ |
| ~SPC k r~   | raise: ~(as <point> b ..)~ -> ~<point>b~                            |
| ~SPC k W~   | unwrap sexp: ~(as)~ -> ~as~                                         |
|-------------+---------------------------------------------------------------------|
|             | Hybrid (= better for non-Lisp languages) commands                   |
|-------------+---------------------------------------------------------------------|
| ~SPC k ` k~ | hybrid delete sexp                                                  |
|-------------+---------------------------------------------------------------------|
| Note 1:     | ~xs~ is one or multiple sexp, ~x~ is a single sexp                  |
| Note 2:     | point is at ~<point>~ when presented, or in the list otherwise      |
