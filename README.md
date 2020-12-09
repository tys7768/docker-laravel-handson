# docke-laravel-handson

# コマンド
`docker-compose up|down`
docker-compose.ymlに定義したサービスを起動する(up)
-d でデタッチモード(バッグラウンド実行)
--build でコンテナ開始前にイメージを構築する
キャッシュがあればそれが使われる

docker-compose.ymlに定義したサービスを停止する(down)

`docker-compose ps`
コンテナの一覧を表示する

`docker-compose exec app bash`
appという名前のコンテナに入る(bashを使用する)

`docker-compose exec app #{command}`
appという名前のコンテナで#{command}のコマンドを実行する
