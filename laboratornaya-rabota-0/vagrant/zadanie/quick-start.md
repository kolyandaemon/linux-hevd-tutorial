# Быстрый старт

Перед инициализацией виртуального окружения необходимо выбрать образ виртуальной машины. Просмотреть список доступных образов можно по данной ссылке: [https://app.vagrantup.com/boxes/search?provider=virtualbox](https://app.vagrantup.com/boxes/search?provider=virtualbox). 

После необходимо выполнить команду: 

```text
$ vagrant init username/boxname
```

Где username  - имя пользователя, а boxname - имя образа виртуальной машины. После выполнения команды будет создан конфигурационный файл виртуальной машины Vagrantfile. 

{% hint style="info" %}
Образ виртуальной машины должен иметь поддержку VirtualBox, иначе он работать не будет.
{% endhint %}

  Запуск машины осуществляется соответствующей командой: 

```text
$ vagrant up
```

Vagrant скачает образ и запустит виртуальную машину в соответствии с конфигурационным файлом Vagrantfile. Как только машина будет запущена и настроена с помощью команды `vagrant ssh`  можно будет подключиться к ней. Команда `logout`  позволит выйти из сеанса SSH. 

По окончание изучения виртуальной среды следует её уничтожить. Для этого достаточно выполнить следующую команду: 

```text
$ vagrant destroy
```

По сути вся работа с виртуальным окружением осуществляется с помощью вышеуказанных команд. Далее будут рассмотрены более тонкие настройки виртуальной среды
