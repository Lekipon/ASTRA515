

# ASTRA 515 　QMKファームウェアについて



## 1：デフォルトキーマップの説明

**レイヤー0　デフォルトレイヤー（ANSIモード）**

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/layer00.png)

- デフォルトレイヤーはQWERTY配列をベースとした格子配列となっています。
- また、この状態ではレイヤーインジゲータのLEDは「暗い緑色」に発光します。
- 左右両方にスペースキーがありますが、右のスペースの「SandS」とは「タップでSpace、押しっぱなしだとShift」の兼用という設定になっています。右の親指でShiftを押せるようにしておくと何かと便利なため、この設定にしてあります。
- ロータリーエンコーダを付けた場合の設定は、左側のノブを回すとカーソルの上下移動、右側のノブを回すとカーソルの左右移動に割り当ててあります。プッシュボタンを押した時はそれぞれ" [ ”と” ] ”の記号を出す設定になっています（ロータリーエンコーダ無しの構成で組んだ場合に配慮のため）。
- このモードではPCのOS側は英語配列（104キーボード）の設定になっている必要があります。

<br>

**レイヤー1　JIS設定用レイヤー（JISモード）**

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/layer01.png)

- このレイヤーはPCのOS側が日本語配列（109キーボード）の設定になっている場合に使うレイヤーです。
- また、この状態ではレイヤーインジゲータのLEDは「暗い青色」に発光します。
- 職場等でリモート接続先のPCだとOS側の設定が日本語配列になっている場合が普通なので、そのような場合に記号類の不整合を直すためにこのレイヤーに切り替えて使用しています。
- このモードに入る時は後述のADJUSTレイヤーにてJISモードに切り替えます。
- なお、このJISモードの実装については[koktohさんのjtu_custom_keycodes](https://github.com/koktoh/jtu_custom_keycodes)のコードを利用させていただいています。

<br>

**レイヤー2　RAISE（ファンクションキーレイヤー）**

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/layer02.png)

- このレイヤーは右手親指のRaiseキーを押している間だけ有効となります。
- また、この状態ではレイヤーインジゲータのLEDは「明るいオレンジ色」に発光します。
- 右手のホームポジションから手を動かすことなくカーソル移動が出来る設定になっていますが、PCゲームの「WASD」やVimの「HJKL」といったデファクトスタンダートなカーソル移動方法に慣れている人にとっては、かなり使いにくいかも知れません。
- 作者個人としては「H」の位置に「B/S」そして「G」の位置に「Esc」を割り当てたいという事情もあってこのような「JKL;」の位置でカーソル移動させるレイアウトを採用しています。
- また、Raiseを押しながら左手親指のLowerも押すと後述のADJUSTレイヤーに入ります。

<br>

**レイヤー3　LOWER（テンキー及び記号のレイヤー）**

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/layer03.png)

- このレイヤーは左手親指のLowerキーを押している間だけ有効となります。

- また、この状態ではレイヤーインジゲータのLEDは「明るい緑色」に発光します。

- 右手のホームポジションのままでテンキーの数字や記号が入力出来るようになっています。ただしNumLockがONになっていることが必要です。なお、NumLockの状態はNumのLEDが「明るい黄色」に発光しているかどうかで確認出来ます。

- 左手のホームポジションにカーソル移動とEnterを割り当てているのは、作者自身が右手で晩酌しながら左手でカーソル移動させることが多いためです。

- RAISE/LOWER共に" [ "と " ] "の記号を割り当てているのはロータリーエンコーダのプッシュスイッチが堅くて押しづらいことに対する配慮となります。

  <br>

**レイヤー4　ADJUST（各種設定用のレイヤー）**

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/layer04.png)

- このレイヤーは「Raiseキーを押しながらLowerキーを押している」間だけ有効となります。逆に「Lowerキーを押しながらRaiseキーを押し」てもテンキーの0が出力されるだけなのでご注意ください。
- また、この状態ではレイヤーインジゲータのLEDは「明るい水色」に発光します。
- アンダーグロウのRGBLEDの設定、PCの音量/ミュート設定、ANSI/JISモードの切り替えに使います。

- 例としてこのレイヤーで「JIS MODE」を押すとレイヤー1に切り替わります。JISモードからANSIモードに戻すときは、同様に「ANSI MODE」を押すとレイヤー0に切り替わります。

<br><br>

## **2：QMKファームウェアについて**

- QMK ToolboxをPCにインストールします。少し古い記事となりますが [サリチル酸さんのBlogの記事](https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox)が大変分かりやすいです。

