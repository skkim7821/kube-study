- install zsh
sudo apt-get install zsh
sudo vim /etc/passwd

- install vim 
curl https://j.mp/spf13-vim3 -L > spf13-vim.sh && sh spf13-vim.sh

- install oh my zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"


- install zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

- install zsh autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

plugins=(zsh-syntax-highlighting zsh-autosuggestions)

- install linux brew
sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"

- install glances
curl -L https://bit.ly/glances | /bin/bash

- install watch
sudo apt-get install watch

