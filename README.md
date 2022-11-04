# Git Lesson

## リモートリポジトリとローカルリポジトリとはそれぞれ何でしょうか？

* リモートリポジトリ
    ネット上に配置されたリポジトリ(ファイルやディレクトリの状態を記録する場所)。
    ネット上に配置することで格納されたデータを複数人で共有して使用できる。
    ローカルリポジトリでの開発内容をリモートリポジトリにアップロードし、
    共有することで他の開発メンバーに内容の確認をしてもらうことができる。
    またリモートリポジトリ上のデータを自身のローカルリポジトリに取得することもできる。
    代表的なサービスとしてGitHubが利用されている。

* ローカルリポジトリ
    PC上のに配置されたリポジトリ。
    リモートリポジトリ上のファイルをそれぞれの開発者が使用するため自分のPC上に配置する為のもの。
    作成方法には2種類あり、git initは変更履歴を管理したいディレクトリ上にローカルリポジトリを作成し、これによりそのディレクトリ内の変更履歴を保存することができる方法。git cloneはこのコマンドに続き複製使用したいリモートリポジトリのURLを記述することでローカルリポジトリにリモートリポジトリ上のデータを複製することができる。


## プッシュとマージの違いは何でしょうか？
  * プッシュ
    ローカルリポジトリでのファイルの変更内容をリモートリポジトリにアップすること。
  * マージン
    リポジトリ内にmasterブランチと呼ばれるリポジトリ上の全てのブランチの元となるブランチと、そこから枝分かれした作業用のブランチがあり、その作業用のブランチでのファイルの変更内容をmasterブランチに取り込むこと。
  * 違い
    プッシュ＝ローカルリポジトリからリモートリポジトリに対しての操作
    マージン＝作業用ブランチからmasterブランチに対する操作


## コミットとプッシュの違い
  * コミット
    ブランチ内でのファイルの変更内容を履歴として残しておける機能。
    ファイルの内容を変更後コミットを行う前にgit addの実行が必要。
    この履歴はgit logコマンドで一覧確認ができるとともに、ログそれぞれにコミットメッセージとしてどのような変更を行ったかという内容を記述して残すことができる。
  * プッシュ
    ローカルリポジトリでのファイルの変更内容をリモートリポジトリにアップすること。
  * 違い
    コミット＝リポジトリ内のブランチでの操作
    プッシュ＝ローカルリポジトリからリモートリポジトリに対しての操作


## コミットのメッセージはどのように書いてあげるのが最適でしょうか？
  その履歴がどんな編集が行われたかを記述する。
  git logにて一覧で履歴を確認した際に、どんな編集が行われているかを一目で判断できる記述が適切。
  開発チームごとに記述のルールが決まっていることが多い。


## ローカルでマージするフローと、プルリクエストでマージするフローの違いは何でしょうか？
  ローカルでマージするフローでは作業用ブランチからリモートmasterブランチへの同期までが全てローカル内で行われる為、プッシュ前に他開発メンバーによるレビューが行われておらず、プッシュした内容に不具合を残していることに気付けないリスクがある。
  プルリクエストでのマージはローカル内の作業用ブランチからリモート内の作業用ブランチにプッシュし、そこで一度他開発メンバーによるレビューを行った後にモートmasterブランチへ同期している。その為ローカルでマージするフローで起こりうる不具合発生リスクを回避できることができる。


## コンフリクトを起こしてしまった場合、どう対処すべきですか？
  ・先にマージされた変更内容を取り込む
  ・後にマージしようとしている変更内容を取り込む
  ・どちらの変更内容も取り込む

  解決には自分以外のメンバーが書いたコード内容を把握する必要ある為、
  そのコードを書いたメンバーと相談しつつ、上記３つの方法を使って対処する。