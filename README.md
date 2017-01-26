# Heroku Error Page Demo

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

環境変数のセットでエラーページの確認が出来ます。

## エラーページ画面

デフォルトでは以下のページが表示されるようになっています。

http://www.herokucdn.com/error-pages/application-error.html

環境変数 `ERROR_PAGE_URL` に任意のURLをセットすることで、動作を確認することが出来ます。 

サンプルのアプリケーションは Procfile の指定が間違っているので必ずエラー画面が表示されます。

デプロイ失敗の他30秒ルール違反のタイムアウトなどで用いられるもので、
アプリケーション側でcatch 可能な `throw Exception` などで表示されるエラーとは別のものになります。

本番のアプリケーション内に確認用のエラールートを作りたい場合、

````
<?php
sleep(31);
````

とかするのが無難？

参考 Heroku ErrorCode 一覧

https://devcenter.heroku.com/articles/error-codes

## メンテナンス画面

メンテナンス中は、デフォルトでは以下のページが表示されるようになっています。

http://www.herokucdn.com/error-pages/maintenance-mode.html

環境変数 `MAINTENANCE_PAGE_URL` に任意のURLをセットすることで、動作を確認することが出来ます。 

参考 Heroku ErrorCode 一覧

https://devcenter.heroku.com/articles/error-codes

## セットするURLについて

利用可能なものと利用不可なものとがあるようです。

リダイレクトする系のURLはだめかもです。