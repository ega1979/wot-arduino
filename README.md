# Arduino向けWoTフレームワーク

これはArduino向けC言語で書かれたWoTフレームワークの実験的な実装になります。このプロジェクトは[WoT向けNodeJSサーバー](https://github.com/w3c/web-of-things-framework)の姉妹的なプロジェクトである。

10億ものIoTデバイスが今後の10年を通して世の中に出されることが期待されています。たくさんのIoTプラットフォーム存在し、IoTテクノロジーの数もどんどん増えていっています。しかし、IoTプロダクトは現在サイロな（それぞれが孤立した）状態であり、相互運用性（互換性）が欠如していことに問題を抱えています。W3Cでは　共通のフレームワークを通じて接続され、そしてマイクロコントローラーからスマートフォンやスマートホーム／オフィスのハブまで様々なスケールで利用可能であり、かつクラウドをベースとしたサーバ群であるWebサーバの新しいクラスを介したWorld Wide Web（www）を通してIoTプラットフォームとデバイスがどうしがブリッジできるような可能性を模索しています。

このフレームワークは物理的かつ抽象的な存在のもののためのプロキシーとして（”things”）という仮想オブジェクトを含んでいます。
どんなプロトコルも一つですべてのニーズを満たすことはないので、このthingsはスクリプティングAPIや様々なプロトコルとバインディングしてメタデータ、イベント、プロパティそしてアクションの観点からモデル化されています。
このサーバはMQTTやCoAPにバインディングして始まります。

## 技術詳細

UnoのようなArduinoボードはRAMやFlashメモリなどに対しては非常に限られたものです。IPに繋がる可能な範囲があります。
Arduino Ethernetシールドは非常に資源が集約されています。ワイヤレスにかんしては、ESP8266を低消費のWiFi接続で使うことができます。もしあなたがIP接続が必要ないならRF24L01+を端末間もしくはメッシュネットワークで使うことができます。ほかにも可能性としてBluetoothとかZigbeeが含まれます。

web of thingsサーバは非常に制約がありますが、単一のセンサとアクチュエータと一緒に利用することができます。IP接続をすると仮定すれば、CoAPとMQTTは通信プロトコルにとっては良い選択です。このプロジェクトはプロトコルの詳細を扱う必要がなくあなたが単一のセンサとアクチュエータのドライバーを書くことが許されるでしょう。デベロッパーはセンサとアクチュエータをよりパワフルなサーバのところで記述できるようになり、そこではWeb of Thingsフレームワークがプロキシオブジェクトとその代わりに動くオブジェクトとの間をつなぐ役割となる
でしょう。

## 前提条件

 *我々がビルドし、実行できるコードをいくつか確保される時、決定されること。
  
## インストール方法
出発点はGitをインストールすることで、以下のとおり：

  http://git-scm.com/book/en/v2/Getting-Started-Installing-Git

次はこのディレクトリのコピーを創り、以下のとおり変更しましょう。

```
  git clone https://github.com/w3c/wot-arduino
  cd wot-arduino
```

## 寄稿

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/w3c/web-of-things-framework?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

We welcome contributions. If you find a bug in the source code or a mistake in the documentation, you can help us by submitting an issue to our [GitHub repository](https://github.com/w3c/arduino-wot), and likewise if you have suggestions for new features. Even better you can submit a Pull Request with a fix. We also have a Gitter chat channel, see above link.

We encourage you to join the W3C [Web of Things Community Group](https://www.w3.org/community/wot/) where contribution and discussions happen. Anyone can join and there are no fees.

The amount of time you contribute and the areas in which you contribute is up to you. 

## License

(The MIT License)

Copyright (c) 2015 Angelos Kapsimanis &lt;angelos.kapsimanis@gmail.com&gt;

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
