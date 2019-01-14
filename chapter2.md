# فصل دوم: نامگذاری متغیرها

### روش های مختلفی برای نامگذاری یک متغیر وجود دارد که میتوانید بسته به نیاز یا سلیقه خودتان یکی از آنها را انتخاب کنید.

انتخاب نام مناسب برای متغیرها بسیار مهم است زیرا نام هر متغیر باید **توضیح** مختصری از دلیل تعریف آن متغیر باشد.

این استانداردها در تمامی زبانهای برنامه نویسی یکسانند.

پس با حوصله بیشتر نام متغیر هاتونو انتخاب کنید ;)

---------------------

## انواع روش های نامگذاری متغیرها:

### ۱. نامگذاری متغیر های `private` و `protected`:

بهتر است قبل از نام متغیر هایی که بصورت `private` یا `protected` تعریف میشود از **underscore** استفاده کنیم تا در طول برنامه به برنامه نویس یادآوری شود که متغیر مورد نظر بصورت `private` یا `protected` تعریف شده است.

*C#*:

```c#
class A{
    protected int _someVariable;
    private int _counter;
    
    public string name;
}
```



*PHP*:

```php
private $_someVariable;
 
class MyClass {
    
   protected function __behindTheScenesMethod() {}
}
```



### ۲. نامگذاری ثوابت(constant):

ثوابت متغیرهایی هستند که در ابتدای برنامه تعریف و مقدار دهی میشوند و در طول برنامه *read only* هستند یعنی نمیتوان مقدار جدید در آنها قرار داد.

بهتر است این متغیرها کاملا با نام بزرگ تعریف شوند تا به برنامه نویس در طول برنامه نویس یادآوری شود که این متغیر از نوع `ثابت` است و نمیتواند مقدار آنرا تغییر دهد.

*javaScript*:

```javascript
var TAXRATE = .0825;
```



*PHP*:

```php
define('TAXRATE', .0825);
```



*C*:

```c
const SPEED = 9600;
// or
#define SPEED 9600
```



### ۳. روش single letter Prefixies:

در این روش با استفاده از یک حرف در ابتدای نام متغیر نوع آن متغیر را مشخص میکنیم.

از `i` برای نوع integer و از `s` برای string , به همین ترتیب کاراکتر اول هر نوع را در ابتدای نام آن متغیر میگذاریم.

*javaScript*:

```javascript
var sName = "Lieutenant Commander Geordi La Forge";
var iAge = 22
```



### ۴. روش camelCase:

این روش که روش مورد علاقه خودمم هست :) به این ترتیبه که اگر نام متغیر ما از چند کلمه تشکیل شده باشه حرف اول کلمه اول رو با حروف کوچک و حرف اول بقیه کلمات رو با حروف بزرگ مینویسیم.

*javaScript*:

```javascript
var preacherOfSockChanging = 'Lieutenant Dan';
```



*python*:

```python
 preacherOfSockChanging = 'Lieutenant Dan'
```



*C*:

```c
int  preacherOfSockChanging = 'Lieutenant Dan';
```



### ۴.  روش underScore:

در این روش اگر نام متغیر ما از چند کلمه تشکیل شده باشه بین هر کلمه یک **underscore** میگذاریم.

*javaScript*:

```javascript
var preache_of_sock_changing = 'Lieutenant Dan';
```



*python*:

```python
preache_of_sock_changing = 'Lieutenant Dan'
```



*C*:

```c
int preache_of_sock_changing = 'Lieutenant Dan';
```



### ۵. روش  **Pascal Casing**:

در این روش اگر نام متعیر از چند کلمه تشکیل شده باشه ابتدای هر کلمه رو با حرف بزرگ شروع میکنیم.

*javaScript*:

```javascript
var FirstName = "mehdi"
```



*python*:

```python
FirstName = "mehdi"
```



*C*:

```c
int NameOfVariable = 123;
```



### ۶. روش مجارستانی (Hungerian):

در این روش برای هر نوع شی موجود یک پیشوند درنظر گرفته می‌شود تا از روی  نام شی بتوان به نوع آن پی برد. در ادامه و پس از این پیشوندها سایر کلمات  بر اساس روش **Pascal Casing** نوشته می‌شوند.

*C*:

```c
char* strFirstName = "ahmad";
int intAge = 22;
```



*python*:

```python
strFirstName = "ahmad"
intAge = 22
```

