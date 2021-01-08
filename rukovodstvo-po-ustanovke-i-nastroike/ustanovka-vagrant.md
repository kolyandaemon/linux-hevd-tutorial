# Установка Vagrant

Vagrant - это инструмент для создания и управления средами виртуальных машин.

## Загрузка установочных файлов

Скачать установочный файл можно с [официального сайта](https://www.vagrantup.com/downloads) практически для любой платформы

![ &#x420;&#x438;&#x441;&#x443;&#x43D;&#x43E;&#x43A; 2 &#x2014; &#x421;&#x442;&#x440;&#x430;&#x43D;&#x438;&#x446;&#x430; &#x437;&#x430;&#x433;&#x440;&#x443;&#x437;&#x43A;&#x438; &#x443;&#x441;&#x442;&#x430;&#x43D;&#x43E;&#x432;&#x43E;&#x447;&#x43D;&#x43E;&#x433;&#x43E; &#x43F;&#x430;&#x43A;&#x435;&#x442;&#x430; VirtualBox](../.gitbook/assets/zagruzka-failov.png)

## Установка Vagrant

### Windows 10

После запуска ранее скачанного файла появиться окно установочной программы Vagrant. Чтобы перейти к следующему шагу необходимо нажать на кнопку "**Next**"

![](../.gitbook/assets/1-etap-ustanovki-glavnoe-okno.png)

Перед принятием лицензионного соглашения, рекомендуется с ним ознакомиться 

![](../.gitbook/assets/2-etap-ustanovki-polzovatlskoe-soglashenie.png)

Далее необходимо указать директорию куда будет установлена программа, но лучше оставить исходное значение

![](../.gitbook/assets/3-etap-ustanovki-put-ustanovki.png)

Далее программа произведет установку всех необходимых компонентов 

![](../.gitbook/assets/4-etap-ustanovki-process-ustanovki-.png)

Скриншот установочной программы представленный ниже знаменует успешное завершение процесса установки программы Vagrant

![](../.gitbook/assets/5-etap-ustanovki-okonchanie-u-ustanovki-.png)

Для завершения установки программы необходимо перезагрузить компьютер.

### Debian 10

Для установки Vagrant на Debian 10 достаточно выполнить в терминале следующие команды: 

```text
sudo apt update
sudo apt upgrade
sudo apt install vagrant
```

###  Windows Subsystem for Linux 2\(Ubuntu 20.04\)

Установка Vagrant в WLS 2 такая же как и в Dedian, но требует дополнительных манипуляций после выполнения соответствующих команд. Необходимо в конец файла с именем ".bashrc", который находиться в домашней директории, добавить следующие строчки:  

```text
export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"
export PATH="$PATH:/mnt/c/Program Files/Oracle/VirtualBox"
```

Первая строчка включает включает функцию использования Vagrant в  WSL 2. Вторая позволяет Vagrant узнать путь куда установлено программное обеспечение VirtualBox.

