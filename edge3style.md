# BLD解説
<div style="text-align: center;">Dedicated to ミッシェル・K・Davis...</div>

本解説は，Speedcubing Advent Calendar 2014 の20日目の記事ですが，WRCCの皆さんには専門必修です．
19日目は[CubeVoyage](https://twitter.com/CubeVoyage)さんの「[アドバイスシリーズ「○○秒が切れない人へのアドバイス」](http://speed-cubing.appspot.com/advice.html)」でした．

## 目次
+ [DFバッファ解説](#sec1)
+ [DF-FU インターチェンジ](#sec2)
+ [DF-BD インターチェンジ](#sec3)
+ [DF-BU インターチェンジ](#sec4)
+ [発展(M2法の範疇からは外れてしまうモノたち)](#sec5)
+ [おわりに &amp; 謝辞](#sec6)
+ [オマケ (M列以外だけどよく使うエッジコミュテータたち)](#sec7)


## &dagger;DFバッファ解説&dagger; <a id="sec1"></a>
ここでは，目隠し競技のエッジ解法においてM2法を使用している方を対象に，3-styleへと気軽に移行できるようにすることを目的としている．M2法で出てくるとどうしても手数が多くなってしまうM列手順 (ここで対象となる **fu*ck** なM列は FU, BU, BD) に関しては，すぐにでも3-cycle手順に変更することをお勧めする (これらが関わる手順の総数は 114通り[森川](https://www.worldcubeassociation.org/results/p.php?i=2011MORI01)調べ) ．M2法の原理を理解していれば，いずれの手順に関してもその場ですぐに生成することが可能になるであろう．また，エッジはミラー手順が使えるのでとても楽である．

そこでまずは，M2法で出てくるものを例にとり，エッジコミュテータを導入しよう．これ以降登場するコミュテータの表記に関しては，[こちら](http://wrcc.main.jp/commentary/corner3style/0)を参考にしてもらいたい.

**本記事で登場する図において，<font color="#ff0000">赤色</font>が<font color="#ff0000"><ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby></font>なパーツで，<font color="#00ff00">緑色</font>が<font color="#00ff00">インサートすべき</font>パーツとなっている．**
### 例．DF &rarr; UB &rarr; FR &rarr; DF
![DF-UB-FR](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-UB-FR.png)

M2法でこれが出てきた場合，すぐさま 
```
M2 U R U' M2 U R' U' 
```
を回すと思う．これが最も基本的なコミュテータ (ピュアコミュテータ)である．M2法の場合，UBが絡むサイクルの大部分はこのようなピュアコミュテータになっている．

コミュテータは，インターチェンジとインサートと呼ばれる2パートから成り立っている．インターチェンジとは，
```M2 U R U' M2 U R' U'```
における ```M2``` (=A と呼ぶ) のことであり，インサートとは，```U R U'``` (=B と呼ぶ) のことである．これによりコミュテータは，```A B A' B'``` の形をしていることがわかる．
この観点で先ほどの手順を眺めると「DF は UB と A でインターチェンジ可能な位置関係にあり(以後 <ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby> とかく)，B により FR を UB へインサートする．あとは A' B' のように回す」という風になる．

ここで注目すべきことは，M2法では必ず**DF と UB が M2 によって<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>になっており，何かしらのパーツを UB へインサート**しているということである．
**何かしらのパーツを UB へインサートするための手順**はよくご存知のものであると思われるが，一応下にまとめておく．ただし，今回の解説で必要となるインサート手順のみに留めておく．

| Edge |   Insert  | (Insert)' |
|:----:|:---------:|:---------:|
|  UR  | R' U R U' | U R' U' R |
|  UL  | L U' L' U | U' L U L' |
|  FR  |   U R U'  |   U R' U  |
|  FL  |  U' L' U  |   U' L U  |
|  LF  |  B L2 B'  |   B L2 B' |
|  LD  |  B L B'   |   B L' B' |
|  LB  | L B L' B' | B L B' L' |
|  LU  |  B L' B'  |   B L B'  | 
|  BL  |  U' L U   |  U' L' U  |
|  BR  |  U R' U'  |   U R U'  | 
|  RB  | R' B' R B | B' R' B R |
|  RD  |  B' R' B  |   B' R B  |
|  RF  |  B' R2 B  |  B' R2 B  | 
|  RU  |  B' R B   |  B' R' B  | 
|  DR  |  U R2 U'  |  U R2 U'  |
|  DL  |  U' L2 U  |  U' L2 U  |

M2法をマスターしている方ならば，この表のインサートとその逆手順は手が覚えていることだろう．
#### <a name="fenced-code-block">次からはいよいよ，このM2法の原理を応用して憎きM列手順へ逆襲を始める．</a>
この解説で扱うエッジコミュテータを手っ取り早くモノにするためには，インターチェンジが何であるかを意識し，**分類された**インサートのパターンに最大限注意しながら，実際にキューブを回すことである．**頭フルスロットル!!!!**
<div style="text-align: center;"> <p><font size="6" color="#000000">**ヽ( ▼∀▼)ﾉ ﾌｫｰ!!**</font></p> </div>


## &dagger;DF-FU インターチェンジ&dagger;<a id="sec2"></a>
さて，先ほどまでは DF と UB が ```M2``` により<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>であった訳だが，DF が ```M'``` により FU と<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>なことは明らかだろう．そこで，**何かしらのパーツを FU へインサート** すればよいのだとわかるので，インサート手順を考える．

### 例．DF &rarr; FU &rarr; UR
![DF-FU-UR](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-FU-UR.png)

```x``` で持ち替えをすると，FU と UR の位置が，それぞれM2法での UB と BR の位置と相対的に同じになる．従って，```U R' U'``` でインサートすればよいことがわかる．結果として，

```
[x : M', U R' U']
```

が得られる．インターチェンジとインサートを行う順序を逆にした

```
[x : U R' U', M']
```

を回すと，DF &rarr; UR &rarr; FU のサイクルとなる．

このパターンに帰着されるものを次の表にまとめておく．

|                 Cycle                  |   Insert (to FU)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; FU &rarr; UR         |      x U R' U'    |   [x : M', U R' U']   | 
|         DF &rarr; FU &rarr; UL         |      x U' L U     |   [x : M', U' L U]    |
|         DF &rarr; FU &rarr; FR         |    x R' U R U'    |   [x : M', R' U R U'] |
|         DF &rarr; FU &rarr; FL         |    x L U' L' U    |   [x : M', L U' L' U] |
|         DF &rarr; FU &rarr; DR         |     x U R U'      |   [x : M', U R U']    |
|         DF &rarr; FU &rarr; DL         |     x U' L' U     |   [x : M', U' L' U]   |
|         DF &rarr; FU &rarr; BR         |     x U R2 U'     |   [x : M', U R2 U']   |
|         DF &rarr; FU &rarr; BL         |     x U' L2 U     |   [x : M', U' L2 U]   |

この表では，FU へインサートすべきパーツが U, F, B, D面(M列を除く) にあるときの 8 &times; 2 = 16 通りをカバーできる．

### 例．DF &rarr; FU &rarr; RF
![DF-FU-RF](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-FU-RF.png)

RF を FU へインサートするには，```U' R U``` と回せばよい (x 持ち替えをすれば，M2法での RU インサートと同じ) ．

```
[M', U' R U]
```

を得る．
一つ前の例では ```x``` 持ち替えをしたが，ここでは持ち替えをしない方が回しやすいので，どうすれば FU へインサートできるのかを次の表を参考にして考えてもらいたい．おそらくすぐに理解できると思われるので，すぐにものにできるだろう．

|                 Cycle                  |   Insert (to FU)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; FU &rarr; RB         |       U' R' U     |     [M', U' R' U]     | 
|         DF &rarr; FU &rarr; RD         |       U' R2 U     |     [M', U' R2 U]     |
|         DF &rarr; FU &rarr; RF         |       U' R U      |     [M', U' R U]      |
|         DF &rarr; FU &rarr; RU         |      R U' R' U    |     [M', R U' R' U]   |
|         DF &rarr; FU &rarr; LF         |       U L' U'     |     [M', U L' U']     |
|         DF &rarr; FU &rarr; LD         |       U L2 U'     |     [M', U L2 U']     |
|         DF &rarr; FU &rarr; LB         |       U L U'      |     [M', U L U']      |
|         DF &rarr; FU &rarr; LU         |      L' U L U'    |     [M', L' U L U']   |

**注意**．DF-FU-RU, DF-FU-LU のサイクルに関しては，M2法のときには使っていないインサートをしているが，回しやすいのですぐに覚えられるだろう．

```
(R U' R' U)' = U' R U R'
```

```
(L' U L U')' = U L' U' L
```

この表では，FU へインサートすべきパーツが R, L面(M列を除く)にあるときの 8 &times; 2 = 16 通りをカバーできる．

### DF-FU-UB パターン
これは少しだけむつかしい．まず ```D``` で DF を DR へセットアップし，FU が ```M'``` により UB と<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>と見る．そして DR を ```U R2 U'``` で UB へインサートすればOK．

![DF-FU-UB-1](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-FU-UB-1.png)

|                 Cycle                  |   Insert (to UB)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; FU &rarr; UB         |    (D) U R2 U'    |    [D : M', U R2 U']  | 
|         DF &rarr; FU &rarr; BD         |    (x D) U R2 U'  |  [x D : M', U R2 U']  | 
これは，2 &times; 2 = 4 通りカバー．

DF-FU-BD はアジア大会2014で**[WRCCの森川くん](https://www.worldcubeassociation.org/results/p.php?i=2011MORI01)**
から教えて貰った手順．

## &dagger;DF-BD インターチェンジ&dagger;<a id="sec3"></a>
ここでは，DF と BD が ```M``` により<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>であることを利用して，コミュテータを生成していく．

### DF-BD-UR パターン
![DF-BD-UR](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BD-UR.png)

```x'``` 持ち替えをすると考えやすい．UR を BD へインサートするには，```x'``` で持ち替えてから ```U R U'``` を回せばよい．
結果として，

```
[x' : M, U R U']
```

を得る．ちなみにこの DF-BD-UR cycleはTwitterで**[某3BLD圧倒的日本記録保持者たくくんさん](https://www.worldcubeassociation.org/results/p.php?i=2012YANA01)**に教えて貰った手順である (神々しい)．
ここでも，インサートの仕方をよく観察して，ものにしてもらいたい．

|                 Cycle                  |   Insert (to BD)  |       Execution         |
|:--------------------------------------:|:-----------------:|:-----------------------:|
|         DF &rarr; BD &rarr; UR         |    x' U R U'      |   [x' : M, U R U']      | 
|         DF &rarr; BD &rarr; FR         |    x' U R2 U'     |   [x' : M, U R2 U']     |
|         DF &rarr; BD &rarr; DR         |    x' U R' U'     |   [x' : M, U R' U']     |
|         DF &rarr; BD &rarr; BR         |   x' R' U R U'    |   [x' : M, R' U R U']   |
|         DF &rarr; BD &rarr; UL         |    x' U' L' U     |   [x' : M, U' L' U]     |
|         DF &rarr; BD &rarr; FL         |    x' U' L2 U     |   [x' : M, U' L2 U]     |
|         DF &rarr; BD &rarr; DL         |    x' U' L U      |   [x' : M, U' L U]      |
|         DF &rarr; BD &rarr; BL         |   x' L U' L' U    |   [x' : M, L U' L' U]   |

この表では，BD へインサートすべきパーツが U, F, D, B面(M列を除く) にあるときの 8 &times; 2 = 16 通りをカバーできる．


### DF-BD-UB パターン
これは ```U``` で上の DF-BD-UR の形にセットアップすれば**勝確**である．

|                 Cycle                  |   Insert (to BD)  |       Execution         |
|:--------------------------------------:|:-----------------:|:-----------------------:|
|         DF &rarr; BD &rarr; UB         |   (U x') U R U'   |   [U x' : M, U R U']    | 
|         DF &rarr; BD &rarr; UF         |   (U x') U' L' U' |   [U x' : M, U' L' U]   | 
2 &times; 2 = 4 通りカバーできる．

### DF-BD-RU パターン
![DF-BD-RU](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BD-RU.png)

この場合は ```x``` 持ち替えをするとわかりやすい．ただし，一つ注意をしておくと，ここでは M2法における UB の役割をDF にしてもらい，M2法における DF の役割を BD にしてもらう．図を見れば，```x``` 持ち替えにより DF-BD インターチェンジが FU-DFインターチェンジと同じであることが簡単にわかるだろう (敢えて DF-FU とは書いていない) ．
```x``` で持ち替えた後，RU を DF へインサートするためには，```U' R' U``` を回せばよい．
結果として，

```
[x : U' R' U, M']
```

を得る．この場合は，本質的に DF-FU-RF パターンと同じであるが，**サイクルの向きにより一層注意して観察する**ことにより，インサートをものにしてもらいたい．
**!!!!ここに図を入れろ!!!!**

|                 Cycle                  |   Insert (to DF)  |       Execution         |
|:--------------------------------------:|:-----------------:|:-----------------------:|
|        DF &rarr; BD &rarr; RU          |    x U' R' U      |   [x : U' R' U, M']     | 
|        DF &rarr; BD &rarr; RF          |    x R U' R' U    |   [x : R U' R' U, M']   |
|        DF &rarr; BD &rarr; RD          |    x U' R U       |   [x : U' R U, M']      |
|        DF &rarr; BD &rarr; RB          |    x U' R2 U      |   [x : U' R2 U, M']     |
|        DF &rarr; BD &rarr; LU          |    x U L U'       |   [x : U L U', M']      |
|        DF &rarr; BD &rarr; LF          |    x L' U L U'    |   [x : L' U L U', M']   |
|        DF &rarr; BD &rarr; LD          |    x U L' U'      |   [x : U L' U', M']     |
|        DF &rarr; BD &rarr; LB          |    x U L2 U'      |   [x : U L2 U', M']     |

この表では，DF へインサートすべきパーツが R, L面(M列を除く) にあるときの 8 &times; 2 = 16 通りをカバーできる．



## &dagger;DF-BU インターチェンジ&dagger;<a id="sec4"></a>
このパターンは，今までのものとは異なり，BU が DF とinterchangeableでない(<a name="fenced-code-block">**!!!!f*ck!!!!</a>**)．
なので，個別に見ていくことにする...

### DF-BU-UR パターン
この場合は2通り考えることができる．一つ目は，<ruby><rb>Advanced</rb><rp>《</rp><rt>ｱﾄﾞｳﾞｧﾝｽﾄｩ</rt><rp>》</rp></ruby> M2 を使うことによりコミュテータにできる．

![DF-BU-UR](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BU-UR.png)

すなわち，

```
[U' : B L' B', M2]
```

である．しかし，個人的な意見だが，これは ```B L' B'``` を回す際に ```x'``` 持ち替えをして回す人が多いと思われるので，次のように2手セットアップを行う方がよいと考えている．

```
[R' F : U' L' U, M2]
```

このように ```R' F``` で持ち替えを行うと，UR が FD に移り，DF が LF に移るので，実質次図のような M2法の場合と同じなのである．また，2手セットアップではあるが，持ち替えがいらない手順で回せるのがよい．

![DF-BU-UR2](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BU-UR2.png)

後者のセットアップと同様のパターンを表にまとめておく．

|                 Cycle                  |   Insert (to UB)  |       Execution         |
|:--------------------------------------:|:-----------------:|:-----------------------:|
|          DF &rarr; BU &rarr; UR        |   (R' F) U' L' U  |   [R' F : U' L' U, M2]  | 
|          DF &rarr; BU &rarr; UL        |   (L F') U R U'   |   [L F' : U R U', M2]   |
|          DF &rarr; BU &rarr; FR        |   (F) U' L' U     |   [F : U' L' U, M2]     |
|          DF &rarr; BU &rarr; FL        |   (F') U R U'     |   [F' : U R U', M2]     |
|          DF &rarr; BU &rarr; DR        |   (R F) U' L' U   |   [R F : U' L' U, M2]   |
|          DF &rarr; BU &rarr; DL        |   (L' F') U R U'  |   [L' F' : U R U', M2]  |
|          DF &rarr; BU &rarr; BR        |   (R2 F) U' L' U  |   [R2 F : U' L' U, M2]  |
|          DF &rarr; BU &rarr; BL        |   (L2 F') U R U'  |   [L2 F' : U R U', M2]  |
8 &times; 2 = 16 通りをカバーできる．
DF &rarr; BU &rarr; DR, DL もこのセットアップのパターンに入れているが，他によい3-cycle手順が作れるのであまりお勧めできない．


### DF-BU-RF パターン
この場合は，```U2``` して DF-FU-RF パターンに帰着させてしまいましょう．

![DF-BU-RF](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BU-RF.png)

|                 Cycle                  |   Insert (to FU)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; BU &rarr; RF         |   (U2) U' R' U    |   [U2 : M', U' R' U]  | 
|         DF &rarr; BU &rarr; RD         |   (U2) U' R2 U    |   [U2 : M', U' R2 U]  |
|         DF &rarr; BU &rarr; RU         |   (U) R U' R' U   |   [U : M', R U' R' U] |
|         DF &rarr; BU &rarr; LF         |   (U2) U L' U'    |   [U2 : M', U L' U']  |
|         DF &rarr; BU &rarr; LD         |   (U2) U L2 U'    |   [U2 : M', U L2 U']  |
|         DF &rarr; BU &rarr; LU         |   (U') L' U L U'  |   [U' : M', L' U L U']|
6 &times; 2 = 12 通りをカバーできる．

### DF-BU-RB パターン
```B``` でセットアップする <ruby><rb>Advanced</rb><rp>《</rp><rt>ｱﾄﾞｳﾞｧﾝｽﾄｩ</rt><rp>》</rp></ruby> M2 でOK ．

|                 Cycle                  |   Insert (to UB)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; BU &rarr; RB         |    (B) U' L U     |   [B : U' L U, M2]    |
|         DF &rarr; BU &rarr; LB         |    (B') U R' U'   |   [B' : U R' U', M2]  |
2 &times; 2 = 4 通りをカバーできる．

### DF-BU-BD パターン
```U``` でセットアップすると DF-RU-BD パターンと同じになる．

![DF-BU-BD](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BU-BD.png)

もしくは，```x``` で持ち替えた後に ```U``` で DF を LF へセットアップし，BD と BU が ```D2``` で<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>と見る．そして LF を ```M' U' M``` で BD へインサートする (**ちなみにこの M' U' M 系のインサートはエッジコミュテータで多用するので覚えておくとよい**) ．

![DF-BU-BD2](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BU-BD2.png)

|                 Cycle                  |   Insert (to DF)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; BU &rarr; BD         |   (U x) U' R' U   |   [U x : U' R' U, M'] |
|         DF &rarr; BU &rarr; BD         |   (x U) M' U' M   |   [x M : D2, M' U' M] |
2通りカバーできる．



## &dagger; 発展 (M2法の範疇からは外れてしまうモノたち) &dagger;<a id="sec5"></a>
### DF-FU-DB パターン
```U``` で FU を LU へセットアップし，DF と DB が ```D2``` で<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>と見る．そして LU を ```M' U' M``` で DF へインサートする．

![DF-FU-DB](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-FU-DB.png)

|                 Cycle                  |   Insert (to DF)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; FU &rarr; DB         |    (U) M' U' M    |   [U : M' U' M, D2]   |
|         DF &rarr; BU &rarr; DB         |    (U) M' U M     |   [U : M' U M, D2]    |
2 &times; 2 = 4 通りカバーできる．


### DF-BU-UF
これは**[WRCCの森川くん](https://www.worldcubeassociation.org/results/p.php?i=2011MORI01)**
から教えて貰った手順．

```y``` で持ち替え，DF と UF が ```L2``` で<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>と見る．そして BU を ```U M' U'``` で UF へインサートする．**どうです，かっちょいいでしょう**

![DF-BU-UF](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-BU-UF.png)

|                 Cycle                  |   Insert (to UF)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; BU &rarr; UF         |      y U M' U'    |   [y : U M' U', L2]   |
2通りカバーできる．


### DF-FU-BU
これは ```U``` でセットアップし，DF-LU-RU の形にする．```y'``` で持ち替え，LU と RU が ```U2``` で<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>と見る．そして DF を ```M D' M'``` で LU へインサートする．

![DF-FU-BU](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-FU-BU.png)

|                 Cycle                  |   Insert (to LU)  |       Execution       |
|:--------------------------------------:|:-----------------:|:---------------------:|
|         DF &rarr; FU &rarr; BU         |   (U y') M D' M'  |  [U y' : M D' M', U2] |
2 通りカバーできる． 

**注意**．この手順はキャンセルが起きるので，それも含めてモノにしたい (後で触れるが，これは3BLDだともっと良い手順が作れる) ．DF-FU-BU サイクルでは，

```
U y' M D' M' U2 M D M' U y
```

となり，DF-BU-FU のサイクルでは，

```
U' y M D M' U2 M D M' U y'
```

となる．このようなキャンセルは他にもあるので，自分でコミュテータを作りながらモノにしていってもらいたい．

## &dagger;おわりに &amp; 謝辞&dagger;<a id="sec6"></a>
これまで，**f*ck**なM列サイクルたちを華麗にコミュテータに変身させてきた．その数実に 
<div style="text-align: center;"> <p><font size="6" color="#ff0000">**114**</font></p> </div>
通り．強い[確信]．
<div style="text-align: center;"> <p><font size="6" color="#0000ff">**やったねたえちゃん！！**</font></p> </div>

今回紹介した手順が <ruby><rb>speed</rb><rp>《</rp><rt>ｽﾋﾟｰﾄﾞ</rt><rp>》</rp></ruby>
<ruby><rb>optimal</rb><rp>《</rp><rt>ｵﾌﾟﾃｨﾏﾙ</rt><rp>》</rp></ruby> とは限りません．まだ 3-style に移行していないマンは，M列だけでなく，他のサイクルでも君だけの手順を作れ！


今回この記事を書くにあたり，WRCCの知識番長[森川くん](https://www.worldcubeassociation.org/results/p.php?i=2011MORI01) と MBLD圧倒的NR保持者[しおやん](https://www.worldcubeassociation.org/results/p.php?i=2013SATO01) に誤植の指摘や貴重なアドバイスをいただいた．どうもありがとう．

また，Speedcubing Advent Calendar 2014を企画してくださった荒木慎平さんに感謝する．

私はBLDが好きだ．ある圧倒的な者がこう言っていた．
>朝起きた時に今日も一日BLDをやるぞと思ってるようでは，とてもものにならない．BLDを考えながら，いつのまにか眠り，朝目が覚めたときは既にBLDの世界に入っていなければならない．どの位BLDに浸っているかが，勝負の分かれ目だ．BLDは自分の命を削ってやるようなものなのだ．

(ここまでやる気はない)


最近，日本の大会でのBLDのレベルが急上昇しているように感じている．個々人が知恵を絞り，未開のまま横たわっている多くの3-cycle手順を作り出していくことを期待している．本記事がそのための刺激となれば，筆者の望外の喜びとするところである．
<div style="text-align: right;">2014/12/20　[WRCC](http://wrcc.main.jp) blindfolded chief adviser </div>
<div style="text-align: right;">[A. Misawa](https://www.worldcubeassociation.org/results/p.php?i=2010MISA01) </div>

## &dagger;オマケ (M列以外だけどよく使うエッジコミュテータたち)&dagger;<a id="sec7"></a>
ここでは，パターンを紹介するが，表などは作らず一例を挙げるのみに留めることにする．読者自ら手順を作成されたい．tips的サムシングである．

### なんかよくわからないけど使えるやつ
- DF-UB-UFパターン

	![DF-UB-UF](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-UB-UF.png)
	
	この場合は，
	
	```
	M' U2 M U2
	```
	
	だけで揃えられる．逆サイクルの場合は，
	
	```
	U2 M' U2 M
	```
	
	でOK ．
	
	このパターンが重要なのは，このパターンにセットアップできる場合が多いためである．
	例えば DF-UR-UL である．
	
	![DF-UR-UL](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-UR-UL.png)

	これは，```U'``` でセットアップすることにより DF-UB-UF パターンになるが，キャンセルを気持ち良く覚えられるパターンである．
	
	```
	U' M' U2 M U2 U = U' M' U2 M U'
	```
	
	逆サイクルでのキャンセルは次のようになる．
	
	```
	U M' U2 M U2 U' = U M' U2 M U
	```
	
	このパターンは，DF-UR-BL などにもそのまま応用可能である．

### D面インターチェンジ

#### DF-DR-RU パターン
DFとDRが ```D``` で<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>であり，RUを ```M' U M``` でDFへインサートする．

![DF-DR-RU](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-DR-RU.png)

### R面インターチェンジ
- DF-RU-RF

	![DF-RU-RF](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-RU-RF.png)

	UF を ```U M' U'``` により DF へインサートすればよい．同様なパターン豊富でこれもまた美味しい．prpr
	
	```
	[U M' U', R]
	```
	
- DF-UL-DL

	![DF-UL-DL](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-UL-DL.png)
	
	UL を ```U M2 U'``` により DF へインサートすればよい．同様なパターン豊富．
	
	```
	[U M2 U', L2]
	```


### F面インターチェンジ
- DF-RD-UF

	![DF-RD-UF](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-RD-UF.png)
	
	```y``` で持ち替えると，UB と DF が ```L2``` により<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>となる．RD を ```U' M' U``` で UF へインサートすればよい．
	
	```
	[y : U' M' U, L2]
	```
	
- DF-RF-BL

	![DF-RF-BL](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-RF-BL.png)
	
	```x``` で持ち替えると，DF と RF が ```U``` により<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>となる．BL を ```M D M'``` で DF へインサートすればよい．
	
	```
	[x : M D M', U]
	```
	

### E系インターチェンジ
これは，筆者が ```E``` で回せないため， ```z``` 系で持ち替えて ```M``` 系インターチェンジと捉えている．

- DF-FL-BR
	
	![DF-FL-BR](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-FL-BR.png)
	
	```
	[z : U L' U', M2]
	```


### S系インターチェンジ
 - DF-RU-UL

 	![DF-RU-UL](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-RU-UL.png)

	```y``` で持ち替えると，RU と UL が ```M'``` により<ruby><rb>interchangeable</rb><rp>《</rp><rt>ｲﾝﾀｧﾁｪｨﾝｼﾞｬﾎﾞｩ</rt><rp>》</rp></ruby>である．DF を ```U' L2 U``` で UL へインサートすればよい．

	```
	[y : M', U' L2 U]
	```


### これまたなんか変なやつ
さきほど後で触れると書いたものについて，この辺りで触れようと思う．	

- DF-RU-LU パターン

	![DF-RU-LU](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-RU-LU.png)

	逆サイクルも一緒に書いてしまいます．コツは，順サイクルは右指，逆サイクルは左指．
	
	```
	M U M U2 M' U M'
	```
	
	```
	M U' M U'2 M' U' M'
	```

- DF-LF-RF

	![DF-LF-RF](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-LF-RF.png)

	これは，```x``` で持ち替えるとU-permでOK ．
	
	```
	x R2 U R U R' U' R' U' R' U R' x'
	```
	
	ドMな私は，次のM系で回すのがすき&#9825;
	
	```
	x M2 U' M U2 M' U' M2 x'
	```
	
- DF-FL-FR

	![DF-FL-FR](http://wrcc.main.jp/commentary/imgs_edge_tutorial/DF-FL-FR.png)
	
	時計回りのようなこちらのサイクルは ```U``` が使われ，
	
	```
	x M U M' U2 M U M' x'
	```
	
	反時計回りの逆サイクルは ```U'``` が使われる．なかなか好きな3-cycleである．
	
	```
	x M U' M' U2 M U' M' x'
	```

[BLD解説 目次](http://wrcc.main.jp/commentary/)

[TOP](http://wrcc.main.jp)


