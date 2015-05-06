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

gesture recognizerは
