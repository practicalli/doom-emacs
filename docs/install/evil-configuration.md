# Evil configuration



## Map Evil keys

Key bindings to surround text with parens and other pairs

```emacs
(after! evil-surround
  (let ((pairs '((?g "$" . "$") 
                 (?h "(" . ")") 
                 (?j "[" . "]") 
                 (?k "{" . "}") 
                 (?l "<" . ">") 
                 (?ø "'" . "'") 
                 (?æ "\"" . "\""))))
    (prependq! evil-surround-pairs-alist pairs)
    (prependq! evil-embrace-evil-surround-keys (mapcar #'car pairs))))
```

