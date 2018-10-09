# ChofufesApp2017IosED 67回調布祭アプリForDroid

メインのコードはapp/src/main/a67thChofufesApp下にある。

## 今年の流れ
- 4月にアプリの機能についての大まかな方針を決めた。機能上で必要となり、団体に求めるデータなども決めて、説明会でそれを伝える準備をする。作成資料は説明会のものを参照すると良い。
- 第二回説明会でアプリの存在、大まかな仕様を説明し、第三回よりデータの収集を始めた。
- 今年は8/9にデータの締め切りを設定。 **ぶっちゃけ早すぎた。集まった団体数が調布祭自体に参加した団体のそれよりも少なくなってしまった。**
- 開発を続け9月末に公開。丸調の連中やTwitterでデバッグの呼びかけを行い、バグを見つけては修正を繰り返していた。Androidの審査は緩いし早い、バグ修正バージョンの反映も早いので、ギリギリの提出や早急な修正にも対応できる。ただ、Ios版と違い、 **Droidは機種に依存するバグが非常に多く、自分の機種では余裕の動作を見せていても、ある機種では動作が重かったり、それどころかOutOfMemoryになったり、挙句は未知のバグに遭遇したり、** といったことがざらにある。結果として早めの提出をする必要があり、そして広く色んな機種でデバッグをしてもらう必要がある。とかく知り合いのDroidユーザーに片っ端からお願いしよう。

## 仕様一覧・機能について思ったこと
- 模擬店一覧・お知らせ・タイムテーブル
  レイアウトについて前者２つは主にAdapterを利用したListViewで構成、最後者はViewPagerを利用。データの送受信にはFireBase(基本無料・調布祭期間中のみアップグレード$25/month)を利用した。
  - 模擬店一覧については各団体の公式サイトorTwitterにアクセス出来るようにデータを収集した。店舗名検索機能とかあったら良いんじゃね？と思っていたが、抱えていたタスク的にやめた。
  - タイムテーブルは時間変更などを踏まえて最新の情報を載せる目的で搭載したが、そもそも時間が遅れテーブルに変更が生じようが、こちらが他の仕事で忙しかったので意味はなかった。
  - 通知も届くように設定していた。Iosの通知仕様は最近よく変化しているので都度都度確認すると良いかと。
- マップ
  GoogleMapsAPIを使用。構内マップにピン留めなどを加えたが、ナビなどは使い物にならないので役に立ってない気がした。ナビ機能を自前で付けようかと思ったが、それは **歩きスマホを催促させることになるかな、と思ったのでやめておいた。** 結果的にあんま要らなかった機能かもしれない。

## GooglePlayStoreについて
**調布祭用のアカウント** が存在する。年間費などは特にない。審査は非常に緩く数時間で完了するので、調布祭中にバグが見つかったとしても案外となんとかなる()。
