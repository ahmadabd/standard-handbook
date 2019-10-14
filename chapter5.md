# فصل پنجم: Simple Better Than Complex

### در این فصل به اصولی می‌پردازیم که بتوان کد پیچیده‌ای را به کد ساده‌ای تبدیل کنیم.

----------------------

### جلوگیری از خلاصه نویسی:

کد ساده همیشه بهتر از کد پیچیده و گیج کننده است, به سه مثال زیر دقت کنید:

*C*:

```c
if (hours < 24 && minutes < 60 && seconds < 60)
{
    return true;
}
else
{
    return false;
}
```

and

```c
if (hours < 24 && minutes < 60 && seconds < 60)
    return true;
else
    return false;
```

and

```c
return hours < 24 && minutes < 60 && seconds < 60;
```



هر سه کد یک کار را انجام می‌دهند,‌اما کدام یک خواناتر و قابل فهم‌تر است؟ **بدون شک کد اول**

به دو کد زیر دقت کنید و کد بهتر را انتخاب کنید:

```python
## factorial
def fact(n):
    return 1 if n <= 1 else n * fact(n - 1)

print(fact(4))
```

یا

```python
## factorial
def fact(n):
    if n <= 1:
        return 1
    else:
        return n * fact(n - 1)

print(fact(4))
```



-------------------------

در بسیاری از زبان‌ها اگر در یک **Block** فقط یک دستور وجود داشته باشد میتوان از گداشتن {} خوداری کرد و یا در زبان پایتون دستور را مقابل خود بلاک نوشت.

اما استفاده از این قابلیت‌ها اصلا توصیه نمی‌شود زیرا باعث عدم خوانایی کد می‌شود.

### برای مثال:

*python*:

```python
if hours < 24 and minutes < 60 and seconds < 60: return True
else: return False
```

به کد بالا دقت کنید, درست است که این کد کار می‌کند اما کد زنی به این روش اصلا توصیه **نمی‌شود**.

#### بهتر است کد بالا بصورت زیر نوشته شود:

```python
if hours < 24 and minutes < 60 and seconds < 60: 
    return True
else: 
    return False
```



يا این کد را در نظر بگیرید:

*C*:

```c
if (hours < 24)
    if (minutes < 60)
         if (seconds < 60)
    		return true;
return false;
```

این کد ممکن است باعث گیج شدن برنامه‌نویس شود, و اصلا کد‌نویسی به این روش توصیه **نمی‌شود**.

#### بهتر است کد بالا بصورت زیر نوشته شود:

```c
if (hours < 24 && minutes < 60 && seconds < 60)
{
    return true;
}
else
{
    return false;
}
```





-----------------------



### اصول Functional Programming:

> برای مطالعه در مورد Functional Programming [اینجا](https://hkupty.github.io/2016/Functional-Programming-Concepts-Idioms-and-Philosophy/) کلیک کنید.

استفاده صحیح از توابع باعث مرتب شدن کدها و دسته‌بندی هر قسمت کد و در نتیجه خوانایی بیشتر کد می‌شود.

یکی از مهمترین فواید استفاده از توابع سرعت بخشیدن به عیب‌یابی برنامه می‌باشد.

> تابع خوب تابعی است که یک کار را انجام دهد.

> برای مشاهده کد‌های این بخش به این [لینک](https://github.com/ahmadabd/python-check-logger.git) مراجعه فرمایید.