

# ProMicroの換装について・他

- ASTRA 515では一般的な自作キーボードキットと違い、標準添付のProMicroはやや大ぶりなMini-Bタイプのものとさせていただいています。理由は以下の通りとなります。
  - 基板のレイアウトが大柄な故にProMicroの設置場所に余裕があった。
  - HHKB等の市販品でケーブル脱着式のキーボードでは、長年の間Mini-Bコネクタが標準だった（現在の市販キーボードではMini-BからType-Cコネクタに移行する過渡期）。
  - 安価なProMicroではMicroUSBコネクタが「もげる」問題に根本的な対策がされていない。<br>

- 上記の事情でMini-Bタイプを採用していますが、一般的な[ProMicro](https://yushakobo.jp/shop/promicro-spring-pinheader/)や[Elite-C](https://yushakobo.jp/shop/elite-c/)も使用可能なように設計してあります。MicroUSBコネクタは「もげる」問題があるので、換装の際はElite-Cを推奨しますが、MicroUSBケーブルを使いたい事情がある場合は、ProMicroのUSBコネクタをエポキシ接着剤等で補強して使用してください。
- なお、遊舎工房さんで取り扱っているProMicro（コンスルー付きで1,100円）について、少しだけ朗報があります。詳細は以下の比較写真をご覧いただければ分かりますが、USBコネクタがの実装が強化されています。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/040.JPG" width="640" />

・USBコネクタの実装が表面実装からスルーホール実装に変更されています。また、基板の表面仕上げが艶ありから艶消しになっています。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/041.JPG" width="640" />

・スルーホール化されたとはいえ2カ所止めのままでは不安が残るので、結局は写真のようにエポキシ接着剤でコネクタ周辺を補強して使うことになります。強化されたこと自体よりも、補強の際に接着剤がコネクタ内部に流入しにくくなったというメリットの方が大きいかも知れません。

<br>

- 下の写真は標準添付のProMicroを取り付けた状態となります。

  <img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/042.JPG" width="640" />

<br>

- これをElite-Cに換装した場合は以下の写真のようになります。<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/043.JPG" width="640" />

  ・ProMicroとの大きさの違いにより、Type-Cコネクタが奥まった位置になる点にご注意ください。

<br>

- この状態でL型のType-Cケーブルを使う場合は下の写真のように、コネクタの突き出し量が12mm以上あるものを使用してください。余談ですが、写真のケーブルはダイソーで売ってるType-Cケーブルです。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/044.JPG" width="640" />

<br>

<br>

------

- なお、標準添付のProMicroはVCCの赤色LEDの照度が強いため、マットのアクリルプレート越しでも目障りに感じる方もいるかと思います。
- その場合は、あくまで自己責任となりますが、LEDに繋がっている抵抗を除去してLEDを点灯しなくするという処置が可能です。ついでにスタンバイ電力も2mA程度の削減になります。

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/045.JPG" width="640" />

- 抵抗は表面実装部品なので、半田ゴテの二刀流が必要となります（30W程度あれば2本ともFX600である必要はありません）。抵抗の両側からコテ先で同時に加熱して横滑りさせるように力を掛ければ簡単に外れます。

- 間違っても隣接する部品にコテ先を当てないように注意しましょう。

  <br>

  <br>

  （以上）

  