- QMKの[本家](https://github.com/qmk/qmk_firmware)には「ASTRA515」のコードはまだマージされていませんので、当面の間はこの[フォークしたQMK](https://github.com/Lekipon/qmk_firmware)を使用してください。

- QMKのビルド環境の構築方法については、各自のOS環境に合わせて調べていただくようお願いします。特にWindowsでMSYS2環境内に構築する方法はトラブルが報告されているようなので、作者自身もあまり自信ありません（復習のために後日ダメ元で実験してみる予定ですが）。

- 既にQMKファームウェアのビルド環境を構築をしている方は、ダウンロードしたqmk_firmware-master.zipを解凍して、出来上がった「qmk_firmware-master/」フォルダの中から「keyboards/lekipon」以下の中身をご自身の環境にコピーしても大丈夫だと思います（lekiponフォルダには作者が他に開発したキーボードのファームウェアも一緒に入っています）。

  <br>

- ビルドする際にはコマンドライン上でQMKビルド環境のルートフォルダに入って、以下のコマンドでコンパイルします。

```
make lekipon/astra515:default
```

- これでQMKビルド環境のルートフォルダに「lekipon_astra515_default.hex」というファイルが生成されます。このファイルをQMK ToolboxでProMicroに書き込みます。

<br>

- コマンドライン上でそのままProMicroに直接書き込む時は以下のコマンドとなります。

```
make lekipon/astra515:default:flash
```

- Elite-Cを使用する場合は、ProMicroとブートローダーが違うため以下のコマンドとなります。

```
make lekipon/astra515:default:dfu
```

<br>



- なお、動作確認の為にデフォルトの[HEXファイル](https://github.com/Lekipon/ASTRA515/blob/master/hex/lekipon_astra515_default.hex)を用意していますが、標準添付のProMicroに書込済のものと同様になります。





















・写真のように先が細いピンセットでダイオードの根元をつまんで足を直角に曲げていきます。なお、PCB側のダイオード用の穴は6.35mmの間隔で設計していますので、その穴にマッチするように曲げていってください。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/010.JPG" style="zoom:50%;" />





・このように両方の足を曲げたダイオードを全部で75本作っていきます。正直「面倒くさい」作業ですが、一つ一つのダイオードが全て役割を持っているということを感じていただけたら幸いです。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/011.JPG" style="zoom:50%;" />





・PCBの表面からダイオードを差し込んで行きます。なお「ASTRA 515」ではDuplexMatrixの実装をしている関係上、写真のように5個一組で交互に実装方向が反転しているのが特徴です。PCB表面のシルク印刷でも実装方向を明示していますが、原則として「四角い穴のある側に黒い印がくるように」と覚えていただければ結構です。

・試しに方向の間違いがなく10本差し込んでみたら、表面からマスキングテープを貼ってダイオードを固定してみましょう。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/012.JPG" style="zoom:50%;" />





・PCBを裏返してニッパーでダイオードの足を切って行きます。切る長さですが、気持ち的には「ツライチ」にする感じでいいと思います。

・なお写真ではニッパーに100均の強力マグネットを貼り付けているため、切った足は自動的にマグネットに吸着されるようになっています。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/013.JPG" style="zoom:50%;" />





・「ツライチ」のつもりで切っても僅かに表面に足が出た状態になります。個人的にはこれくらいが好みです。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/014.JPG" style="zoom:50%;" />



・スルーホール部品のハンダ付けでは必須ではないですが、軽くフラックスを塗布した上でハンダ付けを行います。なお、FX600での温度設定は終始320℃の設定で支障ありません。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/015.JPG" style="zoom:50%;" />





・これで最初のダイオード10個が実装されました。この後も10個づつ慎重に実装をしていくといいでしょう。なお、実装後のフラックス汚れは一段落ついた後でフラックス洗浄液で落とせば綺麗になります。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/016.JPG" style="zoom:50%;" />





・全てのダイオードの実装が完了すると写真のようになります。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/019.JPG" style="zoom:50%;" />

ここまでの工程で数時間は掛かっているはずなので、一旦休憩を入れた方がいいと思います。





## **3：PCBへのKailhソケットの取り付け**

・PCBを裏返しにしてKailhソケットをハンダ付けしていきます。難易度の低い部品ですが、表面実装のためパッドには必ずフラックスを塗布するようにしてください。

・この工程のソケット部品はFX600に標準添付のB型コテ先だと熱を伝えにくいのでC2やD16のように平面とエッジのあるコテ先の使用をお勧めします。コテ先に予めハンダを盛った状態でパッドと端子を加熱すると「ジョワっ」っという音と共にハンダがスムーズに流れ込んで行きます。

・片側をハンダ付けしたら、基板を180度反転させて反対側からも同様にハンダ付けします。

・ハンダの消費量が多く煙が沢山出る作業なので、部屋の換気をしておいた方が良いと思います。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/020.JPG" style="zoom:50%;" />





・65個全てのソケットを実装すると写真のようなります。なお、中央下部のソケットの無い区画はロータリーエンコーダの実装やキーサイズ選択制の都合によりソケット非対応とさせていただいてます。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/021.JPG)



## **4：ProMicroの取り付け**



・PCBのProMicro取り付け箇所は写真のようになっています。大きめなMini-BタイプのProMicro（700mil幅）と通常サイズのProMicro（600mil幅）の両方に対応しているため2種類の幅の列に穴が用意されています。

・なお、添付品のMini-BタイプのProMicroでは外側の列の穴を使用します。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/022.JPG)



