---
sidebar_position: 1
---

# Models.py

## O que é o Models.py?

Models.py é um arquivo onde são criadas as tabelas do banco de dados da nossa aplicação. É lá que são criados os campos que usamos durante toda aplicação.

## Importações

A única importação realizada do projeto, foi a importação do módulo models, da biblioteca django.db:

```python
from django.db import models
```

## Tabelas do projeto

No total, foram criadas 5 tabelas para o banco de dados do projeto que são:

**Cadastro**: Essa tabela contém os campos de cadastro para os professores, contendo o número de identificação, nome, email, número de celular e ocupação.

Criando a tabela:   

``` python
class Cadastro(models.Model):
    ni = models.CharField(max_length=15)
    nome = models.CharField(max_length=255)
    email = models.EmailField()
    cel = models.CharField(max_length=255)
    ocup = models.FloatField()
```

**Explicação**: 

class Cadastro(models.Model): É uma classe que herda do models.Model, além disso é aqui que cria a tabela para um banco de dados associado a essa classe.

ni: É a sigla para o número de identificação do professor. O campo contém um CharField com o limite de caracteres fixo em 15.

nome: É aqui que será armazenado o nome do professor. O campo contém um CharField com o limite de caractetes fixo em 255.

email: O campo de email do professor. Possui um campo específico do tipo EmailField.

cel: O número de celular do professor. Possui um campo CharField com o limite de caracteres fixo em 255.

ocup: O cargo/ocupação do professor dentro da escola. Ele possui um campo de números reais, FloatField.

**Disciplinas**: Essa tabela contém as informações sobre a disciplina que o aluno escolheu, a partir do curso escolhido. Os campos são: cod, disc, ch.

Criando a tabela:

```python 
class Disciplinas(models.Model):
    cod = models.CharField(max_length=100)  #Código             #PWBE
    disc = models.CharField(max_length=100) #Disciplina         #Programação Web Back End
    ch = models.IntegerField()              #Carga Horária      #45
``` 

**Explicações**: 

class Disciplinas(models.Model): É uma classe que herda do models.Model, além disso é aqui que cria a tabela para um banco de dados associado a essa classe.

cod: É o código da disciplina. O campo possui um limite de caracteres fixo em 100.

disc: É o nome da disciplina. O campo possui um limite de caracteres fixo em 100.

ch: É a carga horária da disciplina. O campo é feito apenas para números inteiros.

**Ambiente**: Essa tabela representa a sala de aula da escola, tendo os alunos e os professores como representantes da tabela.

Criando a tabela:

``` python
class Ambiente(models.Model):
    cod = models.CharField(max_length=255)  #Código             #LabA101
    sala = models.CharField(max_length=255) #Sala               #Laboratório de Informáica
    cap = models.IntegerField()             #Capacidade de alunos
    resp = models.CharField(max_length=255) #Responsável pelo Ambiente
    per = models.CharField(choices=PERIODOS, max_length=10, default="M")
```

**Explicações**:

cod: Representa o campo de código da sala de aula. O campo possui um limite de caracteres fixo em 255.

sala: Representa a sala de aula da escola. O campo possui um limite de caracteres fixo em 255.

cap: Representa a quantidade de alunos em uma sala de aula. O campo é do tipo inteiro.

resp: Representa o responsável, ou seja o professor representante da sala de aula. O campo possui um limite de caracteres fixo em 255.

per: Representa o período em que a sala de aula é utilizada. O campo possui um limite de caracteres fixo em 10, e um campo de escolhas que podem ser escolhidas nessa ordem: (Obs: o campo fixo da escolha é do período da manhã)

``` python
PERIODOS = [
    ('M', 'Manhã'),
    ('T', 'Tarde'),
    ('N', 'Noite'),
    ('I', 'Integral'),
]
```

**Turma**: Uma tabela simples que representa as turmas da escola.

Criando a tabela:

``` python
class Turma(models.Model):
    cod = models.CharField(max_length=255)      #Código             #13
    turrma = models.CharField(max_length=255)   #Turma              #2DS-TB
```

**Explicações**:

cod: Representa o código da turma. O campo possui um limite de caracteres fixo em 255.

turma: Representa o curso no qual a turma está realizando. O campo possui um limite de caracteres fixo em 255.

**Curso**: Uma tabela que representa os cursos presentes naquela escola.

Criando a tabela:

``` python
class Curso(models.Model):
    cod = models.CharField(max_length=255)      #Código             #TEC
    curso = models.CharField(max_length=255)    #Curso              #Técnico em Desenvolvimento de Sistemas
    tipo = models.CharField(max_length=20, choices=TIPOS, default="CT")
    ha =  models.CharField(max_length=255)      #Hora Aula          #45
```

**Explicações**:

cod: Representa o código em que a turma está. O campo possui um limite de caracteres fixo em 255.

curso: Representa o nome do curso da escola no qual pode possuir as turmas nele. O campo possui um limite de caracteres fixo em 255.

tipo: O tipo de curso que a escola possui para acomodar seus alunos. O campo possui um limite de caracteres fixo em 20 e um campo de escolhas que podem ser escolhidas nessa ordem: (Obs: o campo CT, é fixo para a visualização do usuário)

```python
TIPOS = [
    ('CAI', 'Aprendizagem'),
    ('CT','Técnico'),
    ('CS','Superior'),
    ('FIC','Formação')
]
``` 

ha: Representa a quantidade de horas das aulas. O campo possui um limite de caracteres fixo em 255.