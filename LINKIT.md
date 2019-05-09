## LinkIt7697
隨著物聯網蓬勃發展，各家廠商皆推出物聯網開發平台，使開發者更容易發揮創意，做出各種物聯網應用。而國內科技大廠聯發科技於這幾年開始，相繼推出幾塊物聯網開發板，包含全功能聯網 （GSM/GPRS/Wi-Fi/Bluetooth/GNSS） 的 LinkIt ONE；可使用 OpenWrt （Linux） 開發較高端應用的 LinkIt Smart 7688/7688 Duo；於2017年6月又偕同Seeed Studio 推出了最新的物聯網開發板 LinkIt 7697。

LinkIt 7697使用 MT7697 作為主控制器，該晶片核心為主流的 ARM Cortex-M4（含浮點運算器），運行時脈為192MHz，同時提供 Wi-Fi 和 BLE（低功耗藍芽）兩種通訊最主要的通訊功能。軟體部分採用最為廣泛地FreeRTOS為作業系統，同時也提供 Arduino 開發環境，為目前學習開發物聯網應用的最佳開發平台之一。
	
![linkit](/img/Linkit/1.png)

### LinkIt硬體介紹

LinkIt 7697的大小，特別設計成能置入於麵包板上，並留有排針腳位可插杜邦線。開發板包含TX/RX LED，會於燒錄軟體或是透過序列埠有在傳送資料時閃爍，PWR LED會於有外部供電時點亮，USR LED則接至PIN 6可透過軟體控制。RST按鈕會重新開機，USR 按鈕可供使用者當作基本的輸入使用。LinkIt 7697開出了18 根可用腳位，可設置成GPIO （18），UART（2），I2C（1），SPI（1），PWM（18），EINT（4），ADC（4），IrDA（1）和I2S（1），除了ADC是 0至2.5V外，其他功能的工作電壓皆為3.3V。板子上有一個 MicroUSB 接頭，用於連接PC以燒錄軟體和供電（5V）。

![linkit](/img/Linkit/2.png)

**板子上最常用的硬件如下**

+ RST 按鈕 : 按下就會重新啟動開發板
+ USR 按鈕 : 板子上內建的輸入按鈕
+ UART RX LED : 序列埠往板子傳資料時會閃爍
+ UART TX LED:  序列埠往 PC 傳資料時會閃爍
+ Micro-USB : 透過 Micro-USB 線和電腦連接，主要用於下載程式和透過序列埠來列印 logs

![linkit](/img/Linkit/3.png)

**針腳的功能**
	
![linkit](/img/Linkit/4.png)

###  LinkIt系列開發版比較

LinkIt ONE 於 2014 年推出，為市面上少見具備 GSM/GPRS/Wi-Fi/BT/GNSS 多功能通訊的 Arduino 相容開發板，但隨著台灣電信商2G系統的關台，缺少了GSM/GPRS 的支持，LinkIt ONE 就缺少最主要的特點了。
目前LinkIt系列開發板針對物聯網應用，主要是提供兩個系列開發板：LinkIt Smart 7688/7688 Duo 用於較高階IoT節點或Gateway使用，可使用高階語言（Python/JS）與眾多Linux套件進行開發。而LinkIt 7697 則定位成較輕量的結點。
	
![linkit](/img/Linkit/5.jpg)

### LinkIt 開發環境介紹

LinkIt 7697針對不同族群的開發者，提供了三種開發環境：
1. GCC/KEIL/IAR : 提供給專業物聯網產品開發者的開發除錯環境，直接使用SDK進行開發，擁有最佳開發彈性且能優化出最佳效能。
2. Arduino IDE：提供給Maker/教育教學者的開發環境，完全相容於Arduino的程式語法，並包含LinkIt 7697獨家功能，例如LWIFI、LBLE、MCS（MediaTek Cloud Sandbox）、LFlash、LRTC及LRemote 等好用函式庫，大幅降低各種物聯網應用的開發門檻。
3. BlocklyDuino : 提供物聯網入門開發者的視覺化積木開發環境，透過簡單的積木拖拉就可組合出各種邏輯應用。BlocklyDuino 會將積木轉換成 Arduino 程式，也可作為從視覺化積木轉換至Arduino程式語言的學習工具。

