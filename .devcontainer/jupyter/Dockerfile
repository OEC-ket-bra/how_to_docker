FROM jupyter/scipy-notebook
USER root

# 日本語ロケールの設定
RUN apt-get update && apt-get install -y locales && \
    localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm

# requirements.txtのコピーとパッケージインストール
# /root ではなく　/home/jovyan/work/　の方が良いらしい
COPY requirements.txt /home/jovyan/work/
RUN pip install --no-cache-dir -r /home/jovyan/work/requirements.txt