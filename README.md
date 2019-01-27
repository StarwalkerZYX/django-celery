# mycelery
Django asynchronous task example using Celery and RabbitMQ.

## Getting Started

### Prerequisities
* Python >= 3.5.2
* RabbitMQ
* Virtualenv

### Installing
```
git clone https://github.com/mdrkb/django-celery.git
cd django-celery
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
cd mycelery
python manage.py migrate
```

### Running Django Server
```
python manage.py runserver
```

### Running RabbitMQ Worker
Open another terminal. Navigate inside ```../mycelery/mycelery/``` by activating virutal environment. Then run the following command:

Celery 4.0在Windows运行会报错。
#### 解决方案
参考网页：
<https://stackoverflow.com/questions/37255548/how-to-run-celery-on-windows/>
其中提到：
So try gevent instead.

```
pip install gevent
celery -A mycelery worker -l info -P gevent
```


#### 使用
Open browser and go to <http://127.0.0.1:8000/generate-user/>. Give input for number of users and the task will be performed asynchronously.

