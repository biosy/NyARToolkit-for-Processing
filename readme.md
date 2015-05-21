# NyARToolkit for proce55ing

Copyright (C)2008-2012 Ryo Iizuka

http://nyatla.jp/nyartoolkit/  
airmail(at)ebony.plala.or.jp  
wm(at)nyatla.jp  


## NyARToolkit for Processing

* NyARToolkit for proce55ingは、processing環境下でNyARToolkitを利用するためのライブラリです。
* 拡張現実感ライブラリには、ARToolKitの派生ライブラリNyARToolKit for Javaを使用しています。
* Processing version 2.2.0での動作を確認しています。 (1.x系は古いライブラリを使ってください。)
* このライブラリは、processingのcamera()関数で取り込んだ画像や、PImage画像を元にマーカ検出処理を実行できます。
* レンダリングシステムには、OPENGLとPV3Dをサポートします。


## NyARToolkit for proce55ingの特徴

* 左手系・右手系両方の座標系をサポートします。
* マルチマーカ、シングルマーカののユースケースに対応します。
* NyIdマーカ、ARToolKitマーカの両方に対応します。
* 自動敷居値に対応しています。(一部のみ)
* パターン取得、スクリーン座標のマーカ座標変換等が手軽に使えます。
* レンダリングにProcessingCoreAPIのみを使います。Graphics3D派生オブジェクト全てに対応します。

## 環境の準備

1. NyARToolkit for proce55ingの実行には、processing/1.5.1、又は2.0b以上が必要です。Processingのウェブサイトからダウンロードして下さい。
  (http://processing.org/download/index.html)
  
2. ProcessingのCapture機能を使用できるようにコンピュータを設定してください。Capture機能は、ProcessingのExamples>Libraries>Video(Capture)以下のサンプルの動作で確認できます。
（このステップは、キャプチャ機能を使わないときには必要ありません。）

3. ProcessingからOpenGL機能を使用できるように、コンピュータの設定をして下さい。OpenGL機能は、ProcessingのExamples>Libraries>OpenGL以下のサンプルの動作で確認できます。（このステップは、レンダリングにP3Dを使用するときには必要ありません。）

4. 以上で準備は完了です。


## サンプル実行

exampleにある、simpleLiteのサンプルの実行手順です。simpleLiteは、Hiroマーカの上に立方体を表示するシンプルなプログラムです。

1. dataディレクトリにある、pattHiro.pdfを印刷しておいてきます。
2.example/simpleLiteにある、simpleLite.pdeを開いて実行してください。マーカを撮影すると、そこに立方体が表示されるはずです。

他のサンプルについても、同様の手順で試す事ができます。


## スケッチの作り方

NyARToolkitを使ったスケッチには、2つのjarライブラリと、使用するマーカのパターンファイル、カメラのパラメータファイルが必要になります。

マーカファイルとカメラパターンファイルは、ARToolKitの仕様に沿ったものを用意して、スケッチのdataフォルダの中に配置します。
 
ライブラリは、libraryフォルダの中にある2つのファイルを、codeフォルダの中に配置します。

## NyARToolkit for Processingの提供するクラス

 NyARToolkit for proce55ingは、ユースケース毎に、機能の異なる複数の
 クラスを提供しています。

* NyARBoradクラス（NyARBoard.java）  
1種類のARマーカを認識するクラスです。
* SingleARTKMarkerクラス（SingleARTKMarker.java）  
複数のARマーカを登録し、そのうちの1個を認識するクラスです。自動敷居値調整と、簡易トラッキング機能を備えます。
* SingleNyIdMarkerクラス（SingleNyIdMarker.java）  
 Idマーカを同時に1個認識するクラスです。Idの仕様は、NyId形式です。
* MultiMarkerクラス (MultiMarker.java)  
 ARマーカ、NyIdマーカを複数個同時に扱えるクラスです。このクラスを使えば、上記の3クラスは不要かもしれません。

## その他

* パターンファイルやカメラパラメータファイルについて  
NyARToolKit for Processingの使用するカメラパラメータファイル、パターンファイルは、ARToolKitと完全な互換性があります。  
現在のライブラリには、これらを作成する機能がありません。ARToolKit、またはFLARToolKitの機能を利用して作成してください。

## ライセンス

* LGPLv3での提供になります。但し、src以下のファイルをのみを使用する場合には、MITライセンスでも使用できます。
* パッケージに含まれるNyARToolkitのソースファイルは、(https://github.com/nyatla/NyARToolkit/)よりダウンロードできます。
