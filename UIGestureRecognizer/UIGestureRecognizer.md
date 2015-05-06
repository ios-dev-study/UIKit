https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIGestureRecognizer_Class/index.html#//apple_ref/occ/instm/UIGestureRecognizer/numberOfTouches

# UIGestureRecognizer

UIGestureRecognizerはgesture-recognizerの具象クラスの抽象基底クラスです
gesture-recognizerオブジェクト、あるいは単にgesture recgnizerは、
ジェスチャーを認識するロジックと、認識した上で動かすロジックを分離します。



 オブジェクトの1つが、共通のジェスチャーを認識すると、指定した
 ターゲットオブジェクトにアクションメッセージを送信します。


 UIGestureRecognizerの具象クラスは以下

* UITapGestureRecognizer
* UIPinchGestureRecognizer
* UIRotationGestureRecognizer
* UISwipeGestureRecognizer
* UIPanGestureRecognizer
* UIScreenEdgePanGestureRecognizer
* UILongPressGestureRecognizer



UIGestureRecognizerクラスは、すべての具象クラスのgesture recognizerに構成される
共通の振る舞いを定義しています。
UIGestureRecognizerDelegate プロトコルを使えば、コミュニケーションできます。

gesture recogniezierは、指定のViewとそのViewのサブViewを操作します。

associationを作るには、UIViewメソッソドのaddGestureRecognizerを呼ぶ。



以下はGoogle翻訳しただけです。



ジェスチャ認識、つまり、UIGestureRecognizeの具象クラスのインスタンス-は、
アプリのジェスチャー認識の振る舞いを微調整するために、
UIGestureRecognizerDelegateプロトコルを採用します。

このデリゲートは、gesture recognizerからメッセージを受け取ります。
それらのメッセージのレスポンスは


ジェスチャ認識は、それに関連付けられた1つ以上のターゲット·アクションの組を有します。
複数のターゲット·アクションのペアが存在する場合、
それらは個別の、累積されません。
関連する対の各々のためのターゲットにアクションメッセージのディスパッチでジェスチャー結果の認識。
呼び出されたアクション·メソッドは、次の署名のいずれかに準拠している必要があります：

```swift
func handleGesture() { }
func handleGesture(gestureRecognizer: UIGestureRecognizer) { }
```

後者のシグネチャに準拠した方法は、追加の情報については、
メッセージを送信するジェスチャ認識装置を照会するためにいくつかのケースでは、ターゲットを可能にします。
例えば、標的は、このジェスチャーのためのアクションメソッドの最後の呼び出し以来（ラジアン）の回転角に対するUIRotationGestureRecognizerオブジェクトを求めることができます。
またはlocationOfTouch：ジェスチャ認識装置のクライアントもlocationInViewを呼び出して、
ジェスチャの位置を求めることができるのInViewを:.

ジェスチャ認識によって解釈ジェスチャーは、離​​散または連続的のいずれかであることができます。
例えば、ダブルタップのような個別のジェスチャは、
マルチタッチシーケンスと送信される単一のアクションで結果ではなく、1回発生します。
マルチタッチシーケンスが終了するまでは、ジェスチャ認識装置は、
回転ジェスチャとして連続ジェスチャを解釈する場合には、各増分の変更のアクションメッセージを送信します。

それがジェスチャ認識に取り付けられたヒットテストさビューに配信する前に、
ウィンドウには、ジェスチャ認識にタッチイベントを配信します。
ジェスチャ認識は、マルチタッチシーケンス内のタッチの流れを解析し、
そのジェスチャーを認識しない場合、一般的に、ビューはタッチの完全な補完を受け取ります。
ジェスチャ認識は、そのジェスチャーを認識した場合、ビューの残りのタッチが解除されます。
ジェスチャ認識のアクションの通常のシーケンスは
cancelsTouchesInView、delaysTouchesBegan、delaysTouchesEndedプロパティのデフォルト値によって決定された経路をたどります。

cancelsTouchesInView
ジェスチャ認識は、そのジェスチャーを認識した場合、それは彼らの見解（そのウィンドウはそれらを配信しません）から、そのジェスチャの残りのタッチをアンバインドします。 withEvent :)メッセージ：ウィンドウが（ touchesCancelledを使用して、以前に配信さのタッチを解除します。ジェスチャ認識は、そのジェスチャを認識しない場合、ビューは、マルチタッチシーケンス内のすべてのタッチを受信します。


## 参考リンク
[GestureRecognizerのイベント取得](https://sites.google.com/a/gclue.jp/swift-docs/ni-yinki100-ios/uikit/uiswipegesturerecognizerdesuwaipuwo-ren-shi)
