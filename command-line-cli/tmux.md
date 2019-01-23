# Tmux

## Copy Mode \(scrolling & coping terminal output\)

```bash
# Prefix = Ctrl key (by Default)
Prefix [

# You may change the keybinding to customize
# how you access Copy Mode

# My .tmux.conf file
    set -g prefix C-a # Set mode key to Control+a
    bind C-a send-prefix 

# How to Enter Copy Text Mode 
# to Scroll Terminal & Copy and Paste Terminal Output 

# Step 1 - Activate Copy Mode
    Ctrl + a [ 
# Step 2 - Highlight Text
     Press Spacebar than highlight text ith the mouse  
# Step 3 - Copy text to paste buffer
    # My way
        Right Mouse Button + Copy
# Step 4 - Exit Copy Mode
    Crtl + c
# Step 5 - Paste Text in Terminal
    Ctrl + Shift + v
```

