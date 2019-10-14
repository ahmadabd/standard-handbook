# فصل سوم: قواعد نامگذاری توابع و کلاس‌ها

این قواعد بسیار مشابه نامگذاری متغیرها هستند اما از ابتدا آنهارا مرور می‌کنیم.

----------------------------

## تابع:

تابع بلاکی شامل خط یا خطوطی کد است که وظیفه مشخصی دارد.

تابع در واقع ساختاری از کد را در بک خط خلاصه می‌کند و معمولا نتیجه‌ای را برمی‌گرداند.

> برای مطالعه بیشتر در مورد تابع [اینجا](https://www.cs.utah.edu/~germain/PPS/Topics/functions.html) کلیک کنید.

-----------------------------------

### در اینجا قواعد  نامگذاری تابع و کلاس را بیان می‌کنیم:

یک نکته بسیار مهم در نامگذاری توابع استفاده از یک **فعل** در نام تابع است که بیانگر عملی است که تابع انجام می‌دهد.

## به مثال‌های زیر توجه کنید:

- فرض کنید تابعی دارید که عمل **گرفتن** (**get**) انجام می‌دهد, برای مثال گرفتن نام کاربر: `getUserName`
- یا تابعی که نام گرفته شده را در یک متفیر محلی **قرار می‌دهد**(**set**): `setUserName`
- تابعی که عمل **reload** اطلاعات از دیتابیس را انجام می‌دهد: `reloadData`

*در* هر سه مثال بالا نام توابع دارای افعال(**set**, **get**, **reload**) هستند که وظیفه توابع را توصیف می‌کنند.

#### در سه مثال بالا از روش camelCase برای نامگذاری  استفاده شده است, اما می‌توانید از دیگر استانداردها نیز استفاده کنید.

--------------------------

## قواعد نامگذاری توابع:

### ۱. روش camelCase:

در این روش اگر از چند کلمه تشکیل شده باشد حرف نخست کلمه اول را با حرف کوچک و حرف  نخست بقیه کلمات رو با حرف بزرگ می‌نویسیم.

*python*:

```python
class Test:
	
    def setUserName(self, name):
    	self.name = name
       
    def getUserName(self):
        return self.name
```



*C*:

```c
void setUserName(char* name){
    
    // codes
}

char* getUserName(){
    
    // codes
}
```



### ۲. روش underScore:

در این روش اگر نام تایع ما از چند کلمه تشکیل شده باشد بین هر کلمه یک **underscore** می‌گذاریم.

*python*:

```python
class Test:
	
    def set_user_name(self, name):
    	self.name = name
       
    def get_user_name(self):
        return self.name
```



*C*:

```c
void set_user_name(char* name){
    
    // codes
}

char* get_user_name(){
    
    // codes
}
```



### ۳. روش pascalCase:

در این روش اگر نام تابع از چند کلمه تشکیل شده باشد ابتدای هر کلمه رو با حرف بزرگ شروع می‌کنیم.



*python*:

```python
class Test:
	
    def SetUserName(self, name):
    	self.name = name
       
    def GetUserName(self):
        return self.name
```



*C*:

```c
void SetUserName(char* name){
    // codes
}

char* GetUserName(){
    
    return name;
}
```



### ۴. magic functions:

در برخی زبانهای برنامه‌نویسی توابعی به اسم **magic function** وجود دارند که با دو **underScore** در ابتدا و دو **underScore** در انتهای نام تابع تعریف می‌شوند.

*python*:

```python
from os.path import join

class FileObject:

    def __init__(self, filepath='~', filename='sample.txt'):
        # open a file filename in filepath in read and write mode
        self.file = open(join(filepath, filename), 'r+')

    def __del__(self):
        self.file.close()
        del self.file
```



### ۵.  نامگذاری توابع `private` و `protected`:

بهتر است قبل از نام توابعی  که بصورت `private` یا `protected` تعریف می‌شود از **underscore** استفاده کنیم تا در طول برنامه به برنامه‌نویس یادآوری شود که تابع مورد نظر بصورت `private` یا `protected` تعریف شده است.

*PHP*:

```php
// This variable is not available outside of the class
private $_someVariable;
 
class MyClass {
   // This method is only available from within this class, or
   // any others that inherit from it. 
    
   protected function __behindTheScenesMethod() {}
   private function __getUserInfo(){} 
}
```





-------------------------------

## قواعد نامگذاری کلاسها:

## کلاس:

در برخی از زبان‌ها قاعده‌ جدیدی بنام **شی‌گرای** بوجود آمد, به این صورت که بخشی از کدها درون بلاکی بنام `class` قرار می‌گیرند

در برنامه‌نویسی شی‌گرا ساختار اصلی برنامه‌ شی‌ است در واقع داده‌ها و توابعی که قرار است روی آن داده‌ها کار کنند در قالبی بنام شی قرار گرفته و یک واحد را تشکیل داده و کپسوله می‌شوند, پس توابع خارجی دیگر نمی‌توانند به آن داده‌ها دسترسی داشته و آنها را تغییر دهند.

##### برنامه‌نویسی شی‌گرا به نسبت از برنامه‌نویسی تحت تابع کارامدتر و پیچیده‌تر است.

### دلایل برتری برنامه‌نویسی شی‌گرا:

- قابلیت سازماندهی بهینه تر کدها
- قابلیت شکستن برنامه به اجزای ساده‌تر و کوچکتر
- امنیت بالاتر

> برای مطالعه بیشتر روی کلاس‌ها [اینجا](https://caml.inria.fr/pub/docs/oreilly-book/html/book-ora140.html) کلیک کنید.

---------------------------

در نامگذاری کلاس‌ها نیز مانند نامگذاری توابع و متغیرها از روش‌های **camelCase**, **pascalCase**, **underScore**, ... استفاده می‌شود.

تنها نکته‌ای که در نامگذاری `class` باید به آن توجه کنیم شروع کلمه اول نام کلاس با حرف بزرگ می‌باشد.



*python*:

```python
class Father:
    ## codes
    
class Child(Father):
    ## codes
```



*PHP*:

```php
// This variable is not available outside of the class
private $_someVariable;
 
class MyClass {
   // This method is only available from within this class, or
   // any others that inherit from it. 
   protected function __behindTheScenesMethod() {}
}
```

