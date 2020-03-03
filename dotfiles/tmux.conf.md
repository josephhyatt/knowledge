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

# Moving Windows
# ctrl + arrow
bind-key -n C-right next
bind-key -n C-left prev

# switch panes using Alt-arrow without prefix
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

# Split Panes Using | and -
bind | split-window -h
bind - split-window -v
unbind '"'
unbind %

######################
### DESIGN CHANGES ###
######################

# loud or quiet?
set -g visual-activity off
set -g visual-bell off
set -g visual-silence off
setw -g monitor-activity off
set -g bell-action none

#  modes
setw -g clock-mode-colour colour5
setw -g mode-style 'fg=colour1 bg=colour18 bold'

# panes
set -g pane-border-style 'fg=colour19 bg=colour0'
set -g pane-active-border-style 'bg=colour0 fg=colour9'

# statusbar
set -g status-position bottom
set -g status-justify left
set -g status-style 'bg=colour18 fg=colour137 dim'
set -g status-left ''
set -g status-right '#[fg=colour233,bg=colour19] %d/%m #[fg=colour233,bg=colour8] %H:%M:%S '
set -g status-right-length 50
set -g status-left-length 20

setw -g window-status-current-style 'fg=colour1 bg=colour19 bold'
setw -g window-status-current-format ' #I#[fg=colour249]:#[fg=colour255]#W#[fg=colour249]#F '

setw -g window-status-style 'fg=colour9 bg=colour18'
setw -g window-status-format ' #I#[fg=colour237]:#[fg=colour250]#W#[fg=colour244]#F '

setw -g window-status-bell-style 'fg=colour255 bg=colour1 bold'

# messages
set -g message-style 'fg=colour232 bg=colour16 bold'

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

