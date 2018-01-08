# dev-setup
Description for setting up a development environment under Linux (Ubuntu)

## Configure vim - "The Ultimate vimrc"
Full Documentation under: https://github.com/amix/vimrc

Installing the basic version:
```shell
git clone git://github.com/amix/vimrc.git ~/.vim_runtime
sh ~/.vim_runtime/install_basic_vimrc.sh
```


## Enhance bash with git-prompt
Full documentation can be found under https://github.com/magicmonty/bash-git-prompt

Clone this repository to your home directory.
```shell
cd ~
git clone https://github.com/magicmonty/bash-git-prompt.git .bash-git-prompt --depth=1
```
Configure  ~/.bashrc

```shell
# Set config variables first
GIT_PROMPT_ONLY_IN_REPO=1

# GIT_PROMPT_FETCH_REMOTE_STATUS=0   # uncomment to avoid fetching remote status

# GIT_PROMPT_SHOW_UPSTREAM=1 # uncomment to show upstream tracking branch
# GIT_PROMPT_SHOW_UNTRACKED_FILES=all # can be no, normal or all; determines counting of untracked files
# GIT_PROMPT_STATUS_COMMAND=gitstatus_pre-1.7.10.sh # uncomment to support Git older than 1.7.10

# GIT_PROMPT_START=...    # uncomment for custom prompt start sequence
# GIT_PROMPT_END=...      # uncomment for custom prompt end sequence

# as last entry source the gitprompt script
# GIT_PROMPT_THEME=Custom # use custom theme specified in file GIT_PROMPT_THEME_FILE (default ~/.git-prompt-colors.sh)
# GIT_PROMPT_THEME_FILE=~/.git-prompt-colors.sh
# GIT_PROMPT_THEME=Solarized # use theme optimized for solarized color scheme
source ~/.bash-git-prompt/gitprompt.sh

```

## Installing Oracle JDK on linux system

Downloading the jdk
```bash
wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u91-b14/jdk-8u91-linux-x64.tar.gz"
```

Installing the jdk
```bash
tar xzvf jdk-8u91-linux-x64.tar.gz
sudo mv jdk1.8.0_91 /usr/local/
sudo ln -s /usr/local/jdk1.8.0_91 /usr/local/jdk
```

Add path of jdk binaries and JAVA_HOME in  ~/.bashrc

```bash
# edit your .bashrc file with vi ~/.bashrc
export PATH=/usr/local/jdk/bin:$PATH
export JAVA_HOME=/usr/local/jdk
```

## Installing Maven
  
Downloading maven
```bash
wget http://mirror.klaus-uwe.me/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
```


Installing maven
```bash
tar xzvf apache-maven-3.3.9-bin.tar.gz
sudo mv apache-maven-3.3.9 /usr/local/
sudo ln -s /usr/local/apache-maven-3.3.9 /usr/local/maven
```

Add maven bin direcotry to path
```bash
# edit your .bashrc file with vi ~/.bashrc
export PATH=$PATH:/usr/local/maven/bin
```

source ~/.bashrc for jdk & maven environment
```bash
source ~/.bashrc
```

## Install groovy and grails
Using sdk
```
curl -s get.sdkman.io | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
sdk install groovy
sdk install grails




