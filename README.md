# 概要
### このリポジトリは基本的なlaravelを用いたプロジェクト作成に使用するファイルを格納
#### ディレクトリ構成

<pre>
basic-laravel-project(プロジェクトのルートディレクトリ)
├ .env
├ docker-compose.yml
└ docker
  ├ mysql
  |  └ my.cnf
  ├ nginx
  |  └ default.conf
  └ php
     ├ Dockerfile
     └ php.ini
</pre>

#### 使い方
1. これらのファイルを自分の作りたいプロジェクトのルートディレクトリ配下に配置する
2. docker-compose.ymlのある階層でコンテナを起動させる
<pre>
  $ docker-compose up -d
</pre>
3. phpディレクトリ配下に移動し、phpコンテナに入る
<pre>
  $ docker exec -it (docker-compose.yml内でつけたphpのコンテナ名) bash
</pre>
4. phpコンテナ内でcomposerが入っていることを確認する
<pre>
# composer -V
</pre>
5. Laravelをインストールする
<pre>
# composer create-project --prefer-dist "laravel/laravel=6.*" .
</pre>
6. .envファイルにAPP_KEYを生成する
<pre>
  # php artisan key:generate
</pre>
7. phpコンテナから抜け、起動しているコンテナを再起動し、.envファイルの更新を反映させる
<pre>
  # exit
  $docker-compose down
  $docker-compose up -d
</pre>
