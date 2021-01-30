# Django2025
 
Passos Iniciais com O Django

Passo 1 – Criar um ambiente virtual

cmd → python -m venv venv

Passo 2 – Ativar a Venv

Entrar na pasta Scripts
cmd – Activate

Passo 3 – Instalar o Django

cmd

pip install django

Passo 4 – criar um projeto
cmd
django-admin startproject 2025

Passo5 – Criar o Banco de dados
cmd- python manage.py migrate

Passo 6 – Criar o Super usuário
cmd- python manage.py createsuperuser

Passo 7 – Rodar o servidor
cmd- python manage.py runserver

Passo 8 – Traduzir a aplicação
Abrir o arquivo Settings.py

LANGUAGE_CODE = 'pt-br'
TIME_ZONE = 'America/Sao_Paulo'

Passo 9 – Criar um app dentro do Projeto  
cmd- python manage.py startapp up 

Passo 10 – Criar dois app dentro do Projeto  
cmd- python manage.py startapp categoria 
cmd- python manage.py startapp down

Passo 11 – Registrar no projeto o novo app  
Abra Settings.py

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
'up',
'down',
]
Passo 11 – Configurar a Views do APP

Views.py

from django.shortcuts import render
from django.http import HttpResponse
def index(request):
    return render(request,'up/index.html')


Passo 12 – Crie o urls.py dentro dos  APP

urls.py  app down

from . import views
from django.urls import path,include
urlpatterns = [
path('', views.index),
]


urls.py  app up

from . import views
from django.urls import path,include
urlpatterns = [
path('up/', views.index),
]

Passo 12 – Crie o urls.py dentro do projeto

from django.contrib import admin
from django.urls import path,include
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('up.urls')),
    path('', include('down.urls')),
]


Passo 13 – Crie os templates dentro dos apps

Uma pasta com o nome de down
dentro da pasta down a pasta templates
dentro da pasta templates a pasta down
dentro da pasta down index.html



