# Включение аппаратной виртуализации

## Включена ли виртуализация?

### Windows 10

В windows 10 это можно проверить в диспетчере задач. Запустить диспетчер задач можно используя комбинации клавиш Ctrl + Shift + Esc. Перейдя во вкладку "Производительность"  нужно выбрать пункт "ЦП" в списке. В правом нижнем углу находиться информация о состоянии аппаратной виртуализации, как показано на рисунке ниже.  

![&#x420;&#x438;&#x441;&#x443;&#x43D;&#x43E;&#x43A; 1 &#x2014; &#x41E;&#x43A;&#x43D;&#x43E; &#x43F;&#x440;&#x43E;&#x433;&#x440;&#x430;&#x43C;&#x43C;&#x44B; &quot;&#x414;&#x438;&#x441;&#x43F;&#x435;&#x442;&#x447;&#x435;&#x440; &#x437;&#x430;&#x434;&#x430;&#x447; Windows&quot;  ](../.gitbook/assets/apparatnaya-virutalizaciya.png)

### Linux\(Ubuntu 20.04\)

В Linux достаточно выполнить в терминале следующую команду:

```
$ egrep '(vmx|svm)' /proc/cpuinfo
```

Если вывод после выполнения команды не пустой, значит процессор поддерживает аппаратную визуализацию.

## Включение аппаратной виртуализации в BIOS/UEFI

Аппаратная виртуализация в большинстве случаев выключена в настройках  BIOS/UEFI.

### Вход в настройки  BIOS/UEFI

Чтобы перейти в настройки BIOS/UEFI необходимо нажать соответствующую клавишу на клавиатуре  при включении компьютера/ноутбука. Ниже приведена таблица производителей ноутбуков и материнских план и соответствующее название клавиши для перехода в настройки BIOS/UEFI:

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x41F;&#x440;&#x43E;&#x438;&#x437;&#x432;&#x43E;&#x434;&#x438;&#x442;&#x435;&#x43B;&#x44C;</th>
      <th
      style="text-align:left">&#x41A;&#x43B;&#x430;&#x432;&#x438;&#x448;&#x430;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Acer</td>
      <td style="text-align:left">
        <p><b>Delete</b>
        </p>
        <p><b>F1</b>(&#x441;&#x442;&#x430;&#x440;&#x44B;&#x435; &#x43C;&#x43E;&#x434;&#x435;&#x43B;&#x438;)</p>
        <p><b>F2</b>
        </p>
        <p><b>Ctrl+Alt+ESC </b>(&#x441;&#x442;&#x430;&#x440;&#x44B;&#x435; &#x43C;&#x43E;&#x434;&#x435;&#x43B;&#x438;)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ASRock</td>
      <td style="text-align:left">
        <p><b>Delete</b>
        </p>
        <p><b>F2</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ASUS</td>
      <td style="text-align:left">
        <p><b>Delete</b>
        </p>
        <p><b>F2</b>
        </p>
        <p><b>F10</b>
        </p>
        <p><b>Insert</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Biostar</td>
      <td style="text-align:left"><b>Delete</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Compaq</td>
      <td style="text-align:left">
        <p><b>ESC</b>
        </p>
        <p><b>F9</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">DELL</td>
      <td style="text-align:left">
        <p><b>Delete</b>
        </p>
        <p><b>F1</b>
        </p>
        <p><b>F2<br />F3<br />F12</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Fujitsu</td>
      <td style="text-align:left"><b>F12</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Intel</td>
      <td style="text-align:left">
        <p><b>Delete</b>
        </p>
        <p><b>F2</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Gigabyte</td>
      <td style="text-align:left"><b>Delete</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">HP</td>
      <td style="text-align:left">
        <p><b>ESC</b>
        </p>
        <p><b>F1</b>
        </p>
        <p><b>F2<br />F6<br />F10<br />F11</b>
        </p>
        <p><b>F12</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Lenovo</td>
      <td style="text-align:left">
        <p><b>Enter</b>
        </p>
        <p><b>F1</b>
        </p>
        <p><b>F2</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">MSI</td>
      <td style="text-align:left"><b>Delete</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Samsung</td>
      <td style="text-align:left"><b>F2</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Toshiba</td>
      <td style="text-align:left">
        <p><b>ESC</b>
        </p>
        <p><b>F1</b>
        </p>
        <p><b>F2<br />F12</b>
        </p>
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
Если ни одна из выше перечисленной клавиш не подошла, воспользуйтесь поисковой системой Google
{% endhint %}

### Включение аппаратной вирутализации

В большинстве случаев параметр отвечающий за активацию аппаратной вирутализации находиться во вкладке "**Advanced**" настроек BIOS/UEFI. А вот название самого параметра у каждого производителя оборудования разное: 

* Intel Virtualization Technology;
* Virtualization;
* Virtualization Technology;
* Secure Virtual Machine Mode;
* VT-x;
* VT-d;
* Virtualization Extensions;
* AMD-V;
* SVM mode.

Для активации пункта необходимо перевести параметр в режим "**Enabled"**. Далее выйти из настроек BIOS/UEFI. Обычно для выхода из настроек и сохранения изменений используется пункт во вкладке "Exit" с именем "**Save changes & Reset**".



