# tmux.conf

```bash
# Reload tmux config
tmux source-file ~/.tmux.conf 
```

```bash
#
# Main Settings
#

set-option -g prefix C-a # Set mode key to Control + a
bind-key C-a send-prefix
setw -g mouse on
set-option -sg escape-time 10
set-option -g allow-rename off

#
# Custom Commands
#

# Moving Window
# ctrl + arrow
bind-key -n C-right next
bind-key -n C-left prev

# Reload Settings
bind r source-file ~/.tmux.conf \; display "Reloaded!"

#
# Plugins
#

# List of 0Plugins
set -g @tpm_plugins 'tmux-plugins/tpm' # tmux package manager
set -g @tpm_plugins 'tmux-plugins/tmux-sensible' # sensible settings everyone can agree on (hopefully)
set -g @tpm_plugins 'tmux-plugins/tmux-resurrect' # persist tmux environment across system restarts
set -g @tpm_plugins 'tmux-plugins/tmux-continuum' # continuous saving of tmux environment
set -g @tpm_plugins 'tmux-plugins/tmux-yank' # for copying to system clipboard
set -g @tpm_plugins 'tmux-plugins/tmux-prefix-highlight' # highlights when you press tmux prefix key

#
# Theme
#

set -g @tpm_plugins 'arcticicestudio/nord-tmux' # an arctic, north-bluish theme

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

