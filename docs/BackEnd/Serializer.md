---
sidebar_position: 2
---

# Serializer.py

## O que é o serializer.py?

O serializer.py é um arquivo onde ele pega os campos e dados da tabela (se houver) e os transformam em um arquivo JSON para ser mostrado em um site ou em uma API, no futuro.

## Importações 

As duas importações realizadas foram essas abaixo:

```python
from rest_framework import serializers
```

Essa importação, importa o módulo serializers do módulo do rest_framework, para construir APIs de forma rápida e fácil.

```python 
from .models import *
```

Essa importação, importa todas as tabelas criadas no arquivo models.py.

## Explicação das classes 

```python 
class CadastroSerializer(serializers.ModelSerializer):
    class Meta:
        model = Cadastro
        fields = '__all__'
```

Nesse trecho, ele vai pegar todos os campos da tabela de Cadastro e irá trasformar em um arquivo JSON.

```python
class DisciplinaSerializer(serializers.ModelSerializer):
    class Meta:
        model = Disciplinas
        fields = '__all__'
```

Nesse trecho, os campos da tabela Disciplinas são transformados em JSON.

```python 
class AmbienteSerializer(serializers.ModelSerializer):
    class Meta:
        model = Ambiente
        fields = '__all__'
```

Nesse trecho, os campos da tabela Ambiente são transformados em JSON.

```python
class TurmaSerializer(serializers.ModelSerializer):
    class Meta:
        model = Turma
        fields = '__all__'
```

Nesse trecho, os campos da tabela Turma são transformados em JSON.

```python
class CursoSerializer(serializers.ModelSerializer):
    class Meta:
        model = Curso
        fields = '__all__'
```

Nesse trecho, os campos da tabela Curso são transformados em JSON.