Installed Chrome- Firefox 

https://docs.brew.sh/Installation

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

https://minikube.sigs.k8s.io/docs/start/

echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /Users/sherief/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/sherief/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"

https://rvm.io/rvm/install
gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

brew install gpg go wget git

\curl -sSL https://get.rvm.io | bash


Downloaded Linux Images

https://ubuntu.com/

http://centos.mirrors.proxad.net/7.9.2009/isos/x86_64/



----------------------------------

SSH Setup for Github and in general:

$ ssh-keygen -t ed25519 -C 'mdsheriefibunsali@gmail.com'

$ ls $HOME/.ssh

id_ed25519	id_ed25519.pub
id_ed25519 - Private Key
id_ed25519.pub - Public Key

$ eval "$(ssh-agent -s)"
Agent pid 31327

$ touch ~/.ssh/config

Copy and paste this to ~/.ssh/config
Host *.github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519

Copy the content of id_ed25519.pub and paste to https://github.com/settings/ssh/new 

Verify the public key is added.

https://github.com/settings/keys

Detailed Guide:
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

Setting up a new repository
$ echo "# firstapp" >> README.md
$ less README.md
$ git init
$ git config --global init.defaultBranch main
$ git branch -m main

$ git config --global user.email "mdsheriefibunsali@gmail.com"
$ git config --global user.name "Mohammed Sherief Ibunsali"

Test the Connection with Github (using SSH Keys)
$ ssh -T git@github.com

$ git commit -m "first commit"
$ git remote add origin git@github.com:mdsherief/firstapp.git
# Push your changes to remote (origin) branch (main)
$ git push -u origin main

Editing a File and Pushing (Uploading) it to Github
$ echo "This is new line to be committed" >> README.md
  >> - To append to end of the file
$ less README.md
$ git status
$ git diff
# Add only README.md
$ git add README.md
# To add multiple edited files (with dot)
$ git add . 
$ git status
# # Push your changes to remote (origin) branch (main) 
# No need to add explicitly from second time
$ git push

$

----------------------------------

Ruby Installation:
$ rvm list known
$ rvm install ruby-3.1.2
$ rvm list
   =* ruby-3.1.2 [ arm64 ]

  # => - current
  # =* - current && default
  #  * - default

$ ruby --version
ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [arm64-darwin21]

-------------------------
# To find where an cmd line tool is installed.
$ which ls
$ which node

echo $PATH
/Users/sherief/.rvm/gems/ruby-3.1.2/bin:/Users/sherief/.rvm/gems/ruby-3.1.2@global/bin:/Users/sherief/.rvm/rubies/ruby-3.1.2/bin:/Users/sherief/.rvm/bin:/opt/homebrew/bin:/opt/homebrew/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin


$ brew install pyenv


-----------------------------
# Adding Code to the path so you can invoke from Terminal

cat << EOF >> ~/.zprofile
# Add Visual Studio Code (code)
export PATH="\$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
EOF

source ~/.zprofile

-------
Python with Pyenv

$ brew install pyenv
$ pyenv install --list
$ pyenv install  3.10.7
$ pyenv global 3.10.7
$ pyenv init

# Load pyenv automatically by appending
# the following to
~/.zprofile (for login shells)
and ~/.zshrc (for interactive shells) :

export PYENV_ROOT="$HOME/.pyenv"
command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"

$ source $HOME/.zshrc
$ pyenv version
$ python --version
Python 3.10.7

# To create another pyenv with different version of python
$ mkdir -p python/sample_app
$ pyenv install 2.7.18
$ pyenv local  2.7.18
$ python --version
Python 2.7.18
$ cd ..
$ python --version
Python 3.10.7

---------
React:

$ brew install node
$ mkdir react
$ cd react
$ node --version
v18.11.0
$ npm --version
8.19.2

$ npm install --save react react-dom

$ npx create-react-app first_react_app
$ cd first_react_app
$ npm start 

-------
Mac/Linux General Commands
# to remove a folder and it contents recursively
$ rm -rf <folder>
$ rm -rf package*

-------
