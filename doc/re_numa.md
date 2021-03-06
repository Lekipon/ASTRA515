

## ロータリーエンコーダの選定について（沼）

- ASTRA 515では当初からロータリーエンコーダを2カ所に搭載するように設計していますが、必ずしも付けなければならないという訳ではありません。最初は全てMX互換スイッチを実装して5x15Ortho配列のキーボードとして使い、配列に慣れてからロータリーエンコーダに換装するというのも有りだと思います。

- 作者自身は仕事で[XD75re](https://kprepublic.com/collections/xd75/products/xd75re-xd75am-xd75-xiudi-60-custom-keyboard-pcb?variant=958306091052)を使用していて、そこから出てきた不満点を洗い出した上でASTRA515を設計したという経緯があるので、最初からロータリーエンコーダを付けていますが、５ピンのロータリーエンコーダは一度ハンダ付けすると外すのにコツが必要なので、初めての人はすぐに実装しない方がいいかも知れないとも考えてます（今更ながらですいません・・・）。

- ということで、ロータリーエンコーダをいくつか試してみて検証しましたので、以下にレビューを記載させていただきます。他の自作キーボードキットでロータリーエンコーダを使用する場合にも参考になるかと思います。

  <br>
  
  

**1）遊舎工房さんで取り扱っている[ロータリーエンコーダ＆ノブセット](https://yushakobo.jp/shop/pec12r-4222f-s0024/)**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/050.JPG" width="640" />

・Bourns社製の「PEC12R-4222F-S0024」とサトーパーツ社製の「K-29-6.1」アルミ削り出しノブのセットとなります。ノブだけでも単品で買うと350円とかする代物なので、なかなかのお買い得セットともいえます。

・PCB面からシャフト先端までの全高は22.5mmで、自作キーボードでの使用を考慮してやや短めのシャフトのとなっています。

・セットのノブは非常にシンプルな形状ながらも良好なグリップ感・・・特に側面と天面のエッジ部分の摩擦力が適正で、非常に実用的な選択だと思います。

・このセットではロータリーエンコーダが24パルス/24クリックのため、QMKファームウェアの「#define ENCODER_RESOLUTION」の値はデフォルト値の「4」の設定で使用します。

・実際に使った使用感ですが、プラスチックのシャフトながらも回した時の金属的なクリック感がなかなか心地よい感触です。あまりハードな使い方をしない前提なら、これで十分ではないかと思います。

・ただ、欲とは深いもので「親指一本でコロコロ回したいな～」とか「丈夫な金属シャフトのものを使いたい」といった欲が出てくると、以下のようにロータリーエンコーダ沼になってくるので十分に注意してください。



#### **2）アルプス EC11E18244A5**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/051.JPG" width="640" />

・PCB面からシャフト先端までの全高は24.5mm。プッシュスイッチは1.5mmと長いストロークで、柔らかいタッチが特長です。モノタロウやRSコンポーネンツで一個600円前後で売っています。

・18パルス/36クリックのため、QMKファームウェアの「#define ENCODER_RESOLUTION」の値は「2」の設定となります。具体的にはキーマップフォルダ内のconfig.hに当該セクションがありますので、設定値を「2」にしてファームウェアをビルドして使用します。

・EC11Eシリーズはこれがもっともシャフトが短い製品となりますので、このままでは自作キーボードで使用するには長すぎるという問題があります。ということで・・・<br>

#### **EC11Eのシャフトを斬る！**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/052.JPG" width="640" />

・金鋸を使用する際にはロータリーエンコーダの駆動部にダメージを与えないようにするために、必ずシャフト先端側をクランプしてカットします。

<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/053.JPG" width="640" />

・5mmほどカットすれば、全高は約20mm弱。カット後はシャフトの先端のエッジ部分をヤスリで軽く面取りして仕上げます。自作キーボードでキーと隣接している状態ではこれくらいの低さが丁度いいくらいです。

・余談ですが、写真の工具は[スーパーツール社製のSG225](https://www.supertool.co.jp/products/products.php?eid=00084)。いわゆるバイスグリップ系の工具では世界的にも珍しい開口幅切り替え式が特長です。このシリーズの工具は個人的に何かと出番が多くて長年使っています。現在ではAmazonで2,200円で買えるので、一本持っておいても損はないと思います。

<br>

#### **3）Bourns PEC11R-4015F-S0024**<br><img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/054.JPG" width="640" />

・PCB面からシャフト先端までの全高は21.5mm（シャフト長が15mmでベース部分の高さが6.5mm）。プッシュスイッチは樹脂シャフトのPEC12Rシリーズ同様に0.5mmストロークの堅いタッチです。マルツオンライン等で一個250円前後で売っています。

・実は24パルス/24クリックの「PEC11R-4215F-S0024」と間違えてノンクリックの物を買ってしまい、これは失敗したなと思ったのですが・・・回転がとても軽くスムーズで指一本で簡単に回せるので逆に好都合でした。

・24パルス/ノンクリックのため、QMKファームウェアの「#define ENCODER_RESOLUTION」の値はクリック数を気にせずに自由に設定出来ます。例えば「2」に設定すると1回転で48回、「3」に設定すると1回転で32回、「4」に設定すると1回転で24回、といった出力回数となります。

・金属シャフトのPEC11Rシリーズではこれがもっともシャフトが短い製品となりますので、キーキャップの低さやノブの高さによっては、アルプスEC11E同様にシャフトを若干カットする必要が出てきます。<br>



#### **4）アルプス EC11E1834403**<br><img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/055.JPG" width="640" />

・先に紹介した「EC11E18244A5」のノンクリック版。これもプッシュスイッチは1.5mmと長いストロークで、柔らかいタッチです。モノタロウやRSコンポーネンツで一個600円前後で売っています。

・18パルス/ノンクリックのため、QMKファームウェアの「#define ENCODER_RESOLUTION」の値はクリック数を気にせずに自由に設定出来ます。例えば「2」に設定すると1回転で36回、「3」に設定すると1回転で24回、「4」に設定すると1回転で18回、といった出力回数となります。

・こちらはノンクリックとはいえ、残念ながら中のグリスが堅いのか回転がかなり重いです。ただ、使い込むうちに次第に軽くなってくる傾向があるので。今後使い込んで馴染ませてみたいと思います。

<br>



## ノブの選択について（更なる沼）

- 上記でロータリーエンコーダについて数点のレビューをしましたが、ノブに関してはネジ止めで簡単に交換できる代わりに「実際に付けてみないと分からない」という要素がかなり発生します。奮発して買った高価なアルミ削り出しノブがイマイチで、安価な樹脂製ノブの方が良かったなんてことは茶飯事です。

- 一般に15mm径のノブなら周辺のキーの打鍵を妨げることはありませんが、18～19mm径クラスの大径ノブを使用すると隣接するキーが打ちづらくなるため、より低く装着する必要が出てきます。

- 現時点で下の写真のノブを試していますが、今後も徐々に増えていく可能性は十分あります。

  <img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/056.JPG" width="640" />

  <br>

  ・ここでは、実際に試したもののうち、いくつか写真付きでレビューしたいと思います。なお、ASTRA515に装着した見本写真では、PEC11R-4015F-S0024（全高21.5mm）とMX互換スイッチ、DSAキーキャップの組み合わせとなっています。

<br>

#### **1）サトーパーツ K-29-6.1**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/057.JPG" width="640" /><br>

・詳細は[こちら](http://www.satoparts.co.jp/JPN/item/K/K-29-6.1/)。遊舎工房さんのロータリーエンコーダセットの添付品でもあります。

・見た目的な面白みはありませんが、エッジ部分の摩擦力が適正なため、指一本での回転操作にもある程度対応できます。

#### <br>**2）Linkman CP-CE15-5-S(6.1)W6**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/058.JPG" width="640" />

・詳細は[こちら](https://www.marutsu.co.jp/pc/i/837992/)。秋葉原の電子部品ショップでよく扱っている安価なノブです。グレーの他に黒色もあります。

・これも、エッジ部分の摩擦力が適正なところが良いと思います。また、グレー系のキーキャップに近い色で外観的にしっくりくるという良さもあります。

・取り付けの穴が結構深くて、プッシュスイッチと干渉しやすいので、あまり低く取り付けられないという欠点はあります。

<br>

#### **3）サトーパーツ K-4071**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/059.JPG" width="640" />

・詳細は[こちら](http://www.satoparts.co.jp/JPN/item/K/K-4071/)。マルツオンライン等で扱っています。

・大径でかつエッジ部分の摩擦力が適正、低く取り付け出来るためDSAのキーキャップとの相性も良いです。ただし、見た目が安っぽいのが一番の難点で色も黒しか有りません。実用性最優先の選択となります。

<br>

#### **4）サトーパーツ K-52-KE-3**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/060.JPG" width="640" />

・詳細は[こちら](http://www.satoparts.co.jp/JPN/item/K/K-52-KE-3/)。マルツオンライン等で扱っています。

・大径ですが、エッジ部分の摩擦力があまり強くないです、低く取り付け出来ることと、外観が安っぽくないというのが良い点だと思います。

<br>

#### **5）サトーパーツ K-38（中）**<br>

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/061.JPG" width="640" />

・詳細は[こちら](http://www.satoparts.co.jp/JPN/item/K/K-38/)。マルツオンライン等で扱っています。

・中サイズだと直径19mmでMXのキーピッチとマッチします。エッジ部分の摩擦力という点では最強ともいえます。ただし、断面図を見ての通り穴が浅いため低く取り付け出来ないという欠点があります。これはSAやMDAのような背の高いキーキャップと組み合わせて使うべきかと思います。

・削り出しのエッジが鋭いため、日々のエタノール消毒で肌荒れした指先には少々辛いという問題もあります。

<br>



<br>

（以上、必要に応じて随時書き足すかも）