![linkit](/img/Linkit/6.png)

### 開發環境設定(Arduino)

1. 前置準備作業

+ 準備一片 LinkIt 7697 開發板
+ 準備一條 Micro USB Cable
+ 準備一台電腦
作業系統版本:

Windows 7, 8 或 10

OS X 10.10 或以上

2. 開發板與電腦連接圖

將 Micro USB 端接 LinkIt 7697，另一端接電腦的 USB 插槽
		
![linkit](/img/Linkit/7.jpg)

3. 架構圖
LinkIt 7697 透過 COM 埠的介面來連接電腦，此介面經由 CP2102N USB-to-UART 來連接 MT7697 SoC 上的 UART0 埠，透過此埠能程式化快閃記憶體，也能經由 Arduino IDE 來撰寫程式。 

![linkit](/img/Linkit/8.png)

4. 安裝 Arduino IDE
	1. 開啟電腦的瀏覽器並輸入https://www.arduino.cc/en/Main/Software
	2. 選擇 Arduino IDE 1.8 以上的版本並 點選 Windows ZIP file for non admin install 
		
  ![linkit](/img/Linkit/9.png)

	3. 點選 JUST DOWNLOAD
			
  ![linkit](/img/Linkit/10.png)

	4. 下載完成並進行解壓縮會看到下方圖示的內容

	![linkit](/img/Linkit/11.png)

	5. 點選 arduino 的執行檔

	![linkit](/img/Linkit/12.png)

	6. 成功開啟後畫面如下

	![linkit](/img/Linkit/13.png)

5. 安裝 CP2102N USB-to-UART 驅動程式
	1. 開啟電腦的瀏覽器並輸入http://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers

	2. 依自己的作業系統來選擇相對應的安裝檔並安裝完成

	![linkit](/img/Linkit/14.png)
6. Arduino IDE 設定
	1. 檔案 ➙ 偏好設定

  ![linkit](/img/Linkit/15.png)

	2. 在額外的開發板管理員網址輸入以下 URL 再點選確定
			
	![linkit](/img/Linkit/16.png)

  ![linkit](/img/Linkit/17.png)
	3. 點選工具 ➙ 開發板 ➙ 開發板管理員

  ![linkit](/img/Linkit/18.png)
	
	4. 右上搜尋欄位輸入 7697

  ![linkit](/img/Linkit/19.png)
	
	5. 點選安裝

	![linkit](/img/Linkit/20.png)

	6. 點選工具 ➙ 開發板  ➙ 選擇 LinkIt 7697

	![linkit](/img/Linkit/21.png)

	7. 點選工具 ➙ 序列埠選擇在裝置管理員中所看到的連接埠號

	![linkit](/img/Linkit/22.png)

  ![linkit](/img/Linkit/23.png)

### 範例程式

**Hello World**

```c
void setup() {  
  // put your setup code here, to run once:
  Serial.begin(9600);
}

void loop() {  
  // put your main code here, to run repeatedly:
  Serial.println("Hello World");
  delay(1000);
}
```

![linkit](/img/Linkit/24.png)

1. 點選草稿碼 ➙ 上傳
	
![linkit](/img/Linkit/25.png)

2. 點選工具 ➙ 序列埠監控視窗
	
![linkit](/img/Linkit/26.png)

3. 序列埠監控視窗顯示 Hello World 
	
![linkit](/img/Linkit/27.png)

**讓LED燈閃爍**

1. 點選檔案 ➙ 範例 ➙ 01.Basic ➙ Blink
2. 再點選燒錄程式

![linkit](/img/Linkit/28.png)

