# Git Github環境構築
## 目次

※Githubのアカウントを作成されていない方は下記のURLよりアカウントを作成してください。

https://github.com/join

1. Gitのインストール
2. ユーザー名とメールアドレスの設定
3. Githubのアカウント設定


### 1 Gitのインストール

https://git-for-windows.github.io/

上記のサイトよりGitのインストールを行ってください。

![image info](img/git1.png)

Downloadボタンをクリックし、exeファイルを実行してください。

![image info](img/git2.png)

「Next」をクリックしてください

![image info](img/git3.png)

「Next」をクリックしてください

![image info](img/git4.png)

「Next」をクリックしてください

![image info](img/git5.png)

「Next」をクリックしてください

![image info](img/git6.png)

「use Visual Studio Code as Git´s default editor」 を選択し
「Next」をクリックしてください。

![image info](img/git7.png)

「Next」をクリックしてください。

![image info](img/git8.png)

「Next」をクリックしてください。

![image info](img/git9.png)

「Next」をクリックしてください。

![image info](img/git10.png)

「Next」をクリックしてください。

![image info](img/git11.png)

「Next」をクリックしてください。

![image info](img/git12.png)

「Next」をクリックしてください。

![image info](img/git13.png)

「Next」をクリックしてください。

![image info](img/git14.png)

「Next」をクリックしてください。

![image info](img/git15.png)

「Next」をクリックしてください。

![image info](img/git16.png)

何も選択せず「install」をクリック。

![image info](img/git17.png)

「Finish」をクリック。

## エクスプローラーにディレクトリに「.git」を表示させよう。

![image info](img/vscode1.png)

「ファイル」をクリック


![image info](img/vscode2.png)

ユーザー設定->設定をクリックしてください。

![image info](img/vscode3.png)

設定の検索バーに「Files Exclude」を入力し、「**/.git」を削除してください。

削除が完了しましたら、Visual Studio Code のターミナルを起動(Ctrl + @)してください。

![image info](img/vscode4.png)

ターミナルを起動し「git init」とコマンドを入力してみましょう。

エクスプローラーに「.git」と表示されたら成功です。

## Git hub のアカウントにログインします。

![image info](img/github1.png)

「New」というボタンをクリックしてください。

![image info](img/github2.png)

リモートリポジトリを作成して行きます。

Repository nameに任意の名前を記述します。

privateにチェックを入れて

「createa repository」をクリックします。

![image info](img/github3.png)

リモートリポジトリが完成出来ました。

## ローカルリポジトリから、リモートリポジトリへプッシュしよう。

![image info](img/github4.png)

Windowsの検索
Git Bashと入力し。「Git Bash」アプリケーションを立ち上げて行きます。

![image info](img/github5.png)

下記のコマンドを実行し、任意のユーザー名とメールアドレスを設定してください。

git config --global user.name "ユーザー名"

git config --global user.email "メールアドレス"

※メールアドレスとユーザー名を設定することで、誰がコミットしたか
分かる様になります。

## リモートリポジトリにpushしよう

![image info](img/ssh1.png)

「cd」 チェンジディレクトリコマンドを使用し、デスクトップに移動してください。

Ex 「cd desktop」

![image info](img/ssh2.png)

「mkdir」メイクディレクトリコマンドを使用し、任意のフォルダを作成してください。

Ex 「mkdir push」

デスクトップにフォルダが作成されたら成功です。

## sshKeyを作成しよう

自分のパソコンからGithubにソースコードを転送する際に、「鍵」が必要になります。

今回はその鍵を作成してきます。

![image info](img/ssh3.png)

「ssh-keygen -t rsa -b 4096」

上記のコマンドを入力しましたらEnterを押しましょう。

>Generating public/private rsa key pair.
>Enter file in which to save the key (/Users/(username)/.ssh/id_rsa):

上記のレスポンスがきましたら、そのまま「Enter」を押してください。

![image info](img/ssh4.png)

過去にsshkeyを作成した事がある方は「already exists」っとレスポンスが

返ってきますが、ここでは 「y」を入力し「Enter」を押します。

![image info](img/ssh5.png)

「Enter passphrase」とパスワードの設定を求められるので任意のパスワードを決めて入力しましたら、

「Enter same passphrase again:」パスワードの確認を求めれますので、再度同じパスワードを入力してください。

![image info](img/ssh6.png)

この様な画面になりましたら。sshKeyの作成が完了です。

## GitBash のsshKeyをクリップボードにコピーしよう。

![image info](img/ssh7.png)

作成したsshKeyを 「clip < /c/Users/r_tsuchiya/.ssh/id_rsa.pub」コマンドを入力しクリップボードにコピーします。

※Ctrl + c などショートカットは利用できないので注意してください。

## Git hubと自分のPCを結びつけよう。

![image info](img/ssh8.png)

Git Hub にログインしてください。

アカウントのアイコンをクリックし、「Settings」をクリックした後、「SSH and GPG keys」をクリックしてください。


![image info](img/ssh9.png)

「New SSH key」をクリックしてください。

![image info](img/ssh10.png)

タイトルは任意で構いません。

「key」の場所に先ほどBashからコピーした、sshkeyを貼り付けて、「Add SSH key」をクリックしてください。

## 実際にpushしてみよう

![image info](img/vsCodeCommand1.png)

vsCodeのターミナルを開き。(Ctrl + @)
作成したフォルダの中に移動出来ているか確認してください。

![image info](img/vsCodeCommand2.png)

「git init」コマンドを入力し、「.git」を作成しましょう。

「git add .」コマンドを入力し、すべてのファイルをインデックスに登録します。

![image info](img/vsCodeCommand3.png)

「git commit -m "任意のコメント"」コマンドを入力しましょう。

![image info](img/github6.png)

「git remote add origin git@sshアドレス」コマンドを入力しましょう。

※リポジトリのgit@に続くアドレスをコピーします。

![image info](img/vsCodeCommand4.png)

コマンド入力できたら。「Enter」を押しましょう。

![image info](img/vsCodeCommand5.png)

「git push origin master」コマンドを入力しGitHubへプッシュします。

![image info](img/vsCodeCommand6.png)

パスワードの入力が求められるので入力してください。

![image info](img/vsCodeCommand7.png)

このようにレスポンスが返ってきたら、push完了です。

![image info](img/finish.png)

GitHubにhtmlファイルが転送されているのが分かります。








