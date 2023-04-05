## 大數資料結構

- 使用 class BigNumber 繼承 vector\<int\>（動態陣列）
	![[Pasted image 20230405223346.png]]
- 利用運算子多載自訂義 BigNumber 的運算

## 測資說明

- 先透過 Python 生成一組組兩個 $n$ 位數，$n \in [1, 10000]$
	![[Pasted image 20230405224319.png]]
- 使用 wandb 製作花費毫秒 - 位數關係圖
	![[Pasted image 20230405224435.png]]

## 實驗結果

- 從下圖中可以看到 karatsuba 演算法大約位於位數 400 時超過傳統演算法
	![[螢幕擷取畫面 2023-04-05 222834.png]]