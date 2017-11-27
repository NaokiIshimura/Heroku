# Heroku

# コマンド

## 基本

```
# ログイン
$ heroku login

# Herokuアプリを作成する
$ heroku create <アプリ名>

# ブラウザでWeb URLへアクセス
$ heroku open

# dynoの再起動
$ heroku ps:restart
$ heroku restart

# ログ
$ heroku logs
```

## 環境変数

```
# 環境変数一覧
$ heroku config

# 環境変数名を指定して参照
$ heroku config:get ENV_NAME

# 環境変数を追加
$ heroku config:set ENV_NAME="value"

# 環境変数を削除
$ heroku config:unset ENV_VAR_NAME
```

## Add-on

```
# Heroku Postgresの追加
$ heroku addons:create heroku-postgresql:hobby-dev
```

## Rails


config/database.yml

```
production:
  url: <%= ENV['DATABASE_URL'] %>
```

Gemfile

```
gem 'sqlite3', group: [:development, :test]
gem 'pg', group: :production
```

```
# DBのマイグレーション
$ heroku run rake db:migrate
```

## その他

[nulltask/heroku\-static\-provider: Static site provider for Heroku\.](https://github.com/nulltask/heroku-static-provider)
