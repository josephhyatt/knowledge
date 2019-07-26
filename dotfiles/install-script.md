# Install Script

1. Create a file called `install`
   1. `touch install`
2. Make the `install` file executable
   1. `chmod +x install`

```bash
#!/usr/bin/env bash

BASEDIR=$(dirname $0)
cd $BASEDIR

ln -s ${PWD}/bashrc ~/.bashrc 
ln -s ${PWD}/zshrc ~/.zshrc

```

