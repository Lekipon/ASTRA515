

# デフォルトキーマップとQMKファームウェアについて



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
- 右手のホームポジションから指を動かすことなくカーソル移動が出来る設定になっていますが、PCゲームの「WASD」やVimの「HJKL」といったデファクトスタンダートなカーソル移動方法に慣れている人にとっては、かなり使いにくいかも知れません。
- 作者個人は過去にEmacsを使っていたこともあって「H」の位置に「B/S」そして「G」の位置に「Esc」を割り当てたいという事情もあってこのような「JKL;」の位置でカーソル移動させるレイアウトを採用させていただいています。
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

- QMKの[本家](https://github.com/qmk/qmk_firmware)には「ASTRA515」のコードはまだマージされていませんので、当面の間は[このフォークしたQMK](https://github.com/Lekipon/qmk_firmware)を使用してください。

- QMKのビルド環境の構築方法については、各自のOS環境に合わせて調べていただくようお願いします。特にWindowsでMSYS2環境内に構築する方法はトラブルが報告されているようなので、作者自身もあまり自信ありません（復習のために後日に[公式ドキュメント](https://docs.qmk.fm/#/ja/newbs_getting_started)を参照して実験してみる予定ですが）。

- 既にQMKファームウェアのビルド環境を構築をしている方は、ダウンロードしたqmk_firmware-master.zipを解凍して、出来上がった「qmk_firmware-master/」フォルダの中から「keyboards/lekipon」以下の中身をご自身のビルド環境にコピーしても大丈夫だと思います

  （lekiponフォルダには作者が他に開発したキーボードのファームウェアも一緒に入っています）。

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

- ご自身でキーマップをカスタマイズする場合は「keyboards/lekipon/astra515/keymaps/」内で「default」フォルダを別の名前にコピーして「keymap.c」をテキストエディタで編集してください。

- なお、動作確認の為にデフォルトの[HEXファイル](https://raw.githubusercontent.com/Lekipon/ASTRA515/master/hex/lekipon_astra515_default.hex)を用意していますが、標準添付のProMicroに書込済のものと同様になります。

<br><br><br>

（以下、必要に応じて随時追記するかも...）