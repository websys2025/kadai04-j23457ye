## 自動販売機（オブジェクト、DOM、イベント処理）のミニレポート
### Q4-1. Itemクラスのメソッドについて説明せよ。
* showItemListがクラスメソッドである理由を考察せよ。
* showItemListは全ての商品の一覧を表示する機能で、特定の商品インスタンスに依存しない
商品リスト全体を引数として受け取り、全商品の情報を出力する処理
どの商品インスタンスからも独立して実行できる処理のため、クラス全体に属する機能として適している
Item.showItemList(item_list)のように、インスタンスを作成せずに直接クラスから呼び出せる
* buyItemがインスタンスメソッドである理由を考察せよ。
 buyItemは特定の商品の購入処理で、その商品固有の情報を操作する
this.stock、this.price、this.nameなど、そのインスタンス固有のプロパティにアクセスする必要がある
商品ごとに異なる処理（在庫減少、HTML要素の更新）を行うため、個別のインスタンスに属する機能として適している
item_list[i].buyItem()のように、特定の商品インスタンスから呼び出す
### Q4-2. 商品の購入ボタンをクリックすると、どのような処理でセルの値が減少するか説明せよ。
* 購入された商品の在庫数のセルをどのようにして特定するのか説明せよ。
* 商品表作成時に各在庫セルに "stock" + 商品ID の形式でID属性を付与
* buyItem()実行時に this.id で自分の商品IDを取得し、対応するHTML要素を特定
* 特定したセルの値をどのように変更するのか説明せよ。
* this.stock--でインスタンスの在庫数を減少
* 減少後の在庫数をHTML要素のtextContentに代入
* ブラウザが自動的に画面表示を更新し、新しい在庫数が表示される
### Q4-3. 感想
* 今回の課題で苦労したこと
* staticメソッドとインスタンスメソッドの使い分けの判断
* HTML要素とJavaScriptでの要素特定を確実に行うためのID設計
* 演習を通して理解できたこと
* クラス設計がいかに現実のシステムを表現できるか
* HTML、CSS、JavaScriptの連携によるインタラクティブなWebアプリケーション開発
* ユーザーのクリック操作に応じた処理の実装方法
* この自動販売機プログラムの追加機能や課題など
* お釣り機能として投入金額と商品価格の差額を計算・表示
* 管理者機能として在庫補充、新商品追加機能
ページリロード時にデータがリセットされること
