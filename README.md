Subversion-Bash-Complete
========================

Bash completion for subversion commands and remote repositories

###Overview
This script is a merge between [Apache's subversion bash completion](http://svn.apache.org/repos/asf/subversion/trunk/tools/client-side/bash_completion) and [Androa's subversion remote repositories completion](https://gist.github.com/androa/4336613)

###Installation
To install the script simply add **source /path-to/svn-completion.sh** in .bashrc or .profile files in your home directory

###Usage
When you type **svn** in your terminal  you can then press *TAB* key to complete the commands for subversion like *merge*, *checkout*, etc. When you type for example **svn merge --** and you press the *TAB* key it will complete all of the arguments for *merge* command like *--revision*, *--non-interactive*, etc. To autocomplete remote paths simply add **^/** as argument and press *TAB* and it will start completing remote paths based on the base path of your repository.

###Toubleshooting
**Q:** Script is not working, what might be the problem?

**A:**  On some systems bash complete might not be activated, to activate it add this code to your .bashrc file
  ```
  [[ $PS1 && -f /usr/share/bash-completion/bash_completion ]] && \
    . /usr/share/bash-completion/bash_completion
  ```
**Q:** When I want to complete remote path nothing happens, any ideas?

**A:** You need to be in a directory where you have checkout a repository, so the script knows which is the base path of the repostitory. Or if you are in a repo folder, sometimes the server where the repository is located may need few seconds to respond on *svn list* command (this command is used to create and show a list with all the remote directories). The delay in *svn list* command will happen only once per terminal session.
