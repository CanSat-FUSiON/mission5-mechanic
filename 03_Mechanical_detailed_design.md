# 【3】Mechanic 詳細設計
基本設計で必要な各パラメータおよび使用する駆動系を決定した。それをもとに各部品形状や配置、材料の決定を行っていく。
## 部品選定

<div align="center">
<img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_1.png" alt="Assem" title="構造組立図">
<br>Fig3.1　構造組立図
</div>

<div align="center">

| 部品名 | 個数 | 材料 |
| :---- | ----- | :---- |
| ①メインプレート | 1 | アルミニウム（A5052） |
| ②シャフト（φ8） | 2 | アルミニウム（A2017） |
| ③モーターマウント | 2 | PLA |
| ④スペーサー | 10 | PLA |
| ⑤スタビライザー固定 | 1 | PLA |
| ⑥バッテリー支え | 1 | PLA |
| ⑦ベアリングマウント | 2 | TPU |
| ⑧ホイール | 2 | TPU |
| ⑨タイヤ | 2 | TPU |
| ⑩スタビライザー | 1 | コンベックステープ |
| ⑪ベアリング | 2 | 部品選定参照 |
| ⑫モーター | 2 | 部品選定参照 |
| ⑬バッテリー | 1 | 部品選定参照 |
| ⑭カップリング | 2 | 部品選定参照 |
| ⑮カメラ・カメラケース | 1 | PLA |
</div>

## 強度概算
  ### 着地衝撃値
  衝撃荷重の場合は荷重が作用する前後のエネルギー保存則から衝撃応力を求める。高度30mでの位置エネルギーは質量m、重力加速度g、高さhを用いて
  <div style="text-align: center;">
     mgh = 1[kg] × 9.8[m/s^2] × 30[m] = 294[J] 
  </div>  
  <br> 
  パラシュートがない場合はこの位置エネルギーがすべて運動エネルギーに変換される。また機体は緩衝材を搭載せず、変形によるひずみエネルギへの変換はないとする。0.1秒で衝撃荷重が加わったとすると  

  <br> 
  <div style="text-align: center;">
    FΔt=m√(2gh)
  </div>
  <div style="text-align: center;">
    F=1[kg]×√(2×9.8[m/s^2]×30[m])/0.1[s]=242[N] 
  </div>
  <br> 

  この荷重をパラシュートをつけることにより減速することで衝撃力を和らげる。
  大会要領から終端速度は4～6m/sにする必要がある。5m/sとすると衝撃力は50[N]である。
  衝撃力がかかる時間によって衝撃力の大きさは異なる。安全率をとり100[N]≒10Gで強度計算を行う。またこの値は大会経験者に評価していただき、10Gに耐える機体であれば大丈夫だという確認を行った。  
  <br> 
  ※パラシュートを大きくすれば、衝撃力は小さくなり耐荷重の小さな機体でよくなる。また質量が減ることは衝撃力がさらに小さくなることが運動量保存則からわかる。しかし落下に時間がかかるほど落下分散が大きくなり流され失格になる可能性もある。
  
  ### 材料の強度・材料の決定
  メインフレームにはアルミニウムA5052を用いた。板部品を用いることで軽量化を図る。板部品として広く流通しているのはA5052である。また板金加工が想定されたため加工難易度の低い材料を選定した。  
  シャフトは強度が必要なため、超ジュラルミンを選定した。入手が簡単な丸材かつ加工性の良いものを選定した。アルミ材はモノタロウで入手した。  
  強度はメインフレームとシャフトが負担するため、モータマウントやベアリングマウントは3Dプリンターで作成した。特にベアリングマウントはカップリングよりもタイヤ側が弾性変形して衝撃を吸収することを想定しTPUでの作成を行う。  
  以下に各材料のヤング率、降伏強度、引張強度を示す。ジュラルミンでも熱処理によって強度が全く異なるので材料特性はよく見て材を購入する。  

  <div align="center">

  | 材料 | 縦弾性率・曲げ弾性率[GPa] | 降伏強度[MPa] |　引張強度[Mpa]　|
  | :---- | :-----: | :-----: | :----: |
  | A5052 | 68 | 215 | 260 |
  | A2017 | 73 | 275 | 425 |
  | TPU | - | - | 35.0 |
  | PLA | 2.5 | - | 60.0 |
  </div>

  ### シャフト径
  シャフトは10Gがかかったときに塑性変形しなければよい。シャフト長は20mmでカップリングの端が固定端となっている場合、最大曲げ応力は固定端に生じる。シャフト径を8mmとすると
  <div style="text-align: center;">
    σ＝M/z= 98[N] × 20[mm] / (8/2[mm])=490[N]
  </div>
  <br>
  で破断する。シャフト径はベアリングの大きさの制限を受けており、ベアリングが外径16mmより大きくなると機体のタイヤの位置が下にずれ、反転時に基板が地面にこすれる可能性がある。シャフトは実際20mmも突き出ることはない。タイヤの突き出し部寸法が決まっていなくても、ベアリングマウントで支えることにより長くて10mm程度に抑えることができる。突き出し部が1/2になった場合、降伏荷重以下になるため破断しない。  
  シャフト部の設計はFig3.1のようになっている。アキシャル方向だけでなく接地させることでラジアル方向に荷重を逃がす。

  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_2.png" alt="シャフト部" title="シャフト部">
  <br>Fig3.2　シャフト部設計断面
  </div>

  ### 板厚の決定・ジェネレーティブデザインを利用した肉抜き
  板厚は板金加工がt2以上は難しいため、t2とした。この板厚で荷重条件を設定し、ジェネレーティブデザインを生成した。そこから肉抜きする箇所を決定した。
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_2_2.png" alt="ジェネレーティブデザイン" title="ジェネレーティブデザイン">
  <br>Fig3.2.2　ジェネレーティブデザイン
  </div>
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_2_3.png" alt="肉抜き" title="肉抜き">
  <br>Fig3.2.3　肉抜き
  </div>
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_2_4.png" alt="メインプレートFM" title="メインプレートFM">
  <br>Fig3.2.4　メインプレートFM
  </div>

