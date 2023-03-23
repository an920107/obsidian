- 安裝 zsh
	```shell
	sudo apt install zsh
	```
- 將 zsh 設定為預設 shell
	```shell
	chsh -s $(which zsh)
	```
- 安裝 oh-my-zsh
	```shell
	sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
	```
- 安裝 pwerlevel p10k
	```shell
	git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
	```
- 編輯 `~/zshrc`，將 `ZSH_THEME` 修改為 `"powerlevel10k/powerlevel10k"`
- 立即生效 `~/zshrc` 設定檔
	```shell
	source ~/.zshrc
	```
- 設定 powerlevel 10k 外觀
	```shell
	p10k configure
	```
- 安裝 nerd font 字體
	https://github.com/ryanoasis/nerd-fonts/releases