# turtlesim

```bash
# ---
# ホストPCから

# X Window System の起動
xhost + 127.0.0.1

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
```
