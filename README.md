# docker-compose-test

とりあえずdocker-composeの機能を使ってDockerをDockerfileを使って立ち上げるテスト。

Dockerのメモはここ
https://github.com/noumi0k/docker-compose-test/wiki

## 手順
※Macでの場合
1. Dockerインストールする
公式サイトからDockerHubからダウンロードしてインストール
https://hub.docker.com/editions/community/docker-ce-desktop-mac

2. Docker Composeインストールする
```
$ curl -L https://github.com/docker/compose/releases/download/1.25.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
$ chmod +x /usr/local/bin/docker-compose
```
3. Docker-Composeビルド
```
# ビルド
$ docker-compose build

# プロキシが存在する場合のビルド
$ docker-compose build \
  --build-arg http_proxy=http://[プロキシサーバのIP]:[プロキシサーバのポート] \
  --build-arg https_proxy=http://[プロキシサーバのIP]:[プロキシサーバのポート]
```
4. Docker起動
```
Docker起動から削除までの流れ
# 起動
$ docker-compose up -d

# 起動状態確認
$ docker-compose ps

# 停止
$ docker-compose stop

# コンテナ削除  [-f]つけるとYes/No聞かれない
$ docker-compose rm

# 停止、削除、ネットワーク削除を全て実行
$ docker-compose down

# 停止、削除、ネットワーク削除を全て実行(Image削除も含める版)
$ docker-compose down --rmi all
```

5. 実行結果は http://localhost:10081/tomcat/ で確認
