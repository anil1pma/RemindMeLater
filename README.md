# RemindMeLater
Remind me later project.

Create a Python 2.7 virtualenv
pip install -r requirements.txt
npm install
sudo apt-get install rabbitmq-server
sudo apt-get install python-librabbitmq
sudo apt-get install python-celery


#DataBase:
Create Database "sendMessage"
in settings.py change Database 
DATABASES = {
    'default': {
        # 'ENGINE': 'django.db.backends.sqlite3',
        # 'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'sendMessage',
        'USER': 'root',
        'PASSWORD': 'asdf123',
        'HOST': 'localhost',   # Or an IP Address that your DB is hosted on
        'PORT': '3306',
    }
}
change 'USER' and 'PASSWORD' accordingly.

#DatabaseModeling:
Tablename: SendMessage
PrimaryKey: id(default key)
attributes: user_mob_no (var char), user_message (var char), user_mail_id(var char),  user_message_through(var char), 
user_msg_date_time(dateTime).

#Run Command:
python manage.py makemigrations
python manage.py migrate
python manage.py runserver

Feel the information and submit.

#Run Celery in back ground:
celery -A mysite beat
celery -A mysite worker




