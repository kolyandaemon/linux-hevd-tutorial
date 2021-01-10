# Установка WSL

Подсистема Windows для Linux \(WSL\) — это новый компонент Windows 10, который позволяет запускать собственные программы командной строки Linux непосредственно в Windows, как классические приложения для Windows и современные приложения Store.

## Установка

### Включение компонентов

Сначала необходимо включить следующие системные компоненты:

* Подсистема Windows для Linux;
* Платформа виртуальной машины.

Включить данные компоненты можно через панель управления. Чтобы открыть панель управления достаточно открыть меню пуск и ввести слово "Панель"\(\) и нажать клавишу Enter.

![](../.gitbook/assets/image%20%282%29.png)

Далее в открывшемся окне необходимо перейти по ссылке "Удаление программы" разделе "Программы"

![](../.gitbook/assets/1-etap%20%283%29.png)

После необходимо перейти по ссылке "Включение или отключение компонентов Windows" в разделе "Программы и компоненты".

![](../.gitbook/assets/2-etap%20%283%29.png)

В открывшемся маленьком окне необходимо отметить вышеуказанные компоненты, нажать на кнопку "ОК" и перезагрузить компьютер чтобы изменения вступили в силу. 

### Установка дистрибутива

Скачать дистрибутив Debian можно в магазине приложений Microsoft Store. 

![](../.gitbook/assets/1-etap%20%284%29.png)

Если по какой-то причине на компьютере отсутствует магазин приложений Microsoft Store, дистрибутив можно скачать по следующей ссылке: [https://aka.ms/wsl-debian-gnulinux](https://aka.ms/wsl-debian-gnulinux)

Установить скачанный пакет можно с помощью следующей команды в терминале Powershell:

```bash
Add-AppxPackage .\app_name.appx
```

### 
