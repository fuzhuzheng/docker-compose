FROM python:3.8.5

WORKDIR /root

COPY ./requirements.txt ./

#安装
RUN pip install --no-cache-dir --upgrade  pip -i https://pypi.tuna.tsinghua.edu.cn/simple
RUN pip install --no-cache-dir uwsgi -i https://pypi.tuna.tsinghua.edu.cn/simple
RUN pip install --no-cache-dir -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
