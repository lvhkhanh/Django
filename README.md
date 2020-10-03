# Django
## Install
```
pip install django
django-admin startproject hello_world
python manage.py startapp myapp
```
```
#urls.py
from django.urls import path
from .views import home
urlpatterns = [
    path('', home,name='home'),
]
```
```
#views.py
from django.shortcuts import HttpResponse

# Create your views here.
def home(request):
    return HttpResponse("Hello world from Django")
```
```
# settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    # local app
    'myapp',
]
```
```
# hello_world/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('myapp.urls'))
]
```
```bash
python manage.py runserver
```
