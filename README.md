# WordPress Ansible Project

## Описание проекта

Данный проект позволяет развернуть CMS WordPress на сервере с ОС Debian с помощью Ansible. Используются роли для установки Apache, MySQL, PHP и самой WordPress. Всё автоматизировано — необходимо только указать IP-адрес хоста.

---

## Шаги по применению Ansible-сценария

> ⚠️ Перед началом убедитесь, что у вас есть **адрес хоста** (например, `192.168.56.10`), полученный после запуска виртуальной машины через Vagrant.

## 1. Настройка инвентарного файла
Создайте файл inventory.ini со следующим содержимым:

```
[wordpress]
192.168.56.10 ansible_user=vagrant ansible_ssh_private_key_file=.vagrant/machines/default/virtualbox/private_key
```
Замените IP-адрес на актуальный, полученный после запуска виртуальной машины.

## 2. Структура проекта
```
wordpress-ansible-project/
├── inventory.ini
├── playbook.yml
├── roles/
│   ├── apache/
│   ├── mysql/
│   ├── php/
│   └── wordpress/
└── README.md
```
## 3. Запуск сценария
   
Запустите Ansible playbook:

```
ansible-playbook -i inventory.ini playbook.yml
```
Что делает сценарий
Устанавливает веб-сервер Apache.

Устанавливает и настраивает СУБД MySQL.

Устанавливает необходимые модули PHP.

Загружает и конфигурирует WordPress.
