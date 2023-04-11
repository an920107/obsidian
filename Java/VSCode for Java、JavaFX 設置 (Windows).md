## 前置作業：軟體、編譯器、Library 安裝

### 安裝 VSCode
![](https://i.imgur.com/vCVSCvZ.png)
> ▲ 筆者 Prefer "System Installer" 這個版本，安裝過程無腦選下一步（可視需求更改安裝位置，以及註冊右鍵選單按鈕、附檔名連結等設置）
> 下載連結：https://code.visualstudio.com/download

</br>

![](https://i.imgur.com/VVNfDxB.png)
> ▲ 跟筆者一樣多益只有455的話，可自左邊 "延伸模組" 中輸入 "Chinese" 安裝中文介面，安裝完成重啟即可套用

</br>

![](https://i.imgur.com/QH5FGS3.png)
> ▲ 同樣在 "延伸模組" 中搜尋 "Java" 安裝圖中所列六項套件

</br>

![](https://i.imgur.com/VCqkl6h.png)
> ▲ 安裝套件 "JavaFX"
> 以上完成 VSCode 的前置作業

</br>


### 安裝 OpenJDK
![](https://i.imgur.com/yYzSSNO.png)
> ▲ 選擇 "Windows/x64 zip"
> 下載連結：https://jdk.java.net/17/

</br>

![](https://i.imgur.com/A7bDBvw.png)
> ▲ 解壓縮放到喜歡的位置，筆者是放在 "C:\Compilers\Java" 之下（此位置請記住，之後會用到）

</br>

![](https://i.imgur.com/lCaAq4Z.png)
> ▲ 在搜尋中輸入 "環境變數" 並開啟

</br>

![](https://i.imgur.com/DY2QI9L.png)
> ▲ 點選 "環境變數"，自下方新增一系統變數，其名稱與值分別為："JAVA_HOME" "[方才安裝OpenJDK的位置]"

</br>

![](https://i.imgur.com/aT1RMg6.png)
> ▲ 在下方系統變數找到 "Path" 編輯，選擇新增，輸入 "%JAVA_HOME%\bin"，最後確認更改關閉視窗

</br>

![](https://i.imgur.com/wCCd3C7.png)
> ▲ 搜尋 "cmd" 開啟，輸入 "java -version"，若回應類似圖中文字，則表示 Java 環境安裝成功

</br>


### 安裝 JavaFX SDK

![](https://i.imgur.com/niPOGSG.png)
> ▲ 依圖片選擇相對應版本下載
> 下載連結：https://gluonhq.com/products/javafx/

</br>

![](https://i.imgur.com/d8RhGoA.png)
> ▲ 解壓縮放到喜歡的位置，筆者是放在 "C:\Compilers\Java" 之下（此位置請記住，之後會用到），至此開發 JavaFX 所需檔案的已備妥

</br>


### 安裝 Scene Builder (Optional)

![](https://i.imgur.com/CyNGCiU.png)
> ▲ 選擇 "Windows Installer" 版本下載，安裝過程無腦下一步即可（可視需求更改安裝位置）
> 下載連結：https://gluonhq.com/products/scene-builder/#download

</br>


## 環境設置 & 基本使用說明


### 建立 Java 專案

![](https://i.imgur.com/3y9Bz9z.png)
> ▲ 按下 "Ctrl + Shift + P" 並輸入 "Create Java Project" 創建 Java 專案

</br>

![](https://i.imgur.com/qgZSy98.png)
> ▲ 選擇 "No build tools"

</br>

![](https://i.imgur.com/twyIY4q.png)
> ▲ 選擇專案存放位置（稍後將會在此資料夾下，再生成一個專案資料夾）

</br>

![](https://i.imgur.com/PHeqZFe.png)
> ▲ 輸入專案名稱，確認後將直接開啟專案資料夾（工作區）

</br>

![](https://i.imgur.com/8mqXa5Y.png)
> ▲ 往後欲重新開啟專案，點選 "檔案" > "開啟資料夾"，選擇專案資料夾即可（內含 ".vscode" 者）

</br>


### 導入 JavaFX SDK

![](https://i.imgur.com/e7XclDU.png)
> ▲ 打開專案中任意 Java 檔案後，左下角將出現 "Java Projects" 並將其展開
> （因筆者的 VSCode 有連結 Github 因此有綠色圖標，各位沒有顯示是正常的）

</br>

![](https://i.imgur.com/a4T6YXe.png)
> ▲ 如圖中所示點選 "Configure Classpath"

</br>

![](https://i.imgur.com/XUqqTxv.png)
> ▲ 確認 "Source" 與 "Output" 是否分別為 "src" 與 "bin"，最後點選下方 "add" 導入 JavaFX

</br>

![](https://i.imgur.com/N8u9IBM.png)
> ▲ 至安裝 JavaFX 處，進入其 "lib" 資料夾，利用 "Ctrl+A" 全選所有 jar 檔並確認導入

</br>

![](https://i.imgur.com/dfyEsqH.png)
> ▲ 完成後如圖所示

</br>


### 編譯設定檔建置

![](https://i.imgur.com/leIDhIb.png)
```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "java",
            "name": "Launch Current File",
            "request": "launch",
            "mainClass": "${file}",
            "classPaths": ["${workspaceFolder}/bin"],
            "cwd": "${workspaceFolder}/bin",
            "vmArgs": "--module-path C:\\Compilers\\Java\\javafx-sdk-17.0.2\\lib --add-modules=javafx.controls,javafx.fxml"
        }
    ]
}
```
> ▲ 在 ".vscode" 中新增檔案 "launch.json"（對資料夾右鍵新增檔案），內容如上：
> （路徑部分依 JavaFX 安裝位置決定，反斜線須以跳脫字元呈現）

</br>

![](https://i.imgur.com/NTaanfl.png)
> ▲ 至此大功告成，往後編譯執行僅需按下 "F5"（或 "fn + F5"）即可

</br>


## 同場加映


### 終端機置右顯示

![](https://i.imgur.com/fjvZg88.png)

![](https://i.imgur.com/gTsgAtf.png)
> ▲ 右鍵終端機頂列空白處，點選 "向右移動面板" 騰出更多撰寫程式的空間

</br>

### 喚回終端機

> 若終端機被關閉，可按下 "Ctrl + \` "（鍵盤左上角 "ESC" 下方）叫回終端機

</br>

### 自定義程式碼片段

![](https://i.imgur.com/OUMcxxz.png)
> ▲ 點選 "檔案" > "喜好設定" > "使用者程式碼片段"

</br>

![](https://i.imgur.com/7EWoMwk.png)
> ▲ 搜尋 "Java" 並選擇

</br>

![](https://i.imgur.com/s6z5GnW.png)
```json
"片段名稱": {
    "prefix": "片段代碼",
    "body": [
        "程式碼內容（第一行）",
        "程式碼內容（第二行）",
        "..."
        // $1, $2, $3... 表示游標停留位置
    ]
}
```
> ▲ 可依喜好定義程式碼片段，簡要格式如上所述

</br>

![](https://i.imgur.com/ZEwYm6J.gif)
> ▲ 往後僅需輸入 "片段代碼"，完整程式碼將出現在建議清單中，按下 "Tab" 即可快速輸入