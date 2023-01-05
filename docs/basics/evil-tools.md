# Evil Editing tools 


* Multiedit - multiple match and replace
* Multiple cursors - add cursors and edit in paralell


## Multiedit




## Multiple cursors

Multiple cursors is most useful where the same changes are required in multiple lines, especially where those lines may be similar in structure but not idential. Changes are made to multiple lines or places in the text where the same editing opperation is desired.

++"g"++ ++"z"++ menu for mutliple cursor menu

When changes are vertically aligined, create multiple cursors with vim-style movements:

++2++ ++4++ ++"g"++ ++"z"++ ++i++ adds a cursor to the next 24 lines

Changes in more random positions benefit from creating 'frozen' cursors in any position that only take key input once switched to mirroring or activated by Evil Insert mode

++"g"++ ++"z"++ ++"z"++ toggle new (frozen) cursors at point. Frozen cursors stay in position until mirroring switched on or switching to insert mode

++"g"++ ++"z"++ ++"t"++ toggle mirroring on and off

With visual select:

++"g"++ ++"z"++ ++i++ to create curors at start of visual selection region

++"g"++ ++"z"++ ++a++ to create curors at end (append) of visual selection region

Remove multiple cursors:

++"g"++ ++"z"++ ++"q"++ to cancel all cursors



