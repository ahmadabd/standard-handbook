# فصل دوم: نامگذاری متغیرها

### روش‌های مختلفی برای نامگذاری یک متغیر وجود دارد که می‌توانید بسته به نیاز یا سلیقه یکی از آنها را انتخاب کنید.

انتخاب نام مناسب برای متغیرها بسیار مهم است زیرا نام هر متغیر **توضیح** مختصری از دلیل تعریف آن متغیرمی‌باشد.

این استانداردها در تمامی زبانهای برنامه‌نویسی یکسانند.

---------------------

### متغیر چیست؟

متغیر نامی است که به اشاره‌گری که به آدرسی از حافظه اشاره می‌کند داده می‌شود.

متغیر ها شامل انواع مختلفی هستند که نوع داده‌ای اطلاعات ذخیره شده در حافظه را مشخص می‌کنند, برای مثال stringو integer و float و ...

> برای مطالعه بیشتر در مورد متغیرها به این [لینک](https://www.tutorialspoint.com/computer_programming/computer_programming_variables.htm) مراجعه کنید.

--------------------

## انواع روش‌های نامگذاری متغیرها:

### ۱. نامگذاری متغیر‌های `private` و `protected`:

بهتر است قبل از نام متغیر‌هایی که بصورت `private` یا `protected` تعریف می‌شود از **underscore** استفاده کنیم تا در طول برنامه به برنامه‌نویس یادآوری شود که متغیر مورد نظر دارای دسترسی `private` یا `protected`  می‌باشد.

> **`private` و `protected`:**
>
> در برنامه نویسی شی‌گرا می توانیم برای هر method یا property دسترسی public, private, protected, ... تعریف کنیم.
>
> **برای یادگیری بیشتر برنامه‌نویسی شی‌گرا روی [لینک](https://en.wikipedia.org/wiki/Object-oriented_programming) کلیک کنید.**

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

متغیر‌هایی را که در کد مقدار ثابت و تاثیر‌گذاری دارند را بصورت **ثابت** در ابتدادی کد تعریف کنید تا در صورتی که نیاز باشد مقدار آن متغیر را تغییر دهید فقط یک بار این کار را انجام دهید تا لازم نباشد در طول کد بارها این کار را انجام دهید.

ثوابت را معمولا با حروف بزرگ تعریف می‌کنند تا برنامه‌نویسان در هر کجای کد که با این متغییر‌ها برخورد می‌کنند بدانند که با یک متغیر از نوع ثابت برخورد کرده‌اند که دارای دسترسی **فقط خواندنی** (read only) می‌باشد و نمی‌توانند مقدار آنرا تغییر دهند.

> برای مطالعه بیشتر در مورد ثوابت به این [لینک](https://www.geeksforgeeks.org/constants-in-c/) مراجعه کنید.

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

در این روش با استفاده از یک حرف در ابتدای نام متغیر نوع آن متغیر را مشخص می‌کنیم.

از `i` برای نوع integer و از `s` برای string , به همین ترتیب کاراکتر اول هر نوع داده‌ای را در ابتدای نام آن متغیر می‌گذاریم.

*javaScript*:

```javascript
var sName = "Lieutenant Commander Geordi La Forge";
var iAge = 22
```



### ۴. روش camelCase:

در این روش اگر از چند کلمه تشکیل شده باشد حرف نخست کلمه اول را با حرف کوچک و حرف  نخست بقیه کلمات رو با حرف بزرگ می‌نویسیم.

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

در این روش اگر نام متغیر ما از چند کلمه تشکیل شده باشد بین هر کلمه یک **underscore** می گذاریم.

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

در این روش اگر نام متعیر از چند کلمه تشکیل شده باشد ابتدای هر کلمه را با حرف بزرگ شروع می‌کنیم.

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

در این روش برای هر نوع شی موجود یک پیشوند درنظر گرفته می‌شود تا از روی  نام شی بتوان به نوع آن پی‌برد. در ادامه و پس از این پیشوندها سایر کلمات  بر اساس روش **Pascal Casing** نوشته می‌شوند.

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

