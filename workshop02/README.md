# 第2回スマートホーム説明会

## 概要
TICK StackとはInfluxDataが提供する4つのソフトウェア（Telegraf、InfluxDB、Chronograf、Kapacitor）で構築される一連のIoTデータ管理システムのことである。本資料ではTICK Stackの構築を行い、各ソフトウェアの連携方法について学ぶ。

## 起動コンテナ一覧
- InfluxDB
- Telegraf
- Chronograf
- Kapacitor
- JupyterNotebook
- Node.js
- MongoDB

## 資料のダウンロード
    $ git clone https://github.com/wataru-sa/smarthome-workshop.git
    $ cd smarthome-workshop/workshop02/

## 起動手順
### Dockerのインストール
[Docker公式リンク](https://www.docker.com/docker-mac)からダウンロードしてインストール。

### docker-composeで起動
    $ docker-compose up

### 起動確認
以下のURLにアクセス
- InfluxDB: http://localhost:8086
- Telegraf
- Chronograf: http://localhost:8008
- Kapacitor: http://localhost:9092
- JupyterNotebook: http://localhost:8888
- Node.js: http://localhost:3000
- MongoDB: http://localhost:27017


## 動作手順
### 1. データ送信
JupyterNotebook: http://localhost:8888 にアクセス。<br>
send.ipynbを実行し、Telegraf経由でInfluxDBへデータ送信がされているか確認。

### 2. データ閲覧
Chronograf: http://localhost:8008 にアクセス。<br>
送信したデータが表示されているか確認。

### 3. 出力確認
Kapacitor: http://localhost:9092/kapacitor/v1/tasks/view/dump<br>
1を実行するたびにKapacitorの出力が更新されているか確認。

### 4. 通知確認
Node.js: http://localhost:3000/tests/latest<br>
Node.jsで起動しているRESTful APIにデータが自動通知されていることを確認。
最新5件を表示するようにしている。