・ProMicroにコンスルーを差し込みます。コンスルーの取り付け方向には決まりがありますので、写真を参考にして間違えないようにしましょう。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/023.JPG)



・コンスルーを装着した状態でProMicroをPCBの穴に差し込みます。先に説明したとおり、Mini-BタイプのProMicroでは外側の列の穴に差し込むようにします。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/024.JPG)



・間違いなく装着出来たら、写真のようにProMicro側だけコンスルーの足をハンダ付けします。くれぐれもコンスルーのPCB側はハンダ付けしないようにしましょう（二度と外せなくなります）

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/025.JPG)



・参考として600mil幅のProMicro（Elite-C）を装着した場合は、以下の写真のように内側の列の穴を使用することになります。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/026.JPG)





## **5：スイッチマウントプレートの取り付け**



・ロータリーエンコーダを使用する場合は、プレートを装着する前に下の写真のようにプレートを金属ヤスリで軽く削っておくことをお勧めします。予めこの加工をしておけば、プレートを外すことなくロータリーエンコーダの交換が出来るようになります。

・なお、ロータリーエンコーダを使用せずにMXスイッチのみの構成とする場合は、上記の加工はしない方が良いです（MXスイッチの保持が甘くなってしまうため）

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/027.JPG)



・プレートのネジ穴（8カ所）に写真のようにM2x8mmネジにM2ワッシャーを1枚通してM2x3mmスペーサーで締め付けます。なお、M2ワッシャーはプレート表面とPCB表面のクリアランスを約5mmになるように調整するために挟んでいます。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/028.JPG)



・8カ所にネジ、ワッシャー、スペーサーを取り付けると下の写真のようになります。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/029.JPG)



・プレートをPCBに被せます。なお、写真では先にロータリーエンコーダをPCBに差し込んでいますが、上記のプレート切削加工をしている場合は、後から差し込んでも構いません。

・なお、中央下段のキーを縦の2Uサイズとする場合はこの時点で2Uのスタビライザー（別売）をPCBに装着しておく必要があります。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/030.JPG)





・PCBのネジ穴にプレートのネジが通ったら、PCB裏面からM2x4mmスペーサーで8カ所締めます。手でスペーサー強く締め込んでからプライヤーで掴んで45度程度右に回すと本締めとなります。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/031.JPG)



・PCB上部の両端4カ所にM2x12mmスタッドスペーサーをM2x4mmスペーサーで取り付けます。

![032](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/032.JPG)





## **6：キースイッチの取り付け**

・下の写真のようにソケット非対応の区画にキースイッチをセットしていきます。なお、キーサイズ選択制の都合により、一部のキースイッチは上下逆方向に取り付けるようになっていますのでご注意ください。

・また、ロータリーエンコーダの代わりにMXスイッチを使用する場合は、3ピンタイプのスイッチでないと入りません。5ピンタイプのスイッチを使う場合は保持用のプラスチックピンをニッパーでカットしてからセットしてください。

・なお、キースイッチの取り付け方向を判別するためにPCBとプレートにキーサイズの表記されています。

![033](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/033.JPG)



・続いてソケット対応の区画にキースイッチをセットしていきます。ソケットの場合は無理にスイッチを押し込んで接点のピンが曲がったりしないように注意してください。ハンダ付けと違って失敗しやすい箇所ですのでご注意ください。

・ソケットにスイッチが正しくセットされていることを確認するために、この時点で一旦PCに接続して押したスイッチが反応することを確認しておくと良いでしょう。

![034](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/034.JPG)



・基板を裏返して、キースイッチとロータリーエンコーダのハンダ付けをします。なお、ロータリーエンコーダのピンは手前3カ所と奥2カ所のピンをハンダ付けすれば十分な強度が得られるので、左右の保持ピンはハンダ付けしない方が良いと思います。

![035](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/035.JPG)





## **7：アクリルプレートの取り付け**

・スイッチ類のハンダ付けが完了したら、写真のようにアクリルのボトムプレートと底上げ用プレートを被せてM2ネジで止めていきます。手前側の8カ所はM2x5mmネジ、奥側両端の4カ所はM2x8mmネジを使用します。

・この時点でゴム足もアクリルプレートに貼付します。手前側にゴム足（小）を、奥側にゴム足（大）を使いますが、奥側は剛性が高く打鍵感が堅くなりやすいので、両端の2カ所だけでいいかも知れません。

（註：写真では試作の無刻印ボトムプレートですが、キットには刻印入りのボトムプレートを添付しています）

![036](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/036.JPG)



・最後にキーキャップを取り付けて、トップカバー用のアクリルプレートをM2x5mmネジで取り付けます。

![037](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/037.JPG)



・以上で組立は終了です。お疲れ様でした。

・ProMicroにはデフォルトキーマップを書き込んでありますので、全てのキーが正しく反応するかチェックしましょう。

![038](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/038.JPG)



（デフォルトキーマップとQMKファームウェアについては別項にて記載します）