## 強度解析
   ### 着地衝撃に耐えうることに対する解析  
  　機体重量1kgに対して10Gの荷重は、98Nの荷重に換算される。メッシュ数は564538要素で解析した。拘束条件はホイールの両端を固定する。荷重条件は構造に98Nの荷重をかけ、両タイヤから衝撃荷重がかかったことを再現する．
  図２に結果を示す。安全率は15以上であり、強度的に問題がないことが分かる。最大応力は13MPaであった。
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_1.png" alt="両輪着地衝撃" title="両輪着地衝撃">
  <br>Fig3.3.1　両輪着地衝撃 境界条件 
  </div>
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_2.png" alt="両輪着地衝撃" title="両輪着地衝撃">
  <br>Fig3.3.2　両輪着地衝撃
  </div>

  片輪から着地し、着地衝撃が機体片方に集中した場合の解析を行う。拘束条件を片輪完全拘束とし、荷重条件は拘束していない他端に衝撃荷重がかかったとする。
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_3.png" alt="片輪着地衝撃" title="片輪着地衝撃">
  <br>Fig3.3.3　片輪着地衝撃 境界条件 
  </div>
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_4.png" alt="片輪着地衝撃" title="片輪着地衝撃">
  <br>Fig3.3.4　片輪着地衝撃
  </div>  
  図3に結果を示す。安全率は3.226となり強度は十分である。最大応力は123MPa であった．
  軸方向横向きに落下した場合を想定し解析を行う。拘束、荷重条件は図4に示す。図5に結果を示す。最小安全率は2.09でメインプレートの中心付近の応力集中箇所であったが2を超えているため強度的に問題がないと判断した．

  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_5.png" alt="軸方向着地衝撃" title="軸方向着地衝撃">
  <br>Fig3.3.5　軸方向着地衝撃 境界条件 
  </div>
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_6.png" alt="軸方向着地衝撃" title="軸方向着地衝撃">
  <br>Fig3.3.6　軸方向着地衝撃
  </div> 
  

   ### シャフト強度評価
  シャフトについてねじり剛性と曲げ剛性を評価する．まずねじり剛性についてモーターからの伝達トルクを受けたときに破断しないかを検証する．モーターからのトルクは計算した値よりも少し大きい200ｍNmを用いて解析した．安全率は15以上あるため強度的に問題がないことが分かる．  
  曲げ剛性は片輪に98Nの荷重がかかった場合を想定して解析を行った．安全率は最低6.996で強度的に問題がないことが分かる．   
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_8.png" alt="シャフト強度解析" title="シャフト強度解析">
  <br>Fig3.3.8　シャフト強度解析
  </div>  
  これらの着地衝撃に対する強度は実際に橋の上からの投下試験を行うことで妥当性を検証した．実際の試験結果は「04_Mechanic_evaluation 実地試験結果  構造の評価」に示す．

  ### 固有振動数解析  
  ロケット内では15Gの荷重がかかった状態で振動が加わるため、余荷重を設定し周波数解析を行う．0〜3000Hzの共振点を求めると同時に、どのような変形モードがあるか検証を行う．  
  以下の点が共振点であった．またその変形モードを下に示す．  
  共振点：248.108Hz 378.97Hz 410.799Hz 496.305Hz 519.723Hz 675.43Hz 761.471Hz 820.09Hz 910.266Hz 1040.916Hz 1071.339Hz 1181.543Hz 1223.802Hz 1340.057Hz 1396.843Hz 1529.286Hz 1581.155Hz 1617.192Hz 1631.88Hz 1647.52Hz 1799.533Hz 1940.615Hz 2202.89Hz 2469.321Hz 2490.621Hz 2528.354Hz 2652.229Hz 2859.15Hz 2859.418Hz
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_9_1.png" alt="1" title="1">

  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_9_2.png" alt="2" title="2">

  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_3_9_3.png" alt="3" title="3">
  <br>Fig3.3.9　変形モード
  </div> 

