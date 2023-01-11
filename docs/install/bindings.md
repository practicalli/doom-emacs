# Key Bindings

[practicalli/doom-emacs-config](https://github.com/practicalli/doom-emacs-config){target=_blank} replaces many of the default Doom key bindings as well as adding more key bindings

`map!` Doom macro is used to define new key bindings.  Existing Doom key bindings are replaced by first setting the binding to `nil` then adding a new definition.

Most Practicalli key bindings are defined in the `~/.config/doom/+bindings.el` configuration file, or in a major mode specific file e.g. `~/.config/doom/+clojure.el`


## Leader / Local leader

++spc++ is the leader key that opens the which-key menu, driving many of the menu based commands.

++comma++ replaces the Doom local leader, `SPC m` which is considered a major mode menu entry under the leader key so not really a shortcut to access the major mode context specific menu.

```emacs title=".config/doom/+bindings.el"
(setq doom-localleader-key ",")
```


## M-x Emacs command list

`SPC :` is probably a good key binding for those very familiar with Vim, as it alighs with the `:` character used to issue vim commands

`SPC SPC` is M-x in Spacemacs, so override the existing key binding that Doom defines to open a file, which is also provided by `SPC f f`


```emacs title=".config/doom/+bindings.el"
(map! :leader
      "SPC" nil
      :desc "M-x" "SPC" #'execute-extended-command)
```

> `SPC :` key binding is kept to allow for migration to the Doom key binding.


## Evil escape

`fd` is used for Evil Escape to provide an alternative to the ++esc++ key that keeps fingers on the home row of the keyboard

```emacs title=".config/doom/+bindings.el"
(after! evil-escape
  (setq evil-escape-key-sequence "fd"))
```


# Buffers

++spc++ ++tab++ switches to last open buffer, providing a convenient way to toggle between two buffers.

++spc++ ++"b"++ ++tab++ added to help discovery of this toggle approach

```emacs title=".config/doom/+bindings.el"
(map! :leader
         "TAB" nil
         :desc "Last Buffer" "TAB" #'evil-switch-to-windows-last-buffer)

(map! :leader
       (:prefix "b"
         :desc "Dashboard" "h" #'+doom-dashboard/open
         :desc "Toggle Last" "TAB" #'evil-switch-to-windows-last-buffer))
```

> Replaces Doom `SPC TAB` used for the workspaces menu, which is also replaced by `SPC l`


## Workspaces

++spc++ ++"l"++ replaces Doom `SPC TAB` to open the workspaces menu to align with Spacemacs (layout) approach. This frees `SPC TAB` to jump to the last open buffer, as in Spacemacs.


```emacs title=".config/doom/+bindings.el"
(map! :leader
       (:prefix-map ("TAB" . nil))
       (:prefix ("l". "Layouts")
         :desc "Last Layout" "<tab>" #'+workspace/other
         :desc "Display Tabs" "d" #'+workspace/display
         :desc "Delete layout" "D" #'+workspace/delete
         :desc "Layout list" "l" #'+workspace/switch-to
         :desc "Load Layout" "L" #'+workspace/load
         :desc "New Layout" "n" #'+workspace/new
         :desc "Rename Layout" "r" #'+workspace/rename
         :desc "Restore session" "R" #'+workspace/restore-last-session
         :desc "Save Layout" "s" #'+workspace/save
         :desc "Kill Session" "x" #'+workspace/kill-session
         :desc "Switch to 0" "0" #'+workspace/switch-to-0
         :desc "Switch to 1" "1" #'+workspace/switch-to-1
         :desc "Switch to 2" "2" #'+workspace/switch-to-2
         :desc "Switch to 3" "3" #'+workspace/switch-to-3
         :desc "Switch to 4" "4" #'+workspace/switch-to-4
         :desc "Switch to 5" "5" #'+workspace/switch-to-5
         :desc "Switch to 6" "6" #'+workspace/switch-to-6
         :desc "Switch to 7" "7" #'+workspace/switch-to-7
         :desc "Switch to 8" "8" #'+workspace/switch-to-8
         :desc "Switch to 9" "9" #'+workspace/switch-to-9))
```



## Treemacs

++spc++ ++"p"++ ++"t"++ toggles treemacs project browser from project menu

```emacs title=".config/doom/+bindings.el"
(map! :leader
      (:prefix "p"
         "t" nil  ; disable project todos key binding
         :desc "Project browser" "t" #'+treemacs/toggle))
```


## Version Control

++spc++ ++"g"++ ++"s"++ to call Magit Status, rather than the Doom binding to stage hunk at point

Practicalli always uses Magit status menu to manage changes, so adopting the Spacemacs binding.

```emacs title=".config/doom/+bindings.el"
(map! :leader
      (:prefix "g"
        :desc "" "s" nil  ; remove existing binding
        :desc "Magit Status" "s" #'magit-status))
```
