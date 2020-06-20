FROM selenium/standalone-chrome-debug

RUN sudo apt -y update && \
    sudo apt -y upgrade && \
    sudo apt install -y python3-pip

RUN sudo ln -s /usr/bin/pip3 /usr/bin/pip

# RUN pip3 install --no-cache-dir \
RUN pip install --no-cache-dir \
uvicorn \
gunicorn \
poetry

RUN poetry config virtualenvs.create false && \
    poetry config virtualenvs.in-project false