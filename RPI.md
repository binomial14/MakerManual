## 樹莓派 RPi 3B(Raspberry Pi 3B)

### 基本介紹
Raspberry Pi 是由劍橋大學的 Eben Upton 及其他幾位老師所設計的，最初只是為了提供一台平價的電腦和自由軟體，讓學生可以輕鬆取得，用來學習跟練習電腦科學的相關知識。
根據 Make:Taiwan - 十個專訪 Raspberry Pi 創始人 Eben Upton 的問題 的描述，之所以被稱為「樹莓派」，是因為 Raspberry 是樹莓，也有人叫覆盆子，而這種水果還沒有人用來當 Logo。
Pi 是 Python 這種程式語言發音的一部份，中文就直接音譯，合起來就像蘋果派一樣的感覺。
		
	圖片待補

雖然它設計出來的原始目的是在教學用途，但是也因為它價格低廉、容易取得、方便攜帶、安裝簡單、運作穩定，而且又可以連接其他週邊設備，導致不止在教育界盛行，在創客 (Maker) 圈也非常愛用它來實作各種不同有趣的點子，甚至有些業界的朋友也真的用它來製作產品、套件、週邊或是專案。

樹莓派是一個小型的單板計算機。通過將鍵盤，滑鼠，顯示器等外圍設備連接到Raspberry Pi，它將作為一台迷你個人電腦，並廣泛用於實時圖像/視頻處理，基於IoT的應用程序和機器人應用程序。

樹莓派比筆記本電腦或台式機慢，但仍然是一個電腦，可以提供所有預期的功能或能力，並且低功耗，我們應該使用SD卡（建議至少8 GB）來存儲操作系統（操作系統）。

樹莓派基金會正式提供基於Debian的Raspbian操作系統。此外，他們還為Raspberry Pi提供NOOBS操作系統。我們可以安裝Ubuntu，Archlinux，RISC OS，Windows 10 IOT Core等幾個第三方版本的操作系統。

Raspbian OS是可以免費使用的官方操作系統。這個操作系統是有效的優化與樹莓派使用。Raspbian有GUI，其中包括瀏覽，Python編程，辦公室，遊戲等工具。

樹莓派不僅僅是計算機，因為它提供了訪問片上硬件，即用於開發應用程序的GPIO。通過訪問GPIO，我們可以連接LED，電機，傳感器等設備，也可以控制它們。

它具有基於ARM的Broadcom處理器SoC以及片上GPU（圖形處理單元）。CPU速度從700 MHz到1.2 GHz不等。此外，它具有從256 MB到1 GB的板載SDRAM。同時還提供片上SPI，I2C，I2S和UART模塊。

#### 有不同版本的raspberry  pi可用，如下所示
1. Raspberry Pi 1 Model A
2. Raspberry Pi 1 Model A+
3. Raspberry Pi 1 Model B
4. Raspberry Pi 1 Model B+
5. Raspberry Pi 2 Model B
6. Raspberry Pi 3 Model B
7. Raspberry Pi 3 Model B+
8. Raspberry Pi Zero

### 硬體介紹
	圖片待補

#### 上面顯示的一些硬件組件如下
1.  HDMI（高清晰度多媒體接口）：用於將未壓縮的視頻或數字音頻數據傳輸到計算機監視器，數字電視等。通常，此HDMI端口有助於將樹莓派連接到數字電視。
2. 攝像頭接口： CSI（攝像頭串行接口）接口在Broadcom處理器和Pi攝像頭之間提供連接。該接口提供兩個設備之間的電連接。
3. DSI顯示器接口： DSI（顯示器串行接口）顯示器接口用於使用15針帶狀電纜將LCD連接到樹莓派。DSI提供快速的高分辨率顯示接口，專門用於將視頻數據直接從GPU發送到LCD顯示器。
4.複合視頻和音頻輸出：複合視頻和音頻輸出端口將視頻和音頻信號傳輸到音頻/視頻系統。
5. 電源指示燈：用於電源指示的紅色指示燈。電源連接到樹莓派時，該指示燈將點亮。它直接連接到5V，並且只要電源電壓降到4.63V以下就會開始閃爍。
6. ACT PWR： ACT PWR是顯示SD卡活動的綠色LED。

#### GPIO腳位圖
	圖片待補

