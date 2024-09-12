# 【4】Mechanic 実地試験・評価
## 実地試験結果

### 構造の評価

　落下後の機体の様子を図6.1に示す．衝撃にカップリングが耐えられず塑性変形した．また機体のフレームが基板を固定している部分で曲がり塑性変形した．  
　4章で示した解析結果からは強度は十分であったが実際は変形が起きたのは、パラシュート展開から落下までに終端速度に達していないからだと考えられる．特にカップリングの剛性に関しては考慮し忘れていたため、カップリングを大きな偏芯が許容され高い耐久力をもつオルダム型に選定し直した．  
　シャフトの変形はなかった（1/10mmスケールで測定できる範囲では変形していない）．  
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_1_1.png" >
  <br>fig4.1.1　落下後の機体
  </div> 

### エンベロープの展開

[0120\_env2.mp4](https://drive.google.com/file/d/1kMq5PLwU9nytJApmHYFAVfuBkZm\_2I6-/view?usp=sharing)  
エンベロープは図5.2の黄色の枠線で示すニクロム線に赤線で示すようにテグス(φ0.52mm)を通しエンベロープの穴を通しながら一周させて固定する．ニクロム線加熱後から4秒〜5秒以内に溶断して展開した．室内での展開と落下試験で落下してからの展開にはこの溶断の速度は変わらなかった．  
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_1_2.png" >
  </div>  
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_1_3.png" >
  <br>fig4.2.2　エンベロープ展開の様子
  </div>

### パラシュートの落下

[MOV\_2816.mp4](https://drive.google.com/file/d/131eMZk6FObMK5rk8qRvGJqnPAn8BNsde/view?usp=sharing)  
[MOV\_2818.mp4](https://drive.google.com/file/d/133eYOmaVmd3esqBcIKSiWl70FeCUUKgp/view?usp=sharing)  
[MOV\_2822.mp4](https://drive.google.com/file/d/13Qpy8ct8myyD8G4hz--Agu5oOBJvdTxX/view?usp=sharing)  
[MOV\_2823.mp4](https://drive.google.com/file/d/13T31pTfu3c1jfJRGJehD0UXgDUgj-NMv/view?usp=sharing)  
　パラシュートに機体を載せて投下する試験を3回行った．その様子を図6.3、図6.4、図6.5に示す．投下１回目2回目に関しては機体が反転して着地しエンベロープは展開したが機体が起き上がることができず走り出すことができなかった.3回目の投下では正常に走り出すことができた．反転から復帰できないのはバッテリが重く重心がスタビライザー付近に偏っているためだと考え九州での試験ではバッテリーを小さくし試験を行う（選定し直したバッテリーは3章で示したものを使う）．<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_3_1.png" >
<br>fig4.3.1　投下1回目 
</div>
<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_3_2.png" >
<br>fig4.3.2　投下2回目 
</div>
<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_3_3.png" >
<br>fig4.3.3　投下3回目 
</div>

### 6.4　スタックからの脱出

[PXL\_20240128\_073856210.TS.mp4](https://drive.google.com/file/d/17hsitapMjb5XOyRKD9sw7jLxDtN3EbKp/view?usp=sharing)  
走行時衝撃がかかった時にモータードライバーの過電流保護が働きモーターがすぐに止まってしまうという問題があった．この衝撃はタイヤの凸凹が大きい時にも作用し走行試験が効率よく行えなかったため凸凹の小さいタイヤで走行試験を行った．草 藁の多いところでは小さな窪みでもタイヤが滑ってしまうという事象が何度か発生した．この時にスタックを抜け出すことができたパターンを示す．  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_4_1.png" >
<br>fig4.4.1　草で滑りスタックした様子 
</div>

機体を旋回させるとスタックから抜け出すことができた．この方法はモータードライバーの保護回路が働いたときも旋回させ復帰させることができるため有効な動作パターンだと考え、プログラム上でスタックを検知したときは機体を旋回させることで対処しようと考えている．この実験では3回旋回し脱出した．  
[PXL\_20240128\_073912910.TS.mp4](https://drive.google.com/file/d/1RMfBfwh61DP28PKBsh-Q5aXjauIWONzK/view?usp=sharing)  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_4_2.png" >
<br>fig4.4.2　機体を旋回させてスタックから脱出する様子  
</div>   

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_4_3.png" >
<br>fig4.4.3　再び機体が走り出した様子  
</div>  
 
タイヤの溝が小さいと草むらで滑って前進できない．実験に用いるタイヤで凸凹が最も小さい(タイヤの面から1mm突き出した凸凹)では草地を走行させることはできないと判断した．[PXL\_20240128\_062404619.TS.mp4](https://drive.google.com/file/d/1VFYi-\_ujCeSU71UF3o4uD5P4YVTCvlrb/view?usp=sharing)  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_4_4.png" >
<br>fig4.4.4　機体が滑って進まない様子  
</div>    

タイヤの溝を大きくすることで滑りやすい草むらで前進できるようになる．タイヤの凸凹の大きさはタイヤの面から10mm突き出した形状である．  
[PXL\_20240128\_062944428.TS.mp4](https://drive.google.com/file/d/1\_FQ5aTl-J1pVCEfuJefQtBaKdjyPMR8m/view?usp=sharing)  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_4_5.png">
<br>fig4.4.5　機体が走行する様子 
</div>

### 6.5　GNSS誘導により目的地まで誘導する様子

GNSS誘導により任意の地点に誘導できるのかを試験した．Googlemapの座標からポイントを打ち誘導を行ったところポイントから半径1.5mの範囲内でとどまったため誘導できていると判断した．GNSS誘導では指定した座標から直径3mの円内まで誘導できるとしてシーケンスを進めるうえでの参考値とする．  
[PXL\_20240128\_025743076.TS.mp4](https://drive.google.com/file/d/11TDuK5wOjCwdr3jrz1qZymf1qrL65QQO/view?usp=sharing)  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_5_1.png">
<br>fig4.5.1　前進10秒する様子 
</div> 

[PXL\_20240128\_020700896.TS.mp4](https://drive.google.com/file/d/1lNtXwuQQH1w\_UuVDlj28n8A6umG1THS0/view?usp=sharing)  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_5_2.png">
<br>fig4.5.2　任意の点から機体をGNSS誘導する様子 
</div> 
  
[PXL\_20240128\_031420519.TS.mp4](https://drive.google.com/file/d/12IgKIemUGkVymzXxvQjd1x5hmrnn6yCw/view?usp=sharing)  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_5_3.png">
<br>fig4.5.3　エンベロープ展開から目的地に到着し旋回する様子（2回目の走行試験） 
</div>  

### 6.6　緩やかな坂であれば上ることができる

河川敷と道路をつなぐ土手部分の傾斜が約15°であったため上ることができるか試験した．前進のみするプログラムであったが30cm程のぼったあとで横にそれて下ってしまったため15°の坂が長く続くようでは上ることはできないと判断した．しかしながら種子島ロケットコンテストの会場では平地が想定され長い坂はないと予想し、この機体性能であれば十分に競技を実施できると判断した．  
[PXL\_20240128\_074309082.TS.mp4](https://drive.google.com/file/d/1Tkze9NP74BlSnQs3WAQbpMH1YVJq\_EDH/view?usp=sharing)  

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/Eva_4_6_1.png">
<br>fig4.6.1　坂の登坂の様子 
</div>   
