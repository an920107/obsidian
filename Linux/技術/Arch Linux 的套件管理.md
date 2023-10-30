## 簡述

Arch Linux 中多數套件可透過 `pacman` 指令直接安裝，但部份套件並非收錄在官方鏡像源中，而在 Arch Linux 中，這些未被收錄的套件全部都可以透過 [Arch Linux User Repository (AUR) ](https://aur.archlinux.org/) 中搜尋到，兩者安裝的方式不太相同

## 透過 Pacman 安裝

> 所有套件都可到 [Arch Linux - Package Search](https://archlinux.org/packages/) 找到

- 安裝套件
  
  ```bash
  pacman -S <package-name>
  ```

- 解除安裝套件
  
  ```bash
  pacman -R <package-name>
  ```

- 更新套件倉庫
  
  ```bash
  pacman -Syu
  ```

## 安裝 AUR 套件

^2b5f0c

> 所有套件都可以在 [AUR](https://aur.archlinux.org/) 中找到

1. 搜尋套件並進入想安裝的套件
   
   ![[Pasted image 20231030233422.png]]

2. 點選 git 連結以複製 git 位置
   
   ![[Pasted image 20231030233556.png]]

3. 用以下指令複製 git repo
   
   ```bash
   git clone <git-url>
   ```

4. `cd` 進入 git repo 資料夾並執行以下指令進行安裝
   
   ```bash
   makepkg -si
   ```
   
   > 安裝過程中可能會出現相依套件無法安裝的問題，其原因為該相依套件也是 AUR 套件，只須一一重複上述步驟將相依套件安裝完成即可
