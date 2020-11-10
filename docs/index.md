# turtlesim

**X Window Server**
```bash
# [Windows]
# X Server のインストール
choco install -y vcxsrv
# 起動
# 認証なし、-nowgl オプション付きで起動

# [Mac]
# X Window System の起動
xhost + 127.0.0.1

```

```bash
# ---
# ホストPCから

# サービスの起動
docker-compose up -d

# bash ターミナル
docker-compose exec focal bash

# ---
# Docker コンテナから

# node 生成
ros2 run turtlesim turtlesim_node

# コマンド
ros2 run turtlesim turtle_teleop_key
ros2 run turtlesim draw_square

# WSL2 の場合
# https://github.com/microsoft/WSL/issues/4106#issuecomment-501885675
export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
```

# note

`docker-compose build` を WSL2 から実行するとパッケージのダウンロードに失敗した。  
コマンドプロンプトからだと成功した。
