# Tmux Commands

> Using [Noobs Termin](https://noobs-term.com/#/) .dotfiles. Love this setup!

## Prefix 

`ctrl + a`

## .tmux.conf file

```text
set -g prefix C-a # Set mode key to Control+a
bind C-a send-prefix 
```

## Open vertical pane

`ctrl + a + shift + %`

## Open horizontal pane

`ctrl + a + shift + "`

## Move to different pane

`ctrl + a + arrow key`

## Close pane

`ctrl + d or type: exit`

## Create new windows

`ctrl + a + c`

## Move to different window

`ctrl + a + number-of-window`

## Rename pane

`ctrl + a + ,`

## How to Enter Copy Text Mode

#### Step 1 - Activate Copy Mode

```text
Ctrl + a [ 
```

#### Step 2 - Highlight Text

```text
 Press Spacebar than highlight text ith the mouse  
```

#### Step 3 - Copy text to paste buffer

```text
# My way
    Right Mouse Button + Copy
```

#### Step 4 - Exit Copy Mode

```text
Crtl + c
```

#### Step 5 - Paste Text in Terminal

```text
Ctrl + Shift + v
```

