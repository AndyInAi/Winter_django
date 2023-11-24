# Winter_django

```sh

echo "
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-updates main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-backports main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-security main restricted universe multiverse
" > /etc/apt/sources.list

export DEBIAN_FRONTEND=noninteractive

apt update -y

python3 -V > /dev/null 2>&1 || apt install -y python3

pip3 -V > /dev/null 2>&1 || apt install -y python3-pip

pip3 config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

python3 -m django --version > /dev/null 2>&1 || pip3 install django tzdata

# 如果访问 GitHub.com 需要代理在此设置
# export http_proxy=http://192.168.1.109:3128/
# export https_proxy=http://192.168.1.109:3128/

if [ ! -d ~/Winter_django ]; then cd ~/ ; git clone https://github.com/AndyInAi/Winter_django.git; fi

cd ~/Winter_django

python3 manage.py runserver 0.0.0.0:8080

# starting HTTP server at http://localhost:8080

```
