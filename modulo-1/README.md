# Módulo 1

## Resumo

Python foi uma linguagem inicialmente escrita por Guido van Rossum

Documentação do [python](https://docs.python.org)

- Built in functions https://docs.python.org/3/library/index.html
  - Documenta todas as lib nativas do python
- Referências da linguagem
  - Documenta a syntax da linguagem https://docs.python.org/3/reference/index.html
- Repositório das libs desenvolvidas pela comunidade para o python https://pypi.org/

## Gerenciador de versão do python

Utilizar o [pyenv](https://github.com/pyenv/pyenv) para gerenciar as versões instaladas no S.O.

- `pyenv versions` Lista as versões instaladas no S.O.
- `pyenv install -l` Lista todas as versões disponíveis para a instalação
- `pyenv install [versao]` Instala uma versão no S.O.
- `pyenv global [versao]` Define a versão passada como padrão no S.O.

## Shell Python

O `ipython` é um modo iterativo com asteróides

- `pip install ipython[notebook]` Instala o ipython com a extensão notebook
- `ipython` Abre o interpretador no modo iterativo utilizando os recursos do ipython
- `ipython notebook` Abre no navegador o notebook com o Jupyter

## Virtual env

No python 3, o virtual env já vem na biblioteca padrão

### Criação no diretório de trabalho

```bash
python -m venv .[nome-do-diretorio-de-trabalho]
```

### Ativar o virtual env

```bash
source .[nome-do-diretorio-de-trabalho]/bin/activate
```

### Instalação do Django

Com o virtual env ativo, instalar as dependências do projeto

```bash
pip install django
```

### Criar um projeto Django

Após a instalação da lib, para iniciar um novo projeto django

```bash
django-admin startproject [nome-do-projeto] [local] # Para criar no diretório corrente use '.'
```

## Ajustes dos projeto

### Simplificando a chamanda ao manage.py

Como sempre iremos trabalhar com o virtual env ativo, haverá uma variável de ambiente definindo o path dele, dessa forma, para criar um alias ao `manage.py`, basta apenas digitar:

```bash
alias manage='python $VIRTUAL_ENV/../manage.py'
```

Assim, para uma nova chamada ao `manage.py` em qualquer diretório do sistema, basta digitar:

```bash
$ manage

Type 'manage.py help <subcommand>' for help on a specific subcommand.

Available subcommands:

[auth]
    changepassword
    createsuperuser

[contenttypes]
    remove_stale_contenttypes

[django]
    check
    compilemessages
    createcachetable
    dbshell
    diffsettings
    dumpdata
    flush
    inspectdb
    loaddata
    makemessages
    makemigrations
    migrate
    sendtestemail
    shell
    showmigrations
    sqlflush
    sqlmigrate
    sqlsequencereset
    squashmigrations
    startapp
    startproject
    test
    testserver

[sessions]
    clearsessions

[staticfiles]
    collectstatic
    findstatic
    runserver
```

### Criando uma Django app

Uma biblioteca python que segue algumas convensões do django

```bash
manage startapp [nome]
```

## Expessão regular para substituir valores

Seleciona todas as propriedades `src e hrf` que pertencem as tags `img, css e js`

```regex
(src|href)="((img|css|js).\*?)"
```

Substitue pelo primeiro grupo `$1` `src e hrf` com os valores do segundo grupo selecionad `$2` juntamente com a tag static

```regex
$1="{% static '$2'%}"
```
