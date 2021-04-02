# WordPress開発環境をローカルに爆速で構築するテンプレート

## 構成
```
docker-compose.yml  -> 定義ファイル
readme.md           -> このファイル
.env                -> 環境変数ファイル
wp-content/themes   -> wp-contentディレクトリは自動で生成される。themesディレクトリ配下にテーマを入れる
```

## バージョン
- WordPress   最新
- MariaDB     MySQLがM1未対応のため、mariadbを利用

## 手順
1. このリポジトリをクローン
2. 環境変数ファイルを「.env」と言う名前で作成し、以下内容をコピペ（一例）<br>
```
MYSQL_ROOT_PASSWORD=somewordpress
MYSQL_DATABASE=wordpress
MYSQL_USER=wordpress
MYSQL_PASSWORD=wordpress

WORDPRESS_DB_HOST=db:3306
WORDPRESS_DB_USER=wordpress
WORDPRESS_DB_PASSWORD=wordpress
```
3. 以下コマンドで起動！
```
docker-compose up -d
```
4. http://localhost:8000/ へアクセス
5. 管理者のユーザー名とパスワードを設定して作成！
6. themes/ 配下にテーマを入れて作成していきましょう。

## Docker コマンド
- docker ps

### run
docker-compose up
docker-compose start

### stop
docker-compose stop

### delete
docker-compose down
※wp-content/ 配下は削除されません。

### Wordpress Access
docker exec -it [Wordpress側のコンテナ名] /bin/bash


