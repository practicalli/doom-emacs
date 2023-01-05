# Using Workspaces

Multiple workspaces are a convienient way to manage working with different projects.

++spc++ ++"l"++ is the workspace menu from practicalli/doom-emacs-config (++spc++ ++tab++ in Doom Emacs)

++spc++ ++"p"++ ++"p"++ and selecting a project will open the project within a workspace

++spc++ ++"l"++ ++"l"++ lists existing workflows

++spc++ ++"l"++ ++tab++ jumps to the last open workspace (use to toggle between two projects)

++spc++ ++"l"++ ++"d"++ displays existing workflows as tabs at the bottom of the frame


## Isolated buffer-list

++spc++ ++"b"++ ++"b"++ is workspace-restricted, showing open buffers only from the scope of the current workspace (projeect). 

++spc++ ++"b"++ ++b++ shows the global list of buffers, along with any typically hidden buffers, e.g. `*messages*` 


## Automatic workspaces

A workspace is automatically created (and switched to) when you:

- Create a new frame with `make-frame`
- Switch to a project using `projectile-switch-project`


## Session persistence

++spc++ ++"q"++ ++"s"++ to save the current session, including open workspaces and buffers, to , `~/.config/emacs/.local/etc/workspaces/autosave`. ++spc++ ++"q"++ ++"s"++ to choose a different file to save the session.

++spc++ ++"q"++ ++"L"++ (~+workspace/load-session~) to load a previous session

You can supply either a name to load a specific session to replace your current one.

### Workspace persistence

++spc++ ++"l"++ ++"s"++ (~+workspace/save~) to save the current workspace to a file.  If workspaces are already saved to file, a prompt appears to confirm keeping the other saved workspaces.

++spc++ ++"l"++ ++"l"++ (~+workspace/load~) to load workspaces from the persisted workspace file, `~/.config/emacs/.local/etc/workspaces/autosave`

++spc++ ++"l"++ ++"L"++ to load a workspace that was previously created in the current session but was not loaded automatically

## Commands

Default keybindings (defined in `/config/default/+evil-bindings.el`

| command                           | description                                                |
|-----------------------------------|------------------------------------------------------------|
| ~+workspace/new~                  | Create a new, blank workspace                              |
| ~+workspace/display~              | Display open workspaces in the mode-line                   |
| ~+workspace/load~                 | Load a saved workspace into the current session            |
| ~+workspace/restore-last-session~ | Restore last session                                       |
| ~+workspace/rename~               | Rename the current workspace                               |
| ~+workspace/save~                 | Save the current workspace to a file                       |
| ~+workspace/switch-to~            | Switch to an open workspace                                |
| ~+workspace/other~                | Switch to last workspace                                   |
| ~+workspace/switch-left~          | Switch to previous workspace                               |
| ~+workspace/switch-right~         | Switch to next workspace                                   |
| ~+workspace/delete~               | Delete the current workspace                               |
| ~+workspace/kill-session~         | Clears the current session (kills all windows and buffers) |
