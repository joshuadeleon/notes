# Notes for new install

## Applications

### Magnet
Download magnet from App Store

### f.lux
Download from net

### iTerm2
- Change codes for [jumping words](https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x)
- Change font size: 18

### Install Homebrew
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
then
```
alias brewup='brew update && brew upgrade && brew cleanup'
```

### Git
Mac has keeps an old version of git. To install: 

```
brew install git 
export PATH=/usr/local/bin:$PATH
```
Configure Git

```
git config --global user.name <my name>
git config --global user.email <my email>
```

### Install Anaconda

### Java
Install using cask
```
brew cask install java
```

### Haskel / Stack

```
brew install haskell-stack
```

### NodeJs

```
brew install node
```

### VSCode 
Download/install from site (can try cask next time)
(looks like)
```
brew cask visual-studio-code
```

- Change font size: 16

Open the Command Palette (⇧⌘P) and type 'shell command' to find the Shell Command: Install 'code' command in PATH command.

### Android Studio
Download/install from site
(looks like)
```
brew cask android-studio
```

### Scala
```
brew install scala sbt
```

### Security
```
brew cask install avast-security
```

### Chrome
```
brew cask install google-chrome
```

### DBeaver 
```
brew cask install dbeaver-community
```

### R & RStudio

#### XQuartz
```
brew cask install xquartz
```

#### Compile R
```
brew install r
```

#### RStudio
```
brew cask install rstudio
```

#### BitWarden
```
brew cask install bitwarden
brew install bitwarden-cli
```

#### AWS CLI
```
brew install awscli
```

#### Postman
```
brew cask install postman
```

#### SimpleNote
```
brew cask install simplenote
```


#### Draw.Io
```
brew cask install drawio
```

#### XnView MP
```
brew cask install xnviewmp

**Notes** 

To use with IntelliJ, set the Scala home to:
  `/usr/local/opt/scala/idea`

You can use `$SBT_OPTS` to pass additional JVM options to sbt.
Project specific options should be placed in .sbtopts in the root of your project.
Global settings should be placed in `/usr/local/etc/sbtopts`


