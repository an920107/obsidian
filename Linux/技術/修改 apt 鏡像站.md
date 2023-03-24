- Ubuntu 鏡像站列表 https://launchpad.net/ubuntu/+archivemirrors
	> 在台灣 `free.nchc.org.tw` 是最快的鏡像站
- 編輯 `/etc/apt/sources.list`，將 `tw.archive.ubuntu.com` 全部取代為 `free.nchc.org.tw`
	> 在 vim 中可使用指令
	> `:%s/tw.archive.ubuntu.com/free.nchc.org.tw/g`