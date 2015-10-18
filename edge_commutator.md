# Edge Commutator
+ 2015/10/16 更新．X1 = UL, UB cycleを追加
+ 2015/10/12 更新．X1 = UR, UF cycleを追加

## 目次
+ [UR](#UR)
+ [UF](#UF)
+ [UL](#UL)
+ [UB](#UB)

## Notation
cycleについては，「DF&rarr;X1&rarr;X2」としている．

## かわいいかわいい手順たち

| X1 | X2 |      execution        |　 | X1 | X2 |      execution        |
|:--:|:--:|:---------------------:|:-:|:--:|:--:|:---------------------:|
|UR<a id="UR"></a>| UR | にゃん    |　|UF<a id="UF"></a>| UR | ([UR&rarr;UF](#URUF))'|
|<a id="URUF"></a>| UF | ```[U, M D2 M']```   |<a id="UFUF"></a>|　   | UF |にゃん|
|<a id="URUL"></a>| UL | ```U' M' U2 M U'```  |<a id="UFUL"></a>|　   | UL |```[M D2 M', U']```|
|<a id="URUB"></a>| UB | ```[R' U R U', M2]```|<a id="UFUB"></a>|　   | UB |```U2 M' U2 M```|
|　|　|　|　|　|　|　 |
|<a id="URFR"></a>| FR | ```[U' M2 U, R]```   |<a id="UFFR"></a>|　   | FR |```[U2; M2, U R U']```|
|<a id="URFD"></a>| FD | にゃん                |<a id="UFFD"></a>|　   | FD |にゃん|
|<a id="URFL"></a>| FL | ```L'```[UR&rarr;UL](#URUL)|<a id="UFFL"></a>|　   | FL |```[U2; M2, U' L' U]```|
|<a id="URFU"></a>| FU | ```x [U R' U', M']```|<a id="UFFU"></a>|　   | FU |にゃん|
|　|　|　|　 |
|<a id="URLF"></a>| LF | ```Uw'```[UB&rarr;FR](#UBFR)|<a id="UFLF"></a>|　   | LF |```x U'```U-perm|
|<a id="URLD"></a>| LD | ```U'```[UB&rarr;LD](#UBLD)|<a id="UFLD"></a>|　   | LD |```y' [R2, U M' U']```|
|<a id="URLB"></a>| LB | ```Uw'```[UB&rarr;FL](#UBFL)|<a id="UFLB"></a>|　   | LB |```B'```[UF&rarr;UB](#UFUB)|
|<a id="URLU"></a>| LU | ```y' [U R2 U', M']```|<a id="UFLU"></a>|　   | LU |```U2```[UB&rarr;RU](#UBRU)|
|　|　|　|　 |
|<a id="URBL"></a>| BL | ```L```[UR&rarr;UL](#URUL)|<a id="UFBL"></a>|　  | BL |```x [M D M', U2]```|
|<a id="URBD"></a>| BD | ```x' [U R U', M]```  |<a id="UFBD"></a>|　  | BD |```[U x'; U' L' U, M]```|
|<a id="URBR"></a>| BR | ```[U' M2 U, R']```   |<a id="UFBR"></a>|　  | BR |```x [M D' M', U2]```|
|<a id="URBU"></a>| BU | ```R' F```[UB&rarr;FL](#UBFL)|<a id="UFBU"></a>|　  | BU |```y [L2, U M' U']```|
|　|　|　|　 |
|<a id="URRB"></a>| RB | ```Uw'```[UB&rarr;BL](#UBBL)   |<a id="UFRB"></a>|　   | RB |```B```[UF&rarr;UB](#UFUB)|
|<a id="URRD"></a>| RD | ```y' [U R2 U', M]``` |<a id="UFRD"></a>|　   | RD |```y [L2, U' M' U]```|
|<a id="URRF"></a>| RF | ```Uw'```[UB&rarr;RB](#UBRB)|<a id="UFRF"></a>|　   | RF |```x U```U-perm|
|<a id="URRU"></a>| RU | にゃん                 |<a id="UFRU"></a>|　   | RU |```U2```[UB&rarr;LU](#UBLU)|
|　|　|　|　 |
|<a id="URDR"></a>| DR | ```[U' M2 U, R2]```   |<a id="UFDR"></a>|　   | DR |```[D', M' U2 M]```|
|<a id="URDB"></a>| DB | ```Uw M Uw2 M Uw```   |<a id="UFDB"></a>|　   | DB |```M Uw2 M Uw2```|
|<a id="URDL"></a>| DL | ```y' [U R2 U', M2]```|<a id="UFDL"></a>|　   | DL |```[D, M' U2 M]```|
|<a id="URDF"></a>| DF | にゃん                 |<a id="UFDF"></a>|　   | DF |にゃん|
|　|　|　|　 |
|UL<a id="UL"></a>| UR | ```U M' U2 M U```    |　|UB<a id="UB"></a>| UR | ([UR&rarr;UB](#URUB))'|
|<a id="ULUF"></a>| UF | ```[U', M D2 M']```    |<a id="UBUF"></a>|　   | UF |```M' U2 M U2```|
|<a id="ULUL"></a>| UL | にゃん|　|<a id="UBUL"></a>| UL |([UL&rarr;UB](#ULUB))'|
|<a id="ULUB"></a>| UB | ```[L U' L' U, M2]``` |　|<a id="UBUB"></a>| UB |にゃん|
|　|　|　|　|　|　|　 |
|<a id="ULFR"></a>| FR | ```R```[UL&rarr;UR](#ULUR)|<a id="UBFR"></a>|　   | FR |```[M2, U R U']```|
|<a id="ULFD"></a>| FD | にゃん                |<a id="UBFD"></a>|　   | FD |にゃん|
|<a id="ULFL"></a>| FL | ```[U M2 U', L']```  |<a id="UBFL"></a>|　   | FL |```[M2, U' L' U]```|
|<a id="ULFU"></a>| FU | ```x [U' L U, M']``` |<a id="UBFU"></a>|　   | FU |```[D: U R2 U', M']```|
|　|　|　|　|　|　|　 |
|<a id="ULLF"></a>| LF |```Uw```[UB&rarr;BL](#UBBL)|<a id="UBLF"></a>|　   | LF |```[M2, B L2 B']```|
|<a id="ULLD"></a>| LD |```y [U' L2 U, M]```|<a id="UBLD"></a>|　   | LD |```[M2, B L B']```|
|<a id="ULLB"></a>| LB |```Uw```[UB&rarr;BR](#UBBR)|<a id="UBLB"></a>|　| LB |```[M2, L B L' B']```|
|<a id="ULLU"></a>| LU |にゃん|<a id="UBLU"></a>|　   | LU |```[M2, B L' B']```|
|　|　|　|　 |
|<a id="ULBL"></a>| BL |```[U M2 U', L]```    |<a id="UBBL"></a>|　  | BL |```[M2, U' L U]```|
|<a id="ULBD"></a>| BD |```x' [U' L' U, M]``` |<a id="UBBD"></a>|　  | BD |```U```[UR&rarr;BD](#URBD)|
|<a id="ULBR"></a>| BR |```R'```[UL&rarr;UR](#ULUR)|<a id="UBBR"></a>|　  | BR |```[M2, U R' U']```|
|<a id="ULBU"></a>| BU |```L F'```[UB&rarr;FR](#UBFR)|<a id="UBBU"></a>|　  | BU |にゃん|
|　|　|　|　 |
|<a id="ULRB"></a>| RB |```Uw```[UB&rarr;FR](#UBFR)|<a id="UBRB"></a>|　   | RB |```[M2, R' B' R B]```|
|<a id="ULRD"></a>| RD |```U```[UR&rarr;RD](#UBRD)|<a id="UBRD"></a>|　   | RD |```[M2, B' R' B]```|
|<a id="ULRF"></a>| RF |```Uw```[UB&rarr;FL](#UBFL)   |<a id="UBRF"></a>|　   | RF |```[M2, B' R2 B]```|
|<a id="ULRU"></a>| RU |```y [U' L2 U, M']``` |<a id="UBRU"></a>|　   | RU |```[M2, B' R B]```|
|　|　|　|　 |
|<a id="ULDR"></a>| DR |```y [U' L2 U, M2]``` |<a id="UBDR"></a>|　   | DR |```[M2, U R2 U']```|
|<a id="ULDB"></a>| DB |```Uw' M Uw2 M Uw'``` |<a id="UBDB"></a>|　   | DB |```Uw2 M Uw2 M```|
|<a id="ULDL"></a>| DL |```[U M2 U', L2]```|<a id="UBDL"></a>|　   | DL |```[M2, U' L2 U]```|
|<a id="ULDF"></a>| DF |にゃん                 |<a id="UBDF"></a>|　   | DF |にゃん|

[BLD解説 目次](http://wrcc.main.jp/commentary/)

[TOP](http://wrcc.main.jp)