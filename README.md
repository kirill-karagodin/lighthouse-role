Role lighthose-role
=========

Requirements
------------
Для установки роли отредактируйте 'requirements.yml'
````bash
- name: lighthose-role
  src: git@github.com:kirill-karagodin/lighthose_role.git
  scm: git
  version: "[last version]"
````
Role Variables
--------------
**default/main.yml** - изменяемые параметры. 
Указаны (при желании можно изменить):
 - директория установки ПО
 - директория записи логов работы сервиса

**tasks/install/git.yml** - установка Git, необходим для получения дистрибутива Lighthouse

**tasks/install/light.yml** - установка сервиса Lignthouse 

**tasks/configure.yml** - деплой конфигурационного файла Lignthouse (конфиг для nginx)

**vars/main.yml** - постоянные параметры для сервиса Lignthouse:
 - ссылка на репозиторий с ПО
 - имя лог файла сервиса

Example Playbook
----------------
````bash
- name: Install Lignthouse
  hosts: [host]
  roles:
    - lignthouse_role
````
License
-------

MIT

