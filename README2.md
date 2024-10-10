### README2.mdの詳細
#### README.mdの作業後、プロジェクトにすぐ入れる構成にしたため、まとめとしてディレクトリ構成を書き残す
<pre>
basic-laravel-project(プロジェクトのルートディレクトリ)
├ .editorconfig
├ .env
├ .env.sample
├ .gitattributes
├ .gitignore
├ .styleci.yml
├ artisan
├ composer.json
├ composer.lock
├ docker-compose.yml
├ package-lock.json
├ package.json
├ phpunit.xml
├ README.md
├ server.php
├ webpack.mix.js
├ app
| ├ HTTP
| |  ├ Controllers
| |  ├ Middleware
| |  ├ .....
| |   
| ├ Models
| ├ .....
|  
├ bootstrap
| ├ .....
|  
├ config
| ├ .....
|  
├ database
| ├ migrations
| ├ .....
|  
├ docker
| ├ mysql
| |  └ my.cnf
| ├ nginx
| |  └ default.conf
| └ php
|    ├ Dockerfile
|    └ php.ini
├ public(←ここをdefault.confのrootに設定することでlaravelの最初のページに繋がる)
| ├ index.php
| ├ .....
|  
├ resources
| ├ css
| ├ js
| ├ lang/en
| ├ views
| ├ .....
|  
├ routes
| ├ api.php
| ├ web.php
| ├ .....
|  
├ storage
| ├ log
| ├ .....
|  
├ tests
| ├ Feature
| ├ Unit
| ├ .....
|  
└ vendor
  ├ .....
</pre>
