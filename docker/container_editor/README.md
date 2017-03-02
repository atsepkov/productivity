# Container Editor
Deploy this script into the VM running docker, after setting it up, you will be able to edit contents of any containers running on that machine from outside the container using vim running on the VM itself (the container does not need to have vim installed). This script will take care of all of the following:

- overwrite original file if you save your changes
- create a backup of original file in same directory as original (inside the container) with .bak suffix
- apply the same permissions to new file as the original
- change user ownership to the same user as the original
- discard changes if you quit vim without saving

Moreover, the bash_completion script will allow the following additional features:

- complete container name as first argument to container_edit script via tab
- complete file path as sencond argument to ctonainer_edit script via tab (this will work the same way as local tab completion, but is smart enough to use the container's own directory structure)

# Usage

	container_edit [container] [filepath]

# Installation

- copy both scripts to ~/bin directory on VM
- add ~/bin to $PATH
- (optional) create an alias for the script (I use 'cv')
- add a command to source ~/bin/container_edit_completion into your ~/.bashrc
