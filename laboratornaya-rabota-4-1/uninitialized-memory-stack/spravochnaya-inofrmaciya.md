# Справочная инофрмация

## Неинициализированная переменная

Неинициализированная переменная \(uninitialized variable\)— это такая переменная, которой не было присвоено начальное значение.

Использование неинициализированных переменных схоже с использованием неинициализированной памяти и может приводить к ошибкам разного рода в процессе работы программы.Примером может служить такой код:

```c
int Sum(int n)
{
  int sum, i;
 
  for (i = 0; i < n; i++)
  {
    sum = sum + 1;
  }
 
  return sum;
}
```

Переменной 'sum' не присвоено начального значения, и она содержит "мусор". В отдельных случаях, при определенном везении, там может оказаться и нулевое значение. Тогда функция будет работать правильно. Но в общем случае, результат работы функции непредсказуем. Коварство подобных ошибок в том, что программа может долгое время вести себя правильно. А потом, после смены компилятора, небольшого рефакторинга и других изменений, начать выдавать ошибочные результаты. Более того, при каждом запуске программа может вести себя по-разному.

Для предотвращения подобных ошибок в языке программирования Си++ лучше инициализировать все переменные начальным значением непосредственно при объявлении. Объявлять переменные лучше всего непосредственно перед использованием, когда уже известны их начальные значения. Тогда работоспособный пример кода будет выглядеть так:

```c
int Sum(int n)
{
  int sum = 0;
 
  for (int i = 0; i < n; i++)
  {
    sum = sum + 1;
  }
 
  return sum;
}
```

## Использование неинициализированной памяти

Использование неинициализированной памяти — это чтение данных из буфера, который был выделен, но не заполнен начальными значениями. Такое поведение программы является ошибкой, которую иногда трудно выявить. Это так называемая "[плавающая ошибка](https://ru.wikipedia.org/wiki/%D0%93%D0%B5%D0%B9%D0%B7%D0%B5%D0%BD%D0%B1%D0%B0%D0%B3)". Проявление ошибки может зависеть от версии компилятора или операционной системы, а так же от запуска "отладочной" или "релиз" версии.

Возникать ошибка может из-за неправильного порядка инициализации или ошибки синхронизации в многопоточном приложении. В любом случае это означает, что данные начинают использоваться до того как были инициализированы.

Рассмотрим пример такой ошибки:

```c
dgCollisionCompoundBreakable::dgCollisionCompoundBreakable(....)
{
  ....
  dgInt32 faceOffsetHitogram[256];
  dgSubMesh* mainSegmenst[256];
  ....
  memset(faceOffsetHitogram, 0, sizeof(faceOffsetHitogram));
  memset(mainSegmenst, 0, sizeof(faceOffsetHitogram));
  ....
}
```

Ошибка заключается в неполной инициализации массива 'mainSegmenst'. Этот код будет работать корректно в 32-битной программе, где размер указателя совпадает с размером типа 'int'. И перестанет в 64-битной программе.

### Указатели на функцию

В языке программирования C функция тоже имеет адрес и может иметь указатель. Указатель на функцию представляет собой выражение или переменную, которые используются для представления адреса функции. Указатель на функцию содержит адрес первого байта в памяти, по которому располагается выполняемый код функции.

Самым распространенным указателем на функцию является ее имя. С помощью имени функции мы можем вызывать ее и получать результат ее работы.

Но также указатель на функцию мы можем определять в виде отдельной переменной с помощью следующего синтаксиса:

```c
	тип (*имя_указателя) (параметры);
```

Здесь тип представляет тип возвращаемого функцией значения.

_имя\_указателя_ представляет произвольно выбранный идентификатор в соответствии с правилами о наименовании переменных.

И параметры определяют тип и название параметров через запятую при их наличии.

Например, определим указатель на функцию:

```c
void (*message) (void);>
```

Здесь определен указатель, который имеет имя message. Он может указывать на функции без параметров, которые возвращают тип void \(то есть ничего не возвращают\).

Применим этот указатель на функцию:

```c
#include <stdio.h>
 
void hello(void)
{
    printf("Hello, World \n");
}
void goodbye()
{
    printf("Good Bye, World \n");
}
int main(void)
{
    void (*message) (void);
     
    message=hello;
    message();
    message = goodbye;
    message();
    return 0;
}
```

Указателю на функцию можно присвоить функцию, которая соответствует указателю по возвращаемому типу и спецификации параметров:

```c
void (*message) (void);
```

НЕ будет аналогично следующему определению:

```c
void *message (void);
```

Во втором случае определен не указатель на функцию, а прототип функции message, которая возвращает указатель типа void\*.

Рассмотрим еще один указатель на функцию:

```c
#include <stdio.h>
 
int add(int x, int y)
{
    return x+y;
}
int subtract(int x, int y)
{
    return x-y;
}
int main(void)
{
    int a = 10;
    int b = 5;
    int result;
    int (*operation)(int a, int b);
     
    operation=add;
    result = operation(a, b);
    printf("result=%d \n", result);     // result=15
```

Здесь определен указатель operation, который может указывать на функцию с двумя параметрами типа int, возвращающую также значение типа int. Соответственно мы можем присвоить указателю адреса функций add и subtract и вызвать их, передав при вызове в указатель нужные значения для параметров.



