Пинг хоста с докер контейнера запущенного на удаленной машине (ipv4) при помощи Ansible playbook, тестировалось на Ubuntu20.04
Условие:
- на машине должен быть установнен Ansible, Git
- долна быть настроена связь с удаленной машиной по ключу SSH (root), путь к ключу должен быть указан в файле host.txt, переменная ansible_ssh_private_key_file
- на удаленном хосте должен быть установлен docker

Работа скрипта
1) Клонируем Git репозиторий https://github.com/Alex-tev/test_task.git
2) Переходим в дерикторию test_task
3) Выполняем команду: ansible-playbook playbook_test_task.yml -e "host=XXX.XXX.XXX.XXX host_port=XXXX ping_host=XXX.XXX.XXX.XXX" 
   где
   host - удаленная машина 
   host_port - порт ssh удаленной машины
   ping_host - хост который будем пинговать с докер контейнера
4) Результат выполнения скрипта записуется в файле /tmp/ipv6_test_log
