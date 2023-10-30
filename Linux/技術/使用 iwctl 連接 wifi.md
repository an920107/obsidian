- 查看可用的裝置[^1]
  
  ```iwd
  device list
  ```
  
  [^1]: `Mode` 欄位須為 `station` 模式才可以連接網路

- 掃描 wifi[^2]
  
  ```iwd
  station <interface> scan
  ```
  
  [^2]: `interface` 為 `device list` 的名稱，例如 wlan0  

- 取得 wifi 列表
  
  ```iwd
  station <interface> get-networks
  ```

- 連接 wifi
  
  ```iwd
  station <interface> connect <SSID>
  ```

- 查看連線狀態
  
  ```iwd
  station <interface> show
  ```
  
- 離開

  ```iwd
  exit
  ```