## パラシュート・エンベロープ
### パラシュート
#### 要求
着地衝撃が10G以下になるように終端速度を計算する。1kgの物体が着地後0.05sで0になるとすると、運動量と力積の関係から約5m/sと計算できる。大会規定でも種子島ロケットコンテストでは終端速度4〜6m/s、ARLISSでは5m/s以下になるように設計する必要がある。  
パラシュートの抗力係数は1.75として計算する。次のページを参考にした。  
[http://modelrocketseisaku.cocolog-nifty.com/blog/2010/12/post-3b40.html]  
抗力と重力がつりあうように計算して（空気の密度は1.2として計算する）  

$mg=\frac{1}{2}C_DU^2S$  

より代表面積S＝0.373ｍ^2である．これは約0.345mの半径をもつ円に相当する．
パラコードはパラフォイルの直径と同じ長さに設定した．
#### 設計
パラフォイルが落下する時に垂直方向投影面積が0.373m^2以上にする必要がある. 作図を行い落下時に投影面積直径が400mmになるように設計した．
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_4_1.png" alt="パラ正面図" title="パラ正面図">
  <br>Fig3.4.1　パラシュート　正面図
  </div>  

  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_4_2.png" alt="パラ平面図" title="パラ平面図">
  <br>Fig3.4.2　パラシュート　平面図
  </div>  

#### 製作
パラシュートの製作工程は過去の資料を参考にして作成する。
  1. 青線の通りに布を切り出す。
  2. 黒線に一致するように正六角形の端の長方形を二回折り返して縫う。
  3. 中心に空いている穴を切り落とす。
  4. 正六角形の各頂点にハトメにあったサイズの穴(8mm)を開け、ハトメで補強する。

#### 布・紐の選定
　パラシュートの布は視認性の高い蛍光色のものを選定する。今回は実績のある赤色のパラシュートを選定する。軽量で破れにくいことからテントなどのアウトドア用用品に用いられるリップストップナイロンを選定する。  
　紐の選定では今回機体重量が大きくなるため他はできるだけ軽くするためにテグスを用いる。種子島ロケットコンテストでは投下後3秒後（10mほど落下した後にパラシュートを展開すると仮定する）に30m/sのCanSatがパラシュートの展開により0.1秒で5m/sへ減速する時の衝撃力は力積と運動量の関係から60Nの開傘衝撃が加わる。開傘衝撃に耐えられるように10号のテグス（引張強度20kg）3本をより合わせて使用する（安全率10）。  
　結び目や固定箇所での強度を確認するために実際に製作し想定される荷重の重りをぶら下げることで試験する。

#### 紐の結び方・パラシュートのたたみ方
紐の結び方
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_4_3.png" alt="ひも" title="ひも">
  <br>Fig3.4.3　パラシュート　紐のむずび方
  </div> 

紐のまとめ方

  1. パラシュートのテグスを6本まとめる.
  2. 8の字結びしてガムテープで固定する.

パラシュートのたたみ方
  1. パラコードが集まるように半分に4回折りたたむ
  2. 半分に折りたたんで、その上に紐を折り曲げて置く
  3. コードを一緒に包むようにして、もう一度半分に折りたたむ
  4. さらに折りたたんで一回巻いて完成

  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_4_4.png" alt="まとめかた" title="まとめかた">
  <br>Fig3.4.4　パラシュート　まとめ方
  </div> 

### エンベロープ
  #### 要求
  * 機体に直接パラシュートをつながずエンベロープで包んだ状態でパラシュートにつなげる。
  * 着地時にエンベロープが展開されるようにコンベックステープをエンベロープに配置する．
  * エンベロープ内で滑らないように、エンベロープ表面の摩擦係数を大きくする。
  * フライトピンをつけられる構造になっている。
  * エンベロープとパラシュートの接続部にコンベックステープをつけることで、必ず落下後機体が走行開始する反対側に、パラシュートが落ちるようにコンベックステープを固定する．
  #### 設計
  * 固定用の溶断するテグス紐はパラシュートと同様の設計で行う。
  * パラシュートとエンベロープを固定する紐は直径3ｍｍのナイロン紐を用いる。
  * エンベロープの素材にはPPクラフトシートを用い、滑り止めに紙やすりを用いる。
  * 固定用のひもが切れたときにエンベロープが展開するようにコンベックステープを挟んでおく。
  * 不必要な電磁的干渉を防ぐため、エンベロープにアルミホイルテープを貼り電磁遮蔽を行う。
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_4_5.png" alt="エンベロープ" title="エンベロープ">
  <br>Fig3.4.5 エンベロープ
  </div> 
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_4_6.png" alt="エンベロープ落下図" title="エンベロープ落下図">
  <br>Fig3.4.6　エンベロープ落下図
  </div> 


  #### 紐の結び方
  <div align="center">
  <img src="https://github.com/CanSat-FUSiON/mission5-mechanic/blob/main/figure/DD_3_4_7.png" alt="エンベロープひも" title="エンベロープ紐">
  <br>Fig3.4.7　エンベロープ　紐のむずび方
  </div> 

