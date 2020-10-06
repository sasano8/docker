FROM selenium/standalone-chrome-debug
RUN cat /proc/version

# RUN sudo apt-get update && sudo apt install -y python3.8 python3.8-dev
# RUN sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1

# 最新リポジトリを適用する。安定版が欲しいなら削除する。
RUN sudo apt-get update && sudo apt-get install -y software-properties-common
# RUN sudo apt-get install -y python-software-properties
RUN sudo add-apt-repository -y ppa:deadsnakes/ppa

RUN sudo apt-get update && sudo apt install -y python3.9 python3.9-dev
RUN sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.9 1

RUN sudo apt -y update && \
    sudo apt -y upgrade && \
    sudo apt install -y python3-pip

RUN sudo ln -s /usr/bin/pip3 /usr/bin/pip

RUN sudo pip install --upgrade keyrings.alt
RUN sudo pip install -U pip \
sudo pip install --no-cache-dir \
poetry \
gunicorn \
uvicorn

RUN poetry config virtualenvs.create false && \
    poetry config virtualenvs.in-project false
