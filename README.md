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
4. phpコンテナ内でcomposerが入っていることを確認する(version 2.*系が望ましい、もっと言うなら2.5.*がいい)
<pre>
  # composer -V
</pre>
5. Laravelをインストールする(後で移動するので一時置きのためにtemp_laravelディレクトリを作成し、その中に格納する)
<pre>
  # composer create-project --prefer-dist "laravel/laravel=8.*" temp_laravel
  # cp -r temp_laravel/* ./
  # mv temp_laravel/.* ./
  # rm -rf temp_laravel
</pre>
6. composer.jsonを書き換える
7. composer.lockを更新する
<pre>
  # composer update
</pre>
8. .envファイルにAPP_KEYを生成する
<pre>
  # php artisan key:generate
</pre>
9. vendorディレクトリを再インストールする
<pre>
  # rm -rf ./vendor
  # composer install
</pre>
11. phpコンテナから抜け、起動しているコンテナを再起動し、.envファイルの更新を反映させる
<pre>
  # exit
  $ docker-compose restart
</pre>