#### RPi作業系統安裝
1. 從[Raspberry PI](https://www.raspberrypi.org/downloads/noobs/)官網 下載 NOOBS 壓縮檔。
2. 將 Micro SD 卡 置入 SD Adapter，按此[官方文件](https://www.raspberrypi.org/documentation/installation/sdxc_formatting.md)格式化。注 [4]
3. 將 NOOBS 壓縮檔裡所有檔案解壓縮放進 SD 卡裡。
4. 把 Micro SD 卡拔出 Adapter，並插入樹莓派插槽。
5. 裝上樹莓派外殼 (如果有的話)，插上鍵盤滑鼠、插上 HDMI與外接螢幕、Ethernet 網路線 (如果有的話)、Micro USB 線。
6. 開機並等待安裝畫面，如果無法正常進入安裝畫面回到第一步測試。
7. 如果需要其他作業系統、可以設定 有線 或 無線 網路來下載作業系統安裝。

*備注: 假設你是用 Windows 平台，首先必須用 SD Formatter 刪除格式化 SD 卡 (開啟自動調整尺寸)、使用 guiformat.exe 來格式化 SD 卡為 FAT 32 格式。*

如果文字說明不太清楚，讀者可以參考官方文件的[教學影片](https://www.raspberrypi.org/help/videos/)。

#### 安裝完的桌面環境
	圖片待補

### RPi軟體準備
安裝完作業系統，會有預設的管理者帳號pi ，密碼是raspberry。
強烈建議把預設密碼改掉，從左上角 Menu / 偏好設定 / Raspberry PI 設定 裡可以更改密碼。或者打開 LX Terminal ，執行 passwd 更改密碼。

	圖片待補

更改密碼讓你的主機在公開網路上不會被人輕易取得系統管理者帳號。 

1. 新增 / 刪除 使用者
Raspbian 作業系統是基於開源 Linux 作業系統修改、維護，支援多人多工同時連線作業。所以可以開帳號讓使用者登入使用。
在終端機 或 LX Terminal 底下，以下 `<username>` 代表你可以任意一個名字、新帳號名。
2. 新增使用者:
		
		sudo useradd `<username>`
或者

	sudo adduser `<username>`
然後輸入新密碼、其他資訊完成創建帳號。

3. 刪除使用者：

		sudo userdel -r `<username>`

4. 給予使用者管理權限：

		sudo usermod -a -G sudo `<username>`
或者

		sudo visudo
(可以參考[這裡](https://www.raspberrypi.org/documentation/linux/usage/users.md)，盡量小心使用此指令)

5. 列出系統上有哪些使用者:
	
		compgen -u

### RPi I/O

接下來介紹如何控制RPi的I/O(input/output)。

+ RPi和一般電腦最大的差別就是你可以自由地使用內建的腳位，自己設計不同的電路來實驗與應用。

+ RPi的I/O一般稱作GPIO(general purpose I/O)，中文稱"通用輸入輸出"，因為這些腳位可以根據需求設定為輸入、輸出、或同時輸入輸出。

以下分為幾個部分介紹GPIO的使用：

1. 相關套件
在python下可以使用GPIO這個套件來控制RPi的GPIO，安裝方法如下

		sudo apt-get install python-rpi.gpio python3-rpi.gpio

2. 基本設定

首先我們要引入GPIO這個套件

	import RPi.GPIO as GPIO

接著設定腳位的編號模式。在rpi的gpio中，腳位的編號分成兩種模式
一種是RPi版上的編號(GPIO.BOARD)，腳位編號如板子上的編號
另一種是博通的標準(GPIO.BCM)，腳位編號如圖一當中有GPIO編號的腳位
以下範例使用GPIO.BCM

	GPIO.setmode(GPIO.BCM)

設定完腳位模式後，要設定這個腳位的功能是輸入還是輸出。
以下示範設腳位12為輸入，並使用input()來讀取腳位12的值

```python
GPIO.setup(12, GPIO.IN)
if GPIO.input(12):                   # input()返回True
print(“讀到高電位”)
else:                                # input()返回False
print(“讀到低電位”)
```

如果要設定腳位功能為輸出，則必須使用output()來讓這個腳位輸出指定的電位

```python
GPIO.setup(12, GPIO.OUT)
GPIO.output(12, GPIO.HIGH)           # 輸出高電位
GPIO.output(12, GPIO.LOW)            # 輸出低電位
```

3. 偵測事件

當一個腳位是輸入腳位時，我們要有辦法偵測這個腳位的電位發生變化(比如按下按鈕)，我們稱這個變化為事件。
在GPIO這個套件裏頭，偵測事件的發生可以有幾種方法：
+ 利用 while 迴圈檢查事件
+ 利用 wait_for_edge() 等待事件
+ 利用 add_event_detect() 註冊事件

1. 利用 while 迴圈檢查事件
如果我們希望程式可以停在某處直到某個腳位電位改變(比如按按鈕)，我們可以這樣寫

```python
print(“程式暫停”)
while GPIO.input(12) == GPIO.LOW:
pass
print(“程式繼續”)
```
	
如果在執行到 while 之前，腳位12都是LOW，那麼這段程式就會暫停，直到腳位12變HIGH。
使用 while 迴圈不斷檢查某個腳位是否改變是一件很浪費效能的事情，因為CPU會一直跑這個迴圈。此外，如果我們要一次檢查很多腳位，比如一台娃娃機最少有上下左右四個以上的按鈕，就要同時檢查這麼多腳位，而且不同腳位必須對應到不同功能，對於程式的效能和反應時間都是一種傷害。因此，以下介紹另一種寫法，可以避免用迴圈一直檢查腳位的電位。

2. 利用 wait_for_edge() 等待事件
wait_for_edge() 顧名思義就是要等一個邊界，邊界的意思是電位變化，比如高電位變成低電位，因此可以看成是一種事件。
事件(邊界)可以分成三種類型：

+ GPIO.RISING (電位由低變高)
+ GPIO.FALLING (電位由高變低)
+ GPIO.BOTH (以上兩種都算)

以下這段寫法與上面的 while 寫法功能一模一樣

```python
print(“程式暫停”)
GPIO.wait_for_edge(12, GPIO.RISING)
print(“程式繼續”)
```

如果程式一開始腳位12都是低電位，那麼程式就會停在wait_for_edge(12,GPIO.RISING) 直到偵測到腳位12的電位變高(RISING)。

wait_for_edge()這個方法相較於while，可以節省程式在等待事件時所需要耗費的效能，不用一直跑迴圈。但如果今天我們希望程式在等待某事件的時候，還能夠一邊做其他運算，讓等待事件這個工作完全和主要的程式分開，不會因為要等這個事件而讓整個程式停下來，也不會因為程式在執行其他運算而錯過這個事件，我們需要更進階的寫法。

3. 利用 add_event_detect() 註冊事件
這個寫法可以讓我們在程式一開始就"註冊"需要偵測的腳位和事件，註冊完之後程式就會自動偵測事件與執行事件發生後應該進行的反應。簡單來說有點像把這個工作丟到背景，主程式可以繼續執行其他運算。
這邊先說明這個函數的樣子

```python
GPIO.add_event_detect(腳位, 事件, 事件發生時要自動做的事)
```

當「腳位」發生了「事件」，程式就會自動執行「事件發生時要自動做的事」。
「事件發生時要自動做的事」在英文稱作callback，直接翻譯是回呼(或之類的)，意思是某事件發生時會自動回去執行的程式碼。
這段程式碼可以用一個自訂函式(method)來表示，以下舉例就用my_callback來命名。

由於my_callback本身是一個自訂函式，因此我們要先定義好這個函式：

```python
def my_callback(channel):
print("這是一個自訂函數")
print("這個函數會在channel {} 發生指定事件時被執行!".format(channel))
```

此時我們想註冊：當腳位12發生電位變高的事件，程式必須自動執行my_callback，那我們可以透過

```python
GPIO.add_event_detect(12, GPIO.RISING, callback=my_callback)
```

來註冊事件。

這個寫法的好處是，他和wait_for_edge()一樣不需要一直跑迴圈等待事件。此外，只要你註冊完指定腳位的事件和callback，程式就會在事件發生時自動執行callback，讓程式寫起來更簡潔，也更好進行複雜的開發。

### 資料來源
http://leonxlin.pixnet.net/blog/post/329986608-%E7%AC%AC%E4%B8%80%E6%AC%A1%E7%8E%A9%E6%A8%B9%E8%8E%93%E6%B4%BE%E5%B0%B1%E4%B8%8A%E6%89%8B---raspberry-pi-3-model-b-%E6%96%B0
https://sites.google.com/site/raspberypishare0918/home


