#開發板介紹
## Arduino
### 基本介紹
Arduino是一種開放授權的互動環境開發技術，互動裝置其實無所不在，像是冷氣的恆溫裝置，便是使用感測器偵測環境溫度，進行室內溫度的自動調節；還有汽車使用的倒車雷達，過於靠近物體便會發出聲音警告駕駛者。這些裝置為生活增加不少安全及便利，互動能帶給使用者驚喜，有時會以藝術品的方式呈現在生活當中。
以往要處理相關的電子設備時，需要透過工程師，逐一由單一小元件拼湊出整個電路。大多數的設計工具都是為了工程師設計，除了電路外還需要廣泛的知識，才有辦法完成電路。還好微處理器有了長足的進步，除了在使用上變得更為容易，價格上的減少更降低了學習的門檻。
 
**Arduino的特色** 
 
開放源碼(open-source)。不僅軟體是開放源碼，硬體也是開放的。軟體的開發環境可在網上免費下載，而Arduino 的電路設計圖也可從官方網站自行下載，依據自身之需求進行修，但須要符合創用CC授權條款(創用CC授權條款)。
開發簡單，參考資料多。在以往的硬體環境中，要開發微控制器的程式，開發者需要具備電子、電機及相關科系的背景，一般人需花費大量時間能有機會進入這個開發環境中。Arduino 學習門檻較為簡單，不需要電子電機相關科系的背景，也可以很容易學會Arduino相關互動裝置的開發。由於 Arduino 以公開共享為基礎，多數人都樂於分享自己的的創品，網路上能找的創作案子非常豐富。以此會基礎，有時只需要參考分享者的作品，依據自身的需求行調整，就可以在短時間內完成自己的創作。
 
**Arduino具備哪些東西**
 
主要可區分為三大類，分別是Arduino硬體、Arduino軟體及Arduino擴充原件。
硬體部分可購買現成的版子或是依據網路下載的電路途自行組裝，出學者建議購買現成的，根據Arduino官方網站所寫，台灣地區具有官方合法授權的代理商為藝科資訊 Aroboto Studio、PlayRobot 飆機器人/普特企業有限公司、iCshop (台灣)電子零件，電子材料，當然，還有別的商家，到網路上搜尋一下可找到不少，拍賣網站上也有，甚至也可以到國外網站去買。目前官方網站提供了許多不同的版子供開發者購買。

### 硬體介紹
	圖片待補
| **項目** | 規格 |
|:----------|:----------|
| **微控制器** | ATMEGA328 |
| **工作電壓** | 5V |
| **輸入電壓（推薦）**| 7~12V|
| **輸入電壓（限制）**| 6~20V|
| **數字I / O接腳** | 14（6個提供PWM輸出）|
| **模擬輸入接腳** | 6支|
| **EEPROM** | 1 KB（ATMEGA328 |
| **震盪速度** | 16MHz |

#### 數位 I/O 接腳
14 支數位 I/O 接腳 可以當作 input 使用，也可以當作 output 使用，使用方法是透過 pinMode(), digitalWrite(), anddigitalRead() 這幾個函式。這 14 支數位 I/O 接腳，其中幾支腳有特殊的功能：

+ **Serial 通訊**

0(RX) 和 1 (TX) 這兩支腳。用來接收(RX)與傳輸(TX) TTL 訊號的序列資料。這兩支腳也連接到 USB Converter 晶片中。

+ **外部中斷**

2 和 3 這兩支腳。這兩支腳可以利用外部事件觸發中斷。詳細內容請參考 attachInterrupt() 函式。

+ **PWM**

3, 5, 6, 9, 10 和 11 共六支腳。透過 analogWrite() 函式可以提供 8-bit 的 PWM 輸出。

+ **SPI**

10 (SS), 11 (MOSI), 12 (MISO) 和 13 (SCK) 這四支腳。這四支腳搭配 SPI Library 可提供 SPI 序列通訊。

+ **LED**

13。內建一顆 LED，當 pin 腳為 HIGH 時，LED 打開，當 pin 腳為 LOW 時，LED 關閉。

#### 類比輸入接腳
Arduino Uno 有 6 支類比輸入腳，標記為 A0 到 A5，每支腳都可提供 10 位元的解析 (即 1024 種不同的數值)。這些腳位所用的參考電壓預設為 0 到 5V，不過參考電壓也是可以更改的，方法是透過 AREF 腳和 analogReference()

+ **I2C**

4 (SDA) 和 5 (SCL) 這兩支腳。透過 Wire library 可以提供 I2C 通訊。

#### 其它
+ **AREF**

類比輸入的參考電壓，搭配 analogReference() 函式一起使用。

+ **Reset**

當 Reset 腳為 LOW 時，微控制器會重置。

