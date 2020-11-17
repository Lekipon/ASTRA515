

# ASTRA515 組立手順

この度は「ASTRA 515」をお買い上げいただきまして誠にありがとうございます。
このキーボードキットは<u>5行x15列の格子配列で設計されたキーボード</u>となります。

ファームウェアについては[QMK Firmware](https://github.com/qmk/qmk_firmware)を採用しており、多少のスキルや慣れは必要ですがユーザー自身で自由に各キーの割り当てを変更することが出来ます。

なお、このキットは初歩的なハンダ付けを含む組立が必要です。

ハンダ付けの難易度が比較的高いRGBLEDに関しては予め手作業で実装した状態で梱包しておりますが、比較的キー数が多く実装部品も多いため、正直言って「簡単だけど面倒くさい」キットとなっている点にはご了承ください。また、当方では「完成品が欲しい」「組立作業を代行して欲しい」といったお問い合わせに応じることは出来ません。

自作キーボードのキットですので出来上がった完成品を使うことで得られる結果だけでなく、それを作る過程も含めて楽しんでいただけたら幸いです。

<br>

<br>

## 1：キット添付品の確認

**1）PCBとスイッチマウントプレート**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/003.JPG" width="640" />

- PCBにはWS2812Bが表面に3カ所、裏面に13カ所実装されています。

<br>

**2）アクリルプレート（３種類）**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/004.JPG" width="640" />

- 上から順にボトムプレート用、トップカバー用、底上げ用となります。

<br>

**3）ネジ・スペーサー類**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/005.JPG" width="640" />

①M2x12mmネジ：12本

②M2x5mmネジ：12本

③M2ワッシャー：8枚

④M2x3mmスペーサー：8本

⑤M2x4mmスペーサー：12本

⑥M2x12mmスペーサー：4本

⑦ゴム足：大3個、小3個

<br>

**4）Kailh PCBソケット（MXスイッチ用65個）**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/006.JPG" width="640" />

<br>

**5）ダイオード（75本）**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/007.JPG" width="640" />

<br>

**6）ProMicro（Mini-Bタイプ）、コンスルー、タクタイルスイッチ**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/008.JPG" width="640" />

- ProMicroにはデフォルトファームウェアを書込み済となっています。基板にバリが残っているので、側面に軽く紙やすりを掛けた上でゼブラの黒マッキー等で側面を黒塗りしておくことをお勧めします。

<br>

<br>

## **2：PCBへのダイオードの取り付け**

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/010.JPG" width="640" />

- 写真のように先が細いピンセットでダイオードの根元をつまんで足を直角に曲げていきます。なお、PCB側のダイオード用の穴は6.35mmの間隔で設計していますので、その穴にマッチするように曲げていってください。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/011.JPG" width="640" />

- このように両方の足を曲げたダイオードを全部で75本作っていきます。正直「面倒くさい」作業ですが、一つ一つのダイオードが全て役割を持っているということを感じていただけたら幸いです。

  <br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/012.JPG" width="640" />

- PCBの表面からダイオードを差し込んで行きます。なお「ASTRA 515」ではDuplexMatrixの配線をしている関係上、写真のように5個一組で交互に実装方向が反転しているのが特徴です。PCB表面のシルク印刷でも実装方向を明示していますが、原則として「四角い穴のある側に黒い印がくるように」と覚えていただければ結構です。

- 試しに方向の間違いがなく10本差し込んでみたら、表面からマスキングテープを貼ってダイオードを固定してみましょう。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/013.JPG" width="640" />

- PCBを裏返してニッパーでダイオードの足を切って行きます。切る長さですが、気持ち的には「ツライチ」にする感じでいいと思います。

- なお写真ではニッパーに100均の強力マグネットを貼り付けているため、切った足は自動的にマグネットに吸着されるようになっています。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/014.JPG" width="640" />

- 「ツライチ」のつもりで切っても僅かに表面に足が出た状態になります。個人的にはこれくらいが好みです。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/015.JPG" width="640" />

- スルーホール部品のハンダ付けでは必須ではないですが、軽くフラックスを塗布した上でハンダ付けを行います。なお、FX600での温度設定は終始320℃の設定で支障ありません。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/016.JPG" width="640" />

- これで最初のダイオード10個が実装されました。この後も10個づつ慎重に実装をしていくといいでしょう。なお、実装後のフラックス汚れは一段落ついた後でフラックス洗浄液で落とせば綺麗になります。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/019.JPG" width="1024" />

- 全てのダイオードの実装が完了すると写真のようになります。

- ここまでの工程で数時間は掛かっているはずなので、一旦休憩を入れた方がいいと思います。

<br>

<br>

## **3：PCBへのKailhソケットの取り付け**

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/020.JPG" width="640" />

- PCBを裏返しにしてKailhソケットをハンダ付けしていきます。難易度の低い部品ですが、表面実装のためパッドには必ずフラックスを塗布するようにしてください。

- この工程のソケット部品はFX600に標準添付のB型コテ先だと熱を伝えにくいのでC2やD16のように平面とエッジのあるコテ先の使用をお勧めします。コテ先に予めハンダを盛った状態でパッドと端子を加熱すると「ジョワっ」っという音と共にハンダがスムーズに流れ込んで行きます。

- 片側をハンダ付けしたら、基板を180度反転させて反対側からも同様にハンダ付けします。

- ハンダの消費量が多く煙が沢山出る作業なので、部屋の換気をしておいた方が良いと思います。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/021.JPG" width="1024" />

- 65個全てのソケットを実装すると写真のようなります。なお、中央下部のソケットの無い区画はロータリーエンコーダの実装やキーサイズ選択制の都合によりソケット非対応とさせていただいてます。

<br>

<br>

## **4：ProMicroの取り付け**

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/022.JPG" width="640" />

- PCBのProMicro取り付け箇所は写真のようになっています。大きめなMini-BタイプのProMicro（700mil幅）と通常サイズのProMicro（600mil幅）の両方に対応しているため2種類の幅の列に穴が用意されています。

- なお、添付品のMini-BタイプのProMicroでは外側の列の穴を使用します。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/023.JPG" width="640" />

- ProMicroにコンスルーを差し込みます。コンスルーの取り付け方向には決まりがありますので、写真を参考にして間違えないようにしましょう。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/024.JPG" width="640" />

- コンスルーを装着した状態でProMicroをPCBの穴に差し込みます。先に説明したとおり、Mini-BタイプのProMicroは幅が広いので外側の列の穴に差し込むようにします。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/025.JPG" width="640" />

- 間違いなく装着出来たら、写真のようにProMicro側だけコンスルーの足をハンダ付けします。くれぐれもコンスルーのPCB側はハンダ付けしないようにしましょう（二度と外せなくなります）

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/026.JPG" width="640" />

- 参考として600mil幅のProMicro（Elite-C）を装着した場合は、上の写真のように内側の列の穴を使用することになります。

<br>

<br>

## **5：スイッチマウントプレートの取り付け**

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/027.JPG" width="640" />

- ロータリーエンコーダを使用する場合は、プレートを装着する前に写真のようにプレートを金属ヤスリで軽く削っておくことをお勧めします。予めこの加工をしておけば、プレートを外すことなくロータリーエンコーダの交換が出来るようになります。

- なお、ロータリーエンコーダを使用せずにMXスイッチのみの構成とする場合は、上記の加工はしない方が良いです（MXスイッチの保持が甘くなってしまうため）

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/028.JPG" width="640" />

- プレートのネジ穴（8カ所）に写真のようにM2x8mmネジにM2ワッシャーを1枚通してM2x3mmスペーサーで締め付けます。なお、M2ワッシャーはプレート表面とPCB表面のクリアランスを約5mmになるように調整するために挟んでいます。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/029.JPG" width="1024" />

- 8カ所にネジ、ワッシャー、スペーサーを取り付けると上の写真のようになります。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/030.JPG" width="640" />

- プレートをPCBに被せます。なお、写真では先にロータリーエンコーダをPCBに差し込んでいますが、上記のプレート切削加工をしている場合は、後から差し込んでも構いません。

- なお、中央下段のキーを縦の2Uサイズとする場合はこの時点で2Uのスタビライザー（別売）をPCBに装着しておく必要があります。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/031.JPG" width="640" />

- PCBのネジ穴にプレートのネジが通ったら、PCB裏面からM2x4mmスペーサーで8カ所締めます。手でスペーサー強く締め込んでからプライヤーで掴んで45度程度右に回すと本締めとなります。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/032.JPG" width="640" />

- PCB上部の両端4カ所にM2x12mmスタッドスペーサーをM2x4mmスペーサーで取り付けます。

<br>

<br>

## **6：キースイッチの取り付け**

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/033.JPG" width="640" />

- 上の写真のようにソケット非対応の区画にキースイッチをセットしていきます。なお、キーサイズ選択制の都合により、一部のキースイッチは上下逆方向に取り付けるようになっていますのでご注意ください。

- また、ロータリーエンコーダの代わりにMXスイッチを使用する場合は、3ピンタイプのスイッチでないと入りません。Gateron等の5ピンタイプのスイッチを使う場合はプラスチックの保持ピンをニッパーでカットしてからセットしてください。

- なお、キースイッチの取り付け方向を判別するためにPCBとプレートにキーサイズの表記されています。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/034.JPG" width="1024" />

- 続いてソケット対応の区画にキースイッチをセットしていきます。ソケットの場合は無理にスイッチを押し込んで接点のピンが曲がったりしないように注意してください。ハンダ付けと違って失敗しやすい箇所ですのでご注意ください。

- ソケットにスイッチが正しくセットされていることを確認するために、この時点で一旦PCに接続して押したスイッチが反応することを確認しておくと良いでしょう。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/035.JPG" width="640" />

- 基板を裏返して、キースイッチとロータリーエンコーダのハンダ付けをします。なお、ロータリーエンコーダのピンは手前側3カ所と奥側2カ所のピンをハンダ付けすれば十分な強度が得られるので、後で交換する可能性がある場合は左右の保持ピンはハンダ付けしない方が良いと思います。

<br>

<br>

## **7：アクリルプレートの取り付け**

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/036.JPG" width="1024" />

- スイッチ類のハンダ付けが完了したら、写真のようにアクリルのボトムプレートと底上げ用プレートを被せてM2ネジで止めていきます。手前側の8カ所はM2x5mmネジ、奥側両端の4カ所はM2x8mmネジを使用します。

- この時点でゴム足もアクリルプレートに貼付します。手前側にゴム足（小）を、奥側にゴム足（大）を使いますが、奥側は剛性が高く打鍵感が堅くなりやすいので、両端の2カ所だけでいいかも知れません。

（註：写真では試作の無刻印ボトムプレートですが、キットには刻印入りのボトムプレートを添付しています）

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/037.JPG" width="640" />

- 最後にキーキャップを取り付けて、トップカバー用のアクリルプレートをM2x5mmネジで取り付けます。

<br>

<br>

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/038.JPG" width="800" />

- 以上で組立は終了です。お疲れ様でした。

- ProMicroにはデフォルトキーマップを書き込んでありますので、全てのキーが正しく反応するかチェックしましょう。

<br>

（デフォルトキーマップとQMKファームウェアについては[**別項**](https://github.com/Lekipon/ASTRA515/blob/master/doc/firmware.md)にて記載します）

<br>