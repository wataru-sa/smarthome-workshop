# 第1回スマートホーム説明会

## GitHubから資料のダウンロード
    $ git clone https://github.com/wataru-sa/smarthome-workshop.git
    $ cd smarthome-workshop/workshop01/

## データ分析環境の構築
### Dockerのインストール
[Docker公式リンク](https://www.docker.com/docker-mac)からダウンロードしてインストール。

### JupyterNotebookの起動
#### コマンドのみで起動
    $ docker run -p 8888:8888 jupyter/datascience-notebook

表示されたURLをTokenごとコピペして、ブラウザでアクセス。

#### docker-composeで起動
    $ cd jupyternotebook
    $ docker-compose up
