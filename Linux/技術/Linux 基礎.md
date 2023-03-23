## 檔案結構

- Linux 檔案結構是一個 tree，這個 tree 的 root 稱為 **根目錄 (/)**
	![](https://i.imgur.com/vyGJeTL.png)
- 在 Linux 上可以有很多使用者，包含 **一般使用者** 與 **超級管理員 (root)**
- 每個檔案都有一個擁有者、所屬群組，也可以個別設定擁有者、所屬群組、其他人的讀取、修改、執行權限
- 使用者可以有一個 **家目錄 (~)**，是打開終端機預設的初始位置，一般使用者的家目錄通常為 **/home/<使用者名稱>**，超級管理員的家目錄通常是 **/root**
- 表達檔案或資料夾位置可使用 **絕對路徑** 或 **相對路徑**
    - 絕對路徑以 **根目錄 (/)** 出發，例如：/var/www、/home/squid/Documents
    - 相對路徑會由參考目錄出發，常見的參考目錄有：
        - 當前目錄 (.)
        - 上一層目錄 (..)
        - 家目錄 (~)
        - 上一次處在的目錄 (-)
    - 例如：./Desktop、~/Documents/Programming
- 在 Linux 中，以 **點 (.)** 開頭的檔案或目錄為隱藏檔案，例如：.vim、.bashrc，這些檔案是存在的，但 GUI 介面中看不到
- Windows 上直接以副檔名判別檔案類型，像是 txt 是文字檔、exe 是執行檔，更改附檔名會造成檔案無法開啟；但在 Linux 上，副檔名只是給使用者判別用的，他們本質上就是文字檔或二進制檔，像是一個 Python 檔，就算不打副檔名，一樣能透過 `python` 指令執行。
- **星號 ( * )** 為萬用字元，表示任意長度的任意字元，例如：
    - *.cpp 表示所有 cpp 檔
    - ./* 表示當前目錄下所有檔案

## 檔案管理

- `pwd`：*print work directory*，印出當前目錄的絕對路徑
	![](https://i.imgur.com/rbmC1o4.png)

- `ls`：*list*，印出有哪些檔案或目錄（不包含隱藏檔案目錄），後方可以輸入目標目錄，當只輸入 `ls` 時，視為當下的目錄
	![](https://i.imgur.com/qdNoDPy.png)
    - `ls -l`：以詳細資訊列表印出，在 Ubuntu 中 `ll` 指令可達到相同效果
	      ![](https://i.imgur.com/sMGjYVF.png)
    
    - `ls -a`：印出所有檔案目錄，包含隱藏檔案目錄 (以 "." 開頭的檔案目錄)
	      ![](https://i.imgur.com/tdRjiIF.png)
    
    - 以上兩者可混用 `ls -la`
	      ![](https://i.imgur.com/duXhkf2.png)

- `cd`：*change directory*，更換目錄到指定路徑，可以是相對或絕對路徑，當後方完全沒有路徑時，將回到家目錄
	  ![](https://i.imgur.com/qmWH8Fs.png)

- `mkdir`：*make directory*，建立新目錄，後方輸入新目錄名稱
	  ![](https://i.imgur.com/i9kXVFH.png)

- `cp`：*copy*，複製檔案，先輸入原檔案路徑，再輸入新檔案路徑
    - 只複製檔案
        - 同一個路徑
	          ![](https://i.imgur.com/RXBiwp1.png)

        - 不同路徑
	          ![](https://i.imgur.com/aE2v7nd.png)
    - `cp -r`：複製整個資料夾，以及裡面的所有東西
	      ![](https://i.imgur.com/Tc24Ajn.png)

- `mv`：*move*，移動檔案或目錄（也可當作重新命名），先輸入原檔案路徑，再輸入新檔案路徑
    - 移動
	      ![](https://i.imgur.com/XbeDbJf.png)
      
    - 重新命名
	      ![](https://i.imgur.com/Q44Pymz.png)

- `rm`：*remove*，刪除指定檔案，不會進到資源回收桶，一去不復返
    - 刪除檔案
	      ![](https://i.imgur.com/FsYysrZ.png)
    
    - `rm -r`：刪除整個目錄（謹慎操作，一去不復返）
	      ![](https://i.imgur.com/Xja3v6f.png)

- `cat`：印出指定的檔案內容
	  ![](https://i.imgur.com/9Jt3fik.png)
  
## 文字編輯器

- 常用的文字編輯器有 `nano` 和 `vim`
- 先使用 `sudo apt install nano vim` 安裝套件
- 用法：`vim <filename>` 或 `nano <filename>`，如果是原本不存在的檔案，會自動建立一個新的
- nano
	  ![](https://i.imgur.com/pKk5rxU.png)
    - 操作上較直覺
    - 下方的快捷鍵列表，^ 表示 Ctrl 鍵，例如按下 Ctrl + X 可離開編輯器
- vim
	  ![](https://i.imgur.com/PdxfujD.png)
    - 極度新手不友善
    - 但有很多快捷鍵，熟練的話會大幅增加打 code 效率
    - 有個 .vimrc 的設定檔可以自訂編輯器功能、外觀
    - 使用方法：
        - 按下 i 鍵進入編輯模式；按下 ESC 鍵離開編輯模式
        - 在非編輯模式下輸入冒號 (:) 可輸入指令
            - w：儲存
            - q：離開
            - !：強制執行指令
          > 所以想要存檔並離開，需輸入 :wq
          > 想要不儲存就離開，需輸入 :q!
    - 還有很多指令、快捷鍵，那只有 coding 魔人才會用
  
## 系統管理

- 一般使用者無法執行會影響到系統的操作，只有超級管理員可以
- 使用 `sudo` (*super user do*) 可一次性的以超級管理員執行後面的指令
	  ![](https://i.imgur.com/Jw2nxkE.png)
- `sudo -i` 可讓身分變成超級管理員，雖然這樣不用每行指令前都多打一個 `sudo`，但不建議使用

## 套件管理

- 不同的 Linux 發行版有不同的套件管理工具（Ubuntu 使用的是 `apt`），套件管理工具可以讓套件的安裝、更新、相依性處理更方便
    - `sudo apt update`：與伺服器同步套件庫
    - `sudo apt upgrade`：更新所有套件
    - `sudo apt install <package-name>`：安裝特定的套件
    - `sudo apt remove <package-name>`：移除特定的套件

## 權限管理

- Linux 的基礎權限有三種：讀取 r、寫入 w、執行 x
- 以上三種權限可分別為，擁有者 owner、所屬群組 group、其他人 anyone，分別設置不同的組合
- 使用 `ls -l` 可以看到檔案的權限設置
	  ![](https://i.imgur.com/DDg2cGP.png)
    - 第一欄位 `drwxr-x---`
        - d 表示這個項目是一個目錄；- 表示為檔案；l 表示為連結捷徑
        - 第一組 r w x 是擁有者所擁有的權限，三者都有出現表示擁有者可以存取、可以寫入、可以執行（對於目錄而言，執行與否表示是否能進入這個目錄）
        - 第二組 r - x 是所屬群組的權限，此處有讀和執行的權限，但沒有寫入的權限
        - 第三組 - - - 是除了上述兩者，所有其他人（超級管理員除外），完全沒有讀寫執行的權限
      ![](https://i.imgur.com/Frc7LYw.png)
    - 第二欄位 數字
        - 如果是目錄，顯示該目錄底下的項目數量
        - 其他類型，此數字為 1
    - 第三欄位 `root` `an920107`
        - 為檔案目錄的擁有者
    - 第四欄位 `root` `an920107`
        - 為檔案目錄的所屬群組
        - 每個使用者都有一個自己的群組，可以把其他使用者加入這個群組，那麼其他使用者將適用於所屬群組的權限
- `chmod`：*chane mode*
- `chown`：*chane owner*

## 其他

- `man`：*manual*，後面輸入指令，可以查詢該指令的使用方式（雖然多數時候 Google 可能比較好用）
	  ![](https://i.imgur.com/j2gzWii.png)
	  ![](https://i.imgur.com/jbts2QE.png)

