#!/bin/bash or #!/usr/bin/zsh
which $SHELL
# variable
name="nameis"
echo $name

# debug
bash -x ./test.sh ( use "set -x" and "set +x" to indicate which areas to debug)