### Arduino軟體介紹
#### 軟體取得
需要開發環境、編譯器、連結器、開發工具鏈、燒錄程式、板子與電腦連接所需要的驅動程式、等等等等，這些通通都已經準備好、打包好了，到Arduino官方網站的[下載頁面](http://arduino.cc/en/Main/Software)即可下載，可在Windows、Mac OS X、Linux上運行。 
	圖片待補
#### 開發環境
Arduino 的軟體開發環境是開放源碼，可以在Arduino官網免費下載，它所用的程式語言語法類似於 C/C++，具備文字編輯介面、常用工具欄、圖形化控制介面及錯誤編輯器，運用這個工具進行城市的上傳，及各項感應器的溝通。
 
#### 編譯環境
使用的Arduino編寫的軟件被稱為Sketch(腳本) 。 這些的腳本都寫在文本編輯器。 腳本名稱就是檔案名稱。上排圖形提供了新增、上傳、除錯及腳板切換介面。而console介面紀錄了完整的執行訊息，更可藉由此介面監視Arduino I/O數值。
 
#### Arduino開發環境的介面
	圖片待補

	**Verify** 檢查參數設定或引入程式是否產生錯誤。

	**Upload** 程式進行編譯，將程式碼透過USB介面燒錄至Arduino控制板。

	**New** 產生新的腳本 
	
	**Open** 開啟腳本，顯示在同一頁面上。點擊不同腳本便顯示不同腳本。 

	**Save** 腳本儲存。

	**Serial Monitor** 開啟監視器頁面，監視Arduino I/O介面。

Arduino 程式主要由 setup() 和 loop() 這兩個函式組成，
	圖片待補
因為setup()和 loop()是每支 Arduino 程式都會用到的兩個函式，為了方便，Arduino已經幫大家準備好程式基本架構了，編寫 Arduino程式時，可直接點選 File > Examples > 1.Basics > Digital ReadSerial 這個範本檔，另存新檔後，然後再修改setup()和 loop()兩個函式的內容即可。

### 範例
#### Arduino 序列通訊
當需要跟外部電腦通訊的時候，序列通訊 (Serial Communication) 就可以派上用場。
	圖片待補，Arduino 可以用同一條 USB cable 做程式上傳與序列通訊
所有 Arduino 的板子至少都有一個 Serial port (又稱 UART 或 USART)，Serial port 使用 TX (pin 1) 跟 RX (pin 0) 這兩支接腳來傳送與接收
	圖片待補Arduino 序列通訊接腳 TX/RX
*註：在使用 Arduino 的時候要特別注意，如果已經用於序列通訊，pin 0 與 1 這兩支接腳就不能再當作數位輸入或輸出使用 (Digital input or output)。*

要撰寫 MCU 的序列通訊程式，以往得先 K datasheet 把序列通訊相關的暫存器都弄熟，必須知道哪個暫存器是設定 baud rate 用的以及 baud rate 的計算方法，你得知道哪個暫存器負責控制傳輸，哪個負責控制接收，要傳送出去的資料該放到哪個暫存器，而收到的資料會被放在哪個暫存器…等，這個學習過程很花時間。
Arduino 的 [Serial Library](http://arduino.cc/en/Reference/Serial) 把序列通訊變得很簡單，當 Arduino 要跟外部電腦通訊的時候，只要使用 Serial 指令就可以了：
+ [Serial.begin()](http://arduino.cc/en/Serial/Begin) - 開啟 Serial Port 並設定通訊速率 (baud rate)
+ [Serial.println()](http://arduino.cc/en/Serial/Println) - 傳送資料到外部電腦
+ [Serial.read()](http://arduino.cc/en/Serial/Read) - 接收來自外部電腦的資料
+ [Serial.available()](https://www.arduino.cc/reference/en/language/functions/com) - 取得 Serial Port 可讀取的資料位元組數目 (number of bytes)，如果 Serial port 有資料進來，Serial.available ( ) 會回傳大於 0 的數值。

1.  將Arduino的值傳到 PC (Arduino >> PC)
如下圖接一個可變電阻來進行測試，然後在Serial Moniter (紅色箭頭指的地方)查看在量測到的數值。把這個資料傳到LabVIEW去處理。
	兩張圖待補
```c
void setup () {
     Serial.begin(9600);
}
void loop() {
int val = analogRead( 3 );     // 把Pin 2讀到的值寫入val的參數裡
Serial.println(val);           // 把參數 val 的值傳出去
}

```
2.  將PC的值傳到Arduino (PC >> Arduino)
除了傳回到PC端，也希望可以由PC端傳到Arduino上。
這個範例就運用LCD來顯示由PC端輸入的字元。
```c
#include <LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
void setup() {
	Serial.begin(9600);
	lcd.begin(16, 2);      // 定義LCD大小 
}
void loop() {
	char Nums[10];
	if(Serial.available () > 0) {
		lcd.print("Data = ");   // 顯示字元
		lcd.setCursor(7, 0);
		Serial.readBytes(Nums,10);  
		lcd.print (Nums); 
	}
}
```
操作的方式如下圖，打開Serial Monitor，在最上方輸入要顯示的文字，再按Send。
就會在LCD上顯示電腦上輸入的文字。
	圖片待補

3. 用PC控制Arduino，以決定動作的Case
當我們可以從PC端輸出之後，更進一步地是輸出代號，Arduino就進入Case之中，如此就可以在Case之中建立我們要的程式。
```c
void setup() {
	Serial.begin(9600);
	for (int ledPin = 2; ledPin <= 4; ledPin++) {
		pinMode(ledPin, OUTPUT);
	}      
}
void loop() {
	if (Serial.available() > 0) {  // 檢查是否有資料可供讀取
		int data = Serial.read();    // 讀取進來的 byte
		switch (data) {       // 根據收到的字元決定要打開哪顆 LED
			case '1':   
				digitalWrite(2, HIGH);
				break;
			case '2':   
				digitalWrite(3, HIGH);
				break;
			case '3':   
				digitalWrite(4, HIGH);
				break;
			default:
				for (int thisPin = 2; thisPin <= 6; thisPin++) {
					digitalWrite(thisPin, LOW);      // 關掉所有的 LED
				}
		}
	}
}
```

### 資料來源
http://newsletter.ascc.sinica.edu.tw/news/read_news.php?nid=2782
https://openhome.cc/Gossip/Books/mBlockArduino1-3and1-4.html#1-3
https://www.arduino.cc/
http://coopermaa2nd.blogspot.com/2011/02/arduino-serial-library.html
http://yhhuang1966.blogspot.com/2015/09/arduino.html
