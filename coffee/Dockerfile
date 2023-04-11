# syntax=docker/dockerfile:1
FROM python:3.9-alpine
RUN apk add postgresql-dev
COPY . .
RUN pip3 install --upgrade pip && \
    pip3 config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple && \
    pip3 install -r requirements.txt && \
    sed -i 's/from flask._compat import text_type/from flask_script._compat import text_type/g' /usr/local/lib/python3.9/site-packages/flask_script/__init__.py 
CMD [ "./entrypoint.sh" ]
