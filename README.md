# MTE 481/482 Capstone - Group 46 - bracketbotcapstone.github.io

[Webpage](bracketbotcapstone.github.io)

----

### Members

Jai Prajapati - j2prajap@uwaterloo.ca

Angad Bajwa - a29bajwa@uwaterloo.ca

Brian Machado - bmachado@uwaterloo.ca

Ivan Yevenko - iyevenko@uwaterloo.ca

----

### Capstone Development

Development repo is [bracket_bot_capstone](https://github.com/BracketBotCapstone/bracket_bot_capstone)

----

### How to develop on Webpage

#### Clone the repo:

```bash
git clone git@github.com:BracketBotCapstone/BracketBotCapstone.github.io.git
```

#### Install jekyll - one time setup

macOS
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install chruby ruby-install xz
ruby-install ruby 3.1.3
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.1.3" >> ~/.zshrc
ruby -v
gem install jekyll
```

Ubuntu
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
gem install jekyll bundler
```

#### Starting website locally

Starting jekyll:
```bash
bundle install
bundle exec jekyll server
```

#### Adding Content

To create a new design log update, add a new markdown file to [collections/_posts](collections/_posts)

To update the design details, edit [pages/work/design.html](/pages/work/design.html)
