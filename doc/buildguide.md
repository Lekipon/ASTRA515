

# ASTRA515 ビルドガイド

この度は「ASTRA 515」をお買い上げいただきまして誠にありがとうございます。
このキーボードキットは<u>5行x15列の格子配列で設計されたキーボード</u>です。

ファームウェアについては[QMK Firmware](https://github.com/qmk/qmk_firmware)を採用しており、多少のスキルや慣れは必要ですがユーザー自身で自由に各キーの割り当てを変更することが出来ます。

なお、このキットは初歩的なハンダ付けを含む組立が必要です。

ハンダ付けの難易度が比較的高いRGBLEDに関しては予め手作業で実装した状態で梱包しておりますが、比較的キー数が多く実装部品も多いため、正直言って「簡単だけど面倒くさい」キットとなっている点にはご了承ください。また、当方では「完成品が欲しい」「組立作業を代行して欲しい」といったお問い合わせに応じることは出来ません。

自作キーボードは出来上がった完成品を使うことで得られる使い心地だけでなく、それを作る過程も含めて楽しんでいただけたら幸いです。



## 1：キット添付品の確認

**1）PCBとスイッチマウントプレート**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/003.JPG" style="zoom:50%;" />

・PCBにはWS2812Bが表面に3カ所、裏面に13カ所実装されています。



**2）アクリルプレート（３種類）**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/004.JPG" style="zoom:50%;" />

・上から順にボトムプレート用、トップカバー用、底上げ用となります。



**3）ネジ・スペーサー類**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/005.JPG" style="zoom:50%;" />

①M2x12mmネジ：12本

②M2x5mmネジ：12本

③M2ワッシャー：8枚

④M2x3mmスペーサー：8本

⑤M2x4mmスペーサー：12本

⑥M2x12mmスペーサー：4本

⑦ゴム足：大3個、小3個



**4）Kailh PCBソケット（MXスイッチ用65個）**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/006.JPG" style="zoom:50%;" />



**5）ダイオード（75本）**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/007.JPG" style="zoom:50%;" />



**6）ProMicro（Mini-Bタイプ）、コンスルー、タクタイルスイッチ**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/008.JPG" style="zoom:50%;" />

・ProMicroにはデフォルトファームウェアを書込み済となっています。基板にバリが残っているので、側面に軽く紙やすりを掛けた上でゼブラの黒マッキー等で側面を黒塗りしておくことをお勧めします。



## **2：PCBへのダイオードの取り付け**



・写真のように先が細いピンセットでダイオードの根元をつまんで足を直角に曲げていきます。なお、PCB側のダイオード用の穴は6.35mmの間隔で設計していますので、その穴にマッチするように曲げていってください。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/010.JPG" style="zoom:50%;" />





・このように両方の足を曲げたダイオードを全部で75本作っていきます。正直「面倒くさい」作業ですが、一つ一つのダイオードが全て役割を持っているということを感じていただけたら幸いです。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/011.JPG" style="zoom:50%;" />





・PCBの表面からダイオードを差し込んで行きます。なお「ASTRA 515」ではDuplexMatrixの実装をしている関係上、写真のように5個一組で交互に実装方向が反転しているのが特徴です。PCB表面のシルク印刷でも実装方向を明示していますが、原則として「四角い穴のある側に黒い印がくるように」と覚えていただいても結構です。

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

・なお、標準添付のMini-BタイプのProMicroでは外側の列の穴を使用します。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/022.JPG)



・ProMicroにコンスルーを差し込みます。コンスルーの取り付け方向には決まりがありますので、写真を参考に間違えないようにします。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/023.JPG)



・コンスルーを装着した状態でProMicroをPCBの穴に差し込みます。先に説明したとおり、Mini-BタイプのProMicroでは外側の列の穴に差し込むようにします。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/024.JPG)



・間違いなく装着出来たら、写真のようにProMicro側だけコンスルーの足をハンダ付けします。くれぐれもコンスルーのPCB側はハンダ付けしないようにしましょう（2度と外せなくなります）

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

![032](P:\GitHub.lekipon\ASTRA515\doc\img\032.JPG)





## **6：キースイッチの取り付け**

・下の写真のようにソケット非対応の区画にキースイッチをセットしていきます。なお、キーサイズ選択制の都合により、一部のキースイッチは上下逆方向に取り付けるようになっていますのでご注意ください。

・また、ロータリーエンコーダの代わりにMXスイッチを使用する場合は、3ピンタイプのスイッチでないと入りません。5ピンタイプのスイッチを使う場合は保持用のプラスチックピンをニッパーでカットしてからセットしてください。

・なお、キースイッチの取り付け方向を判別するためにPCBとプレートにキーサイズの表記されています。

![033](P:\GitHub.lekipon\ASTRA515\doc\img\033.JPG)



・続いてソケット対応の区画にキースイッチをセットしていきます。ソケットの場合は無理にスイッチを押し込んで接点のピンが曲がったりしないように注意してください。ハンダ付けと違って失敗しやすい箇所ですのでご注意ください。

・ソケットにスイッチが正しくセットされていることを確認するために、この時点で一旦PCに接続して押したスイッチが反応することを確認しておくと良いでしょう。

![034](P:\GitHub.lekipon\ASTRA515\doc\img\034.JPG)



・基板を裏返して、キースイッチとロータリーエンコーダのハンダ付けをします。なお、ロータリーエンコーダのピンは手前3カ所と奥2カ所のピンをハンダ付けすれば十分な強度が得られるので、左右の保持ピンはハンダ付けしない方が良いと思います。

![035](P:\GitHub.lekipon\ASTRA515\doc\img\035.JPG)





## **7：アクリルプレートの取り付け**

・スイッチ類のハンダ付けが完了したら、写真のようにアクリルのボトムプレートと底上げ用プレートを被せてM2ネジで止めていきます。手前側の8カ所はM2x5mmネジ、奥側両端の4カ所はM2x8mmネジを使用します。

（この写真では試作の無刻印ボトムプレートですが、キットには刻印入りのボトムプレートを添付しています）

![036](P:\GitHub.lekipon\ASTRA515\doc\img\036.JPG)



・最後にキーキャップを取り付けて、トップカバー用のアクリルプレートをM2x5mmネジで取り付けます。

![037](P:\GitHub.lekipon\ASTRA515\doc\img\037.JPG)



・以上で組立は終了です。お疲れ様でした。

・ProMicroにはデフォルトキーマップを書き込んでありますので、全てのキーが正しく反応するかチェックしましょう。

![038](P:\GitHub.lekipon\ASTRA515\doc\img\038.JPG)



・キーマップとQMKファームウェアについては別項にて記載します。

