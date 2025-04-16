---
siderbar_position: 3
---

# Views.py

## O que é o views.py?

Views.py é onde será realizado a parte funcional da API. É aqui que contém os métodos GET, POST, PUT e DELETE (CRUD) que possuem muitas funcionalidades que ajudam a gerar a API.

## Importações

Nesse arquivo foram feitas muitas importações para o funcionamento da API.

```python
from django.shortcuts import render
```

Aqui, foi importado a função render para renderizar páginas HTML do projeto, porém ela não foi utilizada na API.

```python
from .models import *
```

Nessa importação, foi importado todas as tabelas do arquivo models.py, para ser utilizado no arquivo views.py.

```python
from .serializer import *
```

Aqui, foi importado todas as classes do arquivo serializer.py, para ser utilizado no arquivo views.py.

```python
from rest_framework.response import Response
```

Aqui, foi importado a classe Response do módulo rest_framework para retornar respostas HTTP de forma simples.

```python
from rest_framework.decorators import api_view, permission_classes
```

Aqui, foram feitas duas importações das funções api_view e permission_classes.

O api_view é utilizado para transformar as funções do Django em views da API. 

Já o permission_classes define quais permissões a view do projeto irá seguir.

```python
from rest_framework.generics import ListCreateAPIView, RetrieveUpdateDestroyAPIView, ListAPIView
```

Aqui, foram feitas as importações de views genéricas. 

O ListCreateAPIView serve para listar e criar objetos de uma vez só.

O RetrieveUpdateDestroyAPIView serve para ver, atualizar ou deletar um objeto específico.

O ListAPIView serve apenas para listar os objetos.

```python
from rest_framework import status
```

```python
from rest_framework.permissions import IsAuthenticated, AllowAny
```

```python
from rest_framework.filters import SearchFilter
```

```python
from django_filters.rest_framework import DjangoFilterBackend
```