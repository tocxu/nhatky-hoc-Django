#Create a Django Project
> django-admin startproject ThuyTinhShop

Cấu trúc thư mục:
```
ThuyTinhShop
  ThuyTinhShop
    init.py
    setting.py
    urls.py
    wsgi.py
  db.splite.3
  manage.py
```

trong đó:

* setting.py: chứa các cài đặt của project
* urls.py: chứa url của project
* manage.py: utility for administative tasks

to run server use command:

> python manage.py runserver

manage.py is in the top-level project directory

check in the browser with url: /127.0.0.1:8000/

Create our main app inside of our ThuyTinhShop project:
> python manage.py startapp main_app

our app has its own directory and generated files

*views* in Django app are used to run functions in response to specific URLs entered in the browser.

*templates* in Django app display data provided by views

> vim views.py

```
from django.shortcuts import render
from django.http import HttpResponse
# Create your views here.
def index(request):
	return HttpResponse('<h1>Hello, This is my First app!</h1>')
```


> vim ThuyTinhShop/urls.py

```
from django.conf.urls import url
from django.contrib import admin
from main_app import views
urlpatterns = [
    url(r'^admin/', admin.site.urls),
	#localhost/index
	url(r'^index/',
		views.index),
]
```
