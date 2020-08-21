FROM selenium/standalone-chrome-debug

RUN apt-get update && sudo apt install -y python3.8
RUN sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1

RUN sudo apt -y update && \
    sudo apt -y upgrade && \
    sudo apt install -y python3-pip

RUN sudo ln -s /usr/bin/pip3 /usr/bin/pip

# RUN pip3 install --no-cache-dir \
RUN sudo pip install --no-cache-dir \
uvicorn \
gunicorn \
poetry

RUN poetry config virtualenvs.create false && \
    poetry config virtualenvs.in-project false