3. 開發板上的 USR 燈開始閃爍

![linkit](/img/Linkit/29.png)
![linkit](/img/Linkit/30.png)

### 實際應用 App Inventor

**WiFi控制RGB三色LED**

#### 硬體組裝

請將LinkIt 7697與共陰RGB LED接上麵包板後，按照以下對應來接線：

 
| RGB LED|LinkIt 7697|
|---|---|
|R|P11 (D11)|
|G|P9|
|B|P7 (也是板載的USR LED)|
|GND|任一GND即可|

完成如下圖

![linkit](/img/Linkit/31.png)

#### App Inventor

請登入[MIT App Inventor](http://ai2.appinventor.mit.edu/)之後，建立一個新專案。或直接由[App Inventor中文學習網](https://sites.google.com/a/appinventor.tw/appinvetor/wifi_led_7697/WIFI_7697_LED.aia?attredirects=0&d=1)匯入本專案原始檔，唯一要修改的地方就是LinkIt 7697於您所指定網路所取得的IP位址。

**Designer**

1. 新增一個HorizontalArrangement，其中放入一個按鈕與Label，按鈕是用於設定IP，label則是用於顯示各種訊息。
2. 新增一個Textbox，Text設為空，Hint則設為”check 7697 ip in serial monitor”，用於輸入7697的實際IP
3. 新增一個TableArrangement，寬度設為Fill parent，高度為200像素。Row=2。Column=3。接著放入五個按鈕，寬度各為33%，高度則為100像素。這些分別用於讓RGB LED亮紅色(R)、綠色(G)、藍色(B)、白色(W)與熄滅。


完成後如下圖：

![linkit](/img/Linkit/32.png)

1. IP變數與設定IP按鈕
在此宣告一個變數，內容為`”http://192.168.1.73”`，這是LinkIt 7697於您所指定網路中所取得的IP。後續會把這個變數值用於Web元件的Url屬性。如果您只有一片LinkIt 7697或已經確定其IP的話，可以在此把它寫死不用修改。
不過為了方便起見，我們可以透過Textbox來設定新的IP，這在您現場有多片LinkIt 7697要控制時很方便。按下Button_setIP按鈕，會先檢查Textbox是為空，如果已輸入內容就將設定結果顯示於Label，否則將顯示錯誤訊息於Label。

![linkit](/img/Linkit/33.png)

2. 副程式用於設定URL與顯示訊息
在此宣告一個副程式來管理每次按下按鈕時所發送的字元與顯示訊息。請新增一個procedure，並點選藍色方塊來新增參數，點選副程式與參數名稱即可修改名稱。在此副程式名稱改為sendData，參數名稱為message/ command。

![linkit](/img/Linkit/34.png)

在sendData副程式中，我們會把送進來的參數分別用於7697的[網址](http://192.168.1.73/R)(組合結果：不同字元對應不同動作)與要顯示的訊息。最後再呼叫Web.Get來呼叫LinkIt 7697所產生的網址即可。

![linkit](/img/Linkit/35.png)

3.   各顏色燈光按鈕
這樣做程式是否變的很清爽呢？每個按鈕的差別只在於參數不同而已，當然如果我們要發送/W出去的話，LinkIt 7697也要有對應的程式才行。簡列如下：
Button_R(紅燈)：Red 與 /R
Button_G(綠燈)：Green 與 /G
Button_B(藍燈)：Blue 與 /B
Button_W(白燈)：white 與 /R
Button_off(紅燈)：Red 與 /o

![linkit](/img/Linkit/36.png)

#### LinkIt 7697  Wifi範例
本範例修改自LinkIt 7697的SimpleWebServerWifi範例(就是多加幾個字元而已)，重點段落
1. 連上指定網路

```c
while (status != WL_CONNECTED) {
    Serial.print("Attempting to connect to Network named: ");
    Serial.println(ssid);    
   // print the network name (SSID)
   // Connect to WPA/WPA2 network. Change this line if using open or WEP network:
    status = WiFi.begin(ssid, pass);
  }
server.begin();           // start the web server on port 80
  printWifiStatus();      // you're connected now, so print out the status
```

2. 於7697簡易網頁中網頁顯示訊息，您可在7697所產生的網頁上編寫簡易的html。在此使用超連結可以直接點選。當然目標是透過App Inventor來發送囉。
```c
client.print("Click <a href=\"/R\">here</a> to light red<br>");
client.print("Click <a href=\"/G\">here</a> to light green<br>");
client.print("Click <a href=\"/B\">here</a> to light blue<br>");
client.print("Click <a href=\"/W\">here</a> to light white<br>");
client.print("Click <a href=\"/o\">here</a> to light off<br>");
```

3. 檢查網址並呼叫自定義函式來控制LED。如果我們檢查到某次client request(手機或透過網頁點選)的結尾等於我們所指定的字元，就呼叫led()函式，並透過參數來決定哪一個顏色亮起。1,0,0就是紅色，0,0,1是藍色等。
在此我們並沒有調整每一種顏色的亮度，所以只有亮暗兩種狀態，可以思考一下如何透過這樣的架構把參數送進來給analogWrite()函式來調整RGB LED的亮度，例如(128, 130, 255)，這樣顏色的變化會更繽紛喔！
```c
// Check client request
if (currentLine.startsWith("GET /R")) {  // GET /R to light red
	led(1,0,0);     
}
//其餘省略
void led(int R, int G, int B) {
	digitalWrite(11, R);
	digitalWrite(9, G);
	digitalWrite(7, B);
}
```

**操作**

請先確認7697端程式已經執行，並開啟Serial Monitor來看7697的IP為何。將App Inventor中的ip變數值改好之後執行(由於本範例並非使用藍牙，所以模擬器也可執行)。
確認好IP之後，先開啟瀏覽器，所使用的裝置需與7697位於同一個網段之下才行喔，如以下的192.168.1.73。

![linkit](/img/Linkit/37.png)

![linkit](/img/Linkit/38.png)

開啟app吧，設定IP成功畫面如下圖左，點選各個按鈕可以看到畫面右上角的label會顯示對應的訊息。

![linkit](/img/Linkit/39.png)
![linkit](/img/Linkit/40.png)

Arduino 完整code

```c
/*
  WiFi 7697 LED control
  If the IP address of your shield is yourAddress:
  http://yourAddress/R to light red
  http://yourAddress/G to light green
  http://yourAddress/B to light blue
  http://yourAddress/W to light white
  http://yourAddress/o to turn off LED

  Circuit:
    LinkIt 7697 HDK
    RGB LED (common cathode) 
    R - LinkIt D11
    G - LinkIt D9
    B - LinkIt D7

  created 25 Nov 2012
  by Tom Igoe
  modified 3 Nov 2017
  by CAVEDU
*/
#include <LWiFi.h>

char ssid[] = "ssid";      //  your network SSID (name)
char pass[] = "pass";   // your network password
int keyIndex = 0;                 // your network key Index number (needed only for WEP)

int status = WL_IDLE_STATUS;
WiFiServer server(80);

void setup() {
  Serial.begin(9600);      // initialize serial communication
  pinMode(LED_BUILTIN, OUTPUT);      // set the LED pin mode
  pinMode(11, OUTPUT);  //R
  pinMode(9, OUTPUT);   //G
  pinMode(7, OUTPUT);   //B
  // attempt to connect to Wifi network:
  while (status != WL_CONNECTED) {
    Serial.print("Attempting to connect to Network named: ");
    Serial.println(ssid);                   // print the network name (SSID);

    // Connect to WPA/WPA2 network. Change this line if using open or WEP network:
    status = WiFi.begin(ssid, pass);
  }
  server.begin();                           // start the web server on port 80
  printWifiStatus();                        // you're connected now, so print out the status
}

void loop() {
  WiFiClient client = server.available();   // listen for incoming clients

  if (client) {                             // if you get a client,
    Serial.println("new client");           // print a message out the serial port
    String currentLine = "";                // make a String to hold incoming data from the client
    while (client.connected()) {            // loop while the client's connected
      if (client.available()) {             // if there's bytes to read from the client,
        char c = client.read();             // read a byte, then
        Serial.write(c);                    // print it out the serial monitor
        if (c == '\n') {                    // if the byte is a newline character

          // if the current line is blank, you got two newline characters in a row.
          // that's the end of the client HTTP request, so send a response:
          if (currentLine.length() == 0) {
            // HTTP headers always start with a response code (e.g. HTTP/1.1 200 OK)
            // and a content-type so the client knows what's coming, then a blank line:
            client.println("HTTP/1.1 200 OK");
            client.println("Content-type:text/html");
            client.println();
            // the content of the HTTP response follows the header:
            client.print("Click <a href=\"/R\">here</a> to light red<br>");
            client.print("Click <a href=\"/G\">here</a> to light green<br>");
            client.print("Click <a href=\"/B\">here</a> to light blue<br>");
            client.print("Click <a href=\"/W\">here</a> to light white<br>");
            client.print("Click <a href=\"/o\">here</a> to light off<br>");

            // The HTTP response ends with another blank line:
            client.println();
            // break out of the while loop:
            break;
          } else {    // if you got a newline, then clear currentLine:
            currentLine = "";
          }
        } else if (c != '\r') {  // if you got anything else but a carriage return character,
          currentLine += c;      // add it to the end of the currentLine
        }

        // Check client request
        if (currentLine.startsWith("GET /R")) {  // GET /F to light red
          led(1,0,0);     
        }
        if (currentLine.startsWith("GET /G")) {  // GET /G to light green
          led(0,1,0); 
        }
        if (currentLine.startsWith("GET /B")) {  // GET /B to light 
        	blue
          led(0,0,1);
        }
        if (currentLine.startsWith("GET /W")) {  // GET /W to light white
          led(1,1,1);
        }
        if (currentLine.startsWith("GET /O")) {  // GET /O to light off
          led(0,0,0);
        }
      }
    }
    // close the connection:
    client.stop();
    Serial.println("client disonnected");
  }
}

void printWifiStatus() {
  // print the SSID of the network you're attached to:
  Serial.print("SSID: ");
  Serial.println(WiFi.SSID());

  // print your WiFi shield's IP address:
  IPAddress ip = WiFi.localIP();
  Serial.print("IP Address: ");
  Serial.println(ip);

  // print the received signal strength:
  long rssi = WiFi.RSSI();
  Serial.print("signal strength (RSSI):");
  Serial.print(rssi);
  Serial.println(" dBm");
  // print where to go in a browser:
  Serial.print("To see this page in action, open a browser to http://");
  Serial.println(ip);
}

void led(int R, int G, int B) {
  digitalWrite(11, R);
  digitalWrite(9, G);
  digitalWrite(7, B);
}
```

### 資料來源
http://blog.cavedu.com/2018/06/11/linkit-7697-%E8%AA%8D%E8%AD%98linkit-7697%EF%BC%8C%E4%BD%A0%E6%9C%83%E9%9C%80%E8%A6%81%E9%80%99%E4%B8%80%E7%AF%87%EF%BC%81/
https://docs.labs.mediatek.com/linkit-7697-blocklyduino/linkit-7697-12880255.html
https://docs.labs.mediatek.com/linkit-7697-blocklyduino/%E5%AF%A6%E4%BD%9C%E7%AF%84%E4%BE%8B%E6%95%99%E5%AD%B8-12879630.html
https://oranwind.org/-mediatek-linkit-7697-ji-chu-jiao-xue/
http://blog.cavedu.com/2017/11/13/linkit-7697-wifi-led%E6%8E%A7%E5%88%B6/
