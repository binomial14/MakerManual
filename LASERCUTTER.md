# LASER CUTTER


## 機台介紹

雷射切割機主要用來 ==平面切割== 和 ==平面雕刻== 各式各樣的 ==非金屬材質==，雖然雷射切割機只能對材料進行2D的處理，但因其工作面積和速度遠較3D列印機來的寬廣和快速，因此常常被用於製作外殼和大型部件以及雕刻文字圖像，

* 型號：銘晟數控MS960DS100W雷射機
* 工作面積：**900×600mm**
* 切割厚度：0-15mm（視材料而定）
* 支援軟體：CorelDraw/AutoCAD/Illustrator軟體
* 最小成型文字：漢字2mm,英文1mm
* 適合材料：壓克力，pvc材料、皮革、布料、橡膠、塑膠、木製品、紙製品、石製品等<font color=red>**非金屬材料**</font>。

## 如何使用？

### 電腦繪圖完畢後，你應該...
* 清除重複線條並將聚合線分割成各個線段
	> <font size=2>如果你使用的軟體是 AutoCAD，可以使用以下指令：
	> `EXPLODE`：把聚合線拆分成線段
	> `TXTEXP`：把文字拆分成線段</font>
* 確認軟體上的長度單位是公分(cm)還是毫米(mm)
	> <font size=2>AutoCAD 中的長度通常是沒有標示單位的，需要使用者自己去定義</font>
* 確認檔案的排版沒有超出雷射切割的範圍(900x600mm)或是待切板材的形狀
	>
* **將檔案輸出為`.dxf`檔案**，並存入隨身碟
	> <font size=2>若是無法輸出`.dxf`，也可以改輸出`.dwg`檔，但是會需要花額外的時間進行轉檔</font>


### 當以上事項都完成後，請帶著您的隨身碟找工作人員進行下列步驟：
* 將您的`.dxf`匯入雷切機專用的軟體
* 向工作人員提供下列資訊：
    * 圖檔的單位是 ==公分(cm)== 還是 ==毫米(mm)==
        > <font size=2></font>
	* 您想要使用何種材料？
		> <font size=2>e.g. 5mm 壓克力板、3mm 密迪版 ...</font>
	* 圖檔中哪些部份需要==切割==或是==雕刻==？
        > <font size=2>雷切機專用軟體會以不同顏色顯示不同切割參數，您可以以此確認工作人員所標示的部分是否正確無誤，如下圖中<font color="#3399FF">淺藍色</font>是要雕刻的部分，<font color=black>黑色</font>則是要切割的部分</font>
        > ![](https://i.imgur.com/QQNgB8Y.png)

* 之後工作人員會將輸出一個`.out`檔並前往雷切機進行操作

### 當工作人員在設定雷切機時，您應該留意：
* 工作人員是否有確實==進行對焦==
	> <font size=2>工作人員會在板材和雷射頭中間放置一塊白色壓克力，並調整電動升降台使板材和雷射頭的距離約略等於那塊壓克力的寬度。由於升降台不一定完全水平，因此應該要採用最高的一端進行對焦，使得切割範圍內的板材都保持比焦點略遠的距離。</font>
* 工作人員是否有==準確定位==
	> <font size=2>若您的切割範圍較大，可能很容易超出範圍，請務必要使用"**邊框**"功能確認切割範圍</font>

**切割完成後**
* 清點您的切割成品
* 清除切剩下的碎屑或廢料