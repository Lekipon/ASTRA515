# ASTRA515 ビルドガイド

この度は「ASTRA 515」をお買い上げいただきましてまことにありがとうございます。
このキーボードキットは<u>5行x15列の格子配列で設計されたキーボード</u>です。作者自身が一般的なキーボードの「行ごとに横にずれた」物理配列に対して漠然とした疑問を感じていたことが設計の動機になっています。

ファームウェアについては [QMK Firmware](https://github.com/qmk/qmk_firmware) を採用しており、多少のスキル・慣れは必要ですがユーザー自身で自由に各キーの割り当てを変更することが出来ます。

なお、このキットは初歩的なハンダ付けを含む組立が必要です。

ハンダ付けの難易度が高いRGBLEDに関しては予め手作業で実装した状態で梱包しておりますが、比較的キー数が多く実装部品も多いため、正直言って「簡単だけど面倒くさい」キットとなっている点はご了承ください。

自作キーボードは完成品を使うことで得られる成果だけでなく、それを作る過程も含めてキーボードライフを楽しんでいただけたら幸いです。



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



**6）Promicro（Mini-Bタイプ）、コンスルー、タクタイルスイッチ**

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/008.JPG" style="zoom:50%;" />

・Promicroにはデフォルトファームウェアを書込み済となっています。基板にバリが残っているので、側面に軽く紙やすりを掛けた上でゼブラの黒マッキーで側面を黒塗りしておくことをお勧めします。



## **2：PCBへのダイオードの取り付け**

・写真のように先が細いピンセットでダイオードの根元をつまんで足を直角に曲げていきます。なお、PCB側のダイオード用の穴は6.35mmの間隔で設計していますので、その穴にマッチするように曲げていってください。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/010.JPG" style="zoom:50%;" />



・このように両方の足を曲げたダイオードを全部で75個作っていきます。正直「面倒くさい」作業ですが、一つ一つのダイオードが全て役割を持っているということを感じていただけたら幸いです。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/011.JPG" style="zoom:50%;" />



・PCBの表面からダイオードを差し込んで行きます。なお「ASTRA 515」ではDuplexMatrixの実装をしている関係上、写真のように5個づつ実装方向が反転しているのが特徴です。PCB表面のシルク印刷でも実装方向を明示していますが、原則として**「四角い穴のある側に黒い印がくるように」**と覚えていただいても結構です。

・試しに方向の間違いなく10本差し込んでみたら、表面からマスキングテープを貼ってダイオードを固定してみましょう。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/012.JPG" style="zoom:50%;" />



・PCBを裏返してニッパーでダイオードの足を切って行きます。切る長さですが、気持ち的には「ツライチ」にする感じでいいと思います。

・なお写真ではニッパーに100均の強力マグネットを貼り付けているため、切った足は自動的にマグネットに吸着されるようになっています。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/013.JPG" style="zoom:50%;" />



・「ツライチ」のつもりで切っても僅かに表面に足が残ります。個人的にはこれくらいが好みです。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/014.JPG" style="zoom:50%;" />



・スルーホール部品では必須ではないですが、軽くフラックスを塗布した上でハンダ付けを行います。なお、FX600での温度設定は終始320℃設定で支障ありません。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/015.JPG" style="zoom:50%;" />



・これで最初のダイオード10個が実装されました。この後も10個づつ慎重に実装をしていくといいでしょう。

・なお、実装後のフラックス汚れは一段落ついた後でフラックス洗浄液で落とせば綺麗になります。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/016.JPG" style="zoom:50%;" />



・全てのダイオードの実装が完了すると写真のようになります。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/019.JPG" style="zoom:50%;" />

ここまでの工程で数時間は掛かっているはずなので、一旦休憩を入れた方がいいと思います。



## **3：PCBへのKailhソケットの取り付け**

・PCBを裏返しにしてKailhソケットをハンダ付けしていきます。難易度の低い部品ですが、表面実装のためパッドには必ずフラックスを塗布するようにしてください。

・この工程のソケット部品は標準のB型コテ先だと熱を伝えにくいのでC2やD16のように平面とエッジのあるコテ先の使用をお勧めします。コテ先に予めハンダを盛った状態でパッドと端子を加熱すると「ジョワっ」っという音と共にハンダがスムーズに流れ込んで行きます。

・片側をハンダ付けしたら、基板を180度反転させて反対側も同様にハンダ付けします。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/020.JPG" style="zoom:50%;" />



・写真のように合計で65個のソケットが実装されます。なお、中央下部のソケットの無い区画はロータリーエンコーダの実装やキーサイズ選択制の都合によりソケット非対応とさせていただいてます。

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/021.JPG)







（以下、作成中・・・）



