## *ASTRA 515:A Symmetrical 5x15 Ortholinear Keyboard*

<img src="https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/astra515_01.JPG" alt="Astra515_1" style="zoom:50%;" />

------

![](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/doc/img/astra515_02.JPG)

------

## **概要**

ASTRA 515は一体型の60％キーボードと同じサイズで5x15のオーソリニア（格子配列）となっている自作キーボードです。組立の難易度は決して高くないですが、キー数が多い故にハンダ付け箇所が多い点にご了承ください。

なお、ファームウェアはQMKを使用します。



## 特徴

- Promicro1個だけで可能な限り多くの実装をするためにDuplexMatrixの配線手法を利用。

- 左右の手のホームポジションの間隔を適度に離し、使用頻度の少ないキーを中央の区画に寄せた対称型オーソリニアレイアウト（All1U構成にすれば片側寄せの非対称型のレイアウトも可能ですが...）

- スイッチ付きロータリーエンコーダー（アルプスEC11/EC12互換）を2つ搭載可能
- 好みに応じて親指周辺のキーを「1Ux3」または「1.5Ux2」の構成を選択可能（上の見本写真を参照）。また、中央のキーを縦の2U構成に変更することも可能（凸型配置のカーソルキーが不要な人向け、一般的にはAll1Uの構成を推奨します）

- RGBLED（WS2812B）による3連インジゲータの発光で「CapsLock」「NumLock」の状態を表示。また発光色によりレイヤーの状態を表示

- RGBLEDのアンダーグロウに対応。なお、ハンダ付けの難易度がやや高いRGBLEDのみはPCBに実装済み

- Kailhソケットにより大部分の区画がキースイッチの交換に対応（※中央下段の一部の区画を除く）
- 標準添付のPromicroはUSBコネクタが「もげる」心配の無いmini-Bタイプを採用（※別売となりますが普通のPromicroやElite-Cも使用出来ます）



## キットに入っている部品

1：PCB 1枚（RGBLEDを表面に3カ所、裏面に13カ所実装済）

2：スイッチマウントプレート

3：アクリルプレート3種（ボトムプレート用、トップカバー用、底上げ用、各1枚）

4：M2x8mmネジ（12本）

5：M2x5mmネジ（12本）

6：M2ワッシャー（8枚）

7：M2x12mmスタッドスペーサー（4本）

8：M2x4mmスペーサー（12本）

9：M2x3mmスペーサー（8本）

10：ゴム足（小3個、大3個）

11：Kailh PCBソケット（MX用・65個）

12：ダイオード（リードタイプ・75個）

13：Promicro（Mini-Bタイプ・1個）および12ピンコンスルー（2本）

14：4ピンタクタイルスイッチ（リセットスイッチ用・1個）



## キットとは別に用意が必要な部品

1：Cherry MX互換キースイッチ（All1U構成の場合・73個）

2：キーキャップ（All1U構成の場合・73個）

3：スイッチ付きロータリーエンコーダおよびツマミ（各2個）なお、ロータリーエンコーダを使用しない場合はキースイッチとキーキャップの必要数は各75個となります。

4：USBケーブル（Mini-Bタイプ・1本）



## 必要な工具類

- ハンダごて（HAKKO FX600を推奨・別売コテ先はT18-C2かT18-D16がおすすめ）
- ハンダこて台
- 先が細いピンセット（ダイオードの足を曲げる際に必要）
- 普通のハンダ（スズ60％/鉛40％）およびハンダ吸い取り線
- フラックス（洗浄液もあるとなお良し）
- 精密ドライバーセット（100均のものでOK）
- マスキングテープ
- ニッパー
- プライヤー



## ビルドガイド

（工事中...）