## ESP32
### 基本介紹
![](https://i.imgur.com/2AOzRsr.jpg)

ESP32是由樂鑫資訊科技開發的為控制器，不僅內建有WiFi及低功率藍牙BLE，可用腳位也擴增到約26根，大部分腳位同時支援類比及數位，內建霍爾、溫度、觸控感測器，主頻高達260mHz的雙核心CPU，傳輸界面SPI、I2C、UART等強大的功能，且ESP32與Arduino UNO所有週邊感測元件完全相容，可以無痛直接升級ESP32，不但可以演練所有目前現有UNO課程，而且比起ESP8266多了藍牙及更多數位和類比腳位，使ESP32能完成更多的應用專題，再加上相當有競爭力的價格，讓ESP32成為IoT課程最佳的教學工具。


而ESP32有很多種版本如下：
1. NodeMCU-32S：保留完整38根腳位，且有預留外接天線
2. DOIT DEVKIT：價格便宜，但缺少5V輸出
3. TTGO ESP32：附帶18650電池座，搭配深度睡眠(deepsleep)，一顆電池可用一個月以上
4. Lolin ESP32：附帶Oled顯示器，可快速開發萬年曆、微型氣象站等顯示裝置
5. ESP32-CAM：附帶相機及SD卡槽，可開發具AI影像辨識裝置
6. HaloCode光環板：附帶麥克風及光環LED燈，可開發語音辨識並透過LED互動
7. WeMos ESP32 mini：縮小尺寸至1/2左右，可開發穿戴裝置
8. HELTEC WiFi LoRa 32：擁有超大32M記憶體，內建OLED及長距離Lora通訊


### 硬體介紹
#### NodeMCU-32S腳位圖
* ![](https://i.imgur.com/99S7Jr9.png)
    * 18* Analog-to-Digital：可接類比或數位感測（粉紅色標示）
    * 3* SPI interfaces(MOSI, MISO, SCK, SS)：高速資料傳輸 SD card, TFT, RFID（藍色標示）
    * 3* UART interfaces：藍芽、相機(不限腳位編號)
    * 2* I2C interfaces(SDA,SCL) and I2S interfaces：LCD、氣壓、陀螺儀（GPIO 21,22）
    * 16* PWM output channels：數位輸出也可類比輸出（不限定腳位編號，但需要宣告channel）
    * 2* Digital-to-Analog Converters (DAC)
    * 10* Capacitive sensing GPIOs：提供觸控電容（棕色標示）
* GPIO
    * GPIO 34, 35, 36, 39：Input only（不能作為輸出腳位）
    * GPIO 0, 6, 7, 8, 9, 10, 11：系統用，勿使用（淺灰色標示）
    * GPIO 18：重開機



### 開發環境介紹

#### 1. 前置準備：
❖ 準備一片 ESP32 開發板
❖ 準備一條 Micro USB Cable
❖ 準備一台電腦

#### 2. 開發板與電腦連接圖
將 Micro USB 端接 ESP32，另一端接電腦的 USB 插槽
![](https://i.imgur.com/KwQUbJG.jpg)

#### 3. 安裝 Arduino IDE
需要開發環境、編譯器、連結器、開發工具鏈、燒錄程式、板子與電腦連接所需要的驅動程式、等等等等，這些通通都已經準備好、打包好了，到Arduino官方網站的[下載頁面](http://arduino.cc/en/Main/Software)即可下載，可在Windows、Mac OS X、Linux上運行。 

![](https://i.imgur.com/TTIAuVK.jpg)


#### 4. 安裝 CP210x USB to UART 驅動程式
❖ 開啟電腦的瀏覽器並輸入下方的 URL：
https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers
❖ 依自己的作業系統來選擇相對應的安裝檔並安裝完成
（參考資料：https://techexplorations.com/guides/esp32/begin/cp21xxx/ ）
![](https://i.imgur.com/cIKrWPq.png)


#### 5. Arduino IDE設定
❖ 檔案 ➙ 偏好設定
![](https://i.imgur.com/nwm6NE0.png)


❖ 在額外的開發板管理員網址輸入以下 URL 再點選確定（如果有別的網址，請用’,’隔開）：https://dl.espressif.com/dl/package_esp32_index.json
![](https://i.imgur.com/WjOItd5.png)

❖ 點選工具 ➙ 開發板 ➙ 開發板管理員
![](https://i.imgur.com/7M2OrhV.jpg)

❖ 右上搜尋欄位輸入 esp32並點選安裝
![](https://i.imgur.com/A7DtjmV.png)

❖ 點選工具 ➙ 開發板  ➙ 選擇 NodeMCU-32S
![](https://i.imgur.com/Afq54fH.jpg)

❖ 點選工具 ➙ 序列埠選擇在裝置管理員中所看到的連接埠號
![](https://i.imgur.com/C4YJakE.png)
![](https://i.imgur.com/liDVhC5.png)

即可完成設定


### 範例
ESP32的語法幾乎與Arduino UNO相同 ，因此這裡就先用簡單的HelloWorld當範例。
```C
void setup ( ) {
     Serial.begin(115200);//啟動序列通訊鮑率115200
}
void loop() {
Serial.println(“HelloWord”);
delay(1000);
}
```
按下上傳
![](https://i.imgur.com/w3OKEFB.png)

上傳完畢
![](https://i.imgur.com/icSspLw.png)

開啟序列埠監控視窗
![](https://i.imgur.com/2Cv1wa8.png)

觀看執行結果（記得要將鮑率調成115200，否則會出現亂碼）
![](https://i.imgur.com/sHipbmX.png)

### 資料來源
https://youyouyou.pixnet.net/blog/post/119410732
https://techexplorations.com/guides/esp32/begin/cp21xxx/
https://makerpro.cc/2020/06/esp32-review-and-why-recommend-nodemcu-32s/
