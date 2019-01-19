# فصل پنجم: Simple Better Than Complex

### در این فصل به اصولی میپردازیم که بتوان کد پیچیده ای را به کد ساده ای تبدیل کنیم.

----------------------

### جلوگیری از خلاصه نویسی:

کد ساده همیشه بهتر از پیچیده و گیج کننده است, به سه مثال زیر دقت کنید:

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



هر سه کد یک کار را انجام میدهند,‌اما کدام یک خواناتر و قابل فهم تر است؟ **بدون شک کد اول**

-------------------------

###### در بسیاری از زبانها اگر در یک **Block** فقط یک دستور وجود داشته باشد میتوان از گداشتن {} خوداری کرد و یا در زبان پایتون دستور را مقابل خود بلاک نوشت.

###### اما استفاده از این قابلیت ها اصلا توصیه نمیشود زیرا باعث عدم خوانایی کد میشود.

### برای مثال:

*python*:

```python
if hours < 24 and minutes < 60 and seconds < 60: return True
else: return False
```

به کد بالا دقت کنید, درست است که این کد کار میکند اما کد زنی به این روش اصلا توصیه **نمیشود**.

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

این کد ممکن است باعث گیج شدن برنامه نویس شود, و اصلا کد نویسی به این روش توصیه **نمیشود**.

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

استفاده صحیح از توابع باعث مرتب شدن کدها و دسته بندی هر قسمت از کد و در نتیجه خوانایی بیشتر کد میشود.

یکی از مهمترین فواید استفاده از توابع سرعت بخشیدن به **Error** یابی برنامه میباشد.

> تابع خوب تابعی است که یک کار را انجام دهد.

برنامه زیر را در نظر بگیرید که فاقد تابع است, کدها درهم شده اند و وقتی برنامه رشد کند و به صدها خط برسد دیگر پیدا کردن یک قسمت از کد, تغییر برنامه, یا رفع یک مشکل کاری بسیار دشوار خواهد بود.

*python*:

```python
def showColumns():
    # Gets arranged data and shows them in columns for each mac address

    makeColumns()
    column41S = addStar41()
    column70S = addStar70()
    column52S = addStar52()
    column53S = addStar53()

    c = 0
    print("             mac : 41")
    print("------------------------------------")
    for i in column41S:
        print(str(c) + ") " + i[0] + "  " + i[1] + "  " + i[2])
        c += 1

    print("***************************************\n")

    c = 0
    print("             mac : 70")
    print("------------------------------------")
    for i in column70S:
        print(str(c) + ") " + i[0] + "  " + i[1] + "  " + i[2])
        c += 1

    print("***************************************\n")

    c = 0
    print("             mac : 52")
    print("------------------------------------")
    for i in column52S:
        print(str(c) + ") " + i[0] + "  " + i[1] + "  " + i[2])
        c += 1

    print("***************************************\n")

    c = 0
    print("             mac : 53")
    print("------------------------------------")
    for i in column53S:
        print(str(c) + ") " + i[0] + "  " + i[1] + "  " + i[2])
        c += 1

    # Deletes extra data from RAM
    del column41S[:]
    del column70S[:]
    del column52S[:]
    del column53S[:]

    exitNum = input("Exit(y/n)? ")

    if(exitNum.upper() == 'Y'):
        exit()

    elif(exitNum.upper() == 'N'):

        columnMacForPlot = input("Enter column mac address: ")

        if columnMacForPlot == "41":

            X, Y = getRangeOfPlot(column41)

        elif columnMacForPlot == "70":

            X, Y = getRangeOfPlot(column70)

        elif columnMacForPlot == "52":

            X, Y = getRangeOfPlot(column52)

        elif columnMacForPlot == "53":

            X, Y = getRangeOfPlot(column53)

        else:
            plotData()

    else:
        plotData()

    plt.plot(X, Y, 'r')
    plt.xlabel("range")
    plt.ylabel("tempreture")
    plt.title('Tempreture plot')
	plt.show()
```



میتوان تابع بالا را به چندین تابع کوچکتر تبدیل کرد:

```python
def addStar(column):
    # Puts * for columns that dont have data after one minute from last column

    dataTime = column[0][2].split(" ")[1]
    tmp = int(dataTime.split(":")[1])

    columnS = column[:]

    for i in columnS:

        dataTime = i[2].split(" ")[1]
        minutes = int(dataTime.split(":")[1])

        if abs(tmp - minutes) > 1:
            columnS.insert(columnS.index(i), ['*', '*', '*'])

        tmp = minutes

    return columnS


def showData(column, mac):
    # Shows data of each mac address in a column

    c = 0
    print("             mac : {0}".format(mac))
    print("------------------------------------")
    for i in column:
        print(str(c) + ") " + i[0] + "  " + i[1] + "  " + i[2])
        c += 1

    print("***************************************")


def showColumns():
    # Gets arranged data and shows them in columns for each mac address

    makeColumns()
    column41S = addStar(column41)
    column70S = addStar(column70)
    column52S = addStar(column52)
    column53S = addStar(column53)

    showData(column41S, 41)
    showData(column70S, 70)
    showData(column52S, 52)
    showData(column53S, 53)

    # Deletes extra data from RAM
    del column41S[:]
    del column70S[:]
    del column52S[:]
    del column53S[:]

    plotData()


def getRangeOfPlot(column):
    # Gets range of X and Y from user and makes them for each mac addresses logs

    Y = []
    fromRow = int(input("From: "))
    toRow = int(input("To: "))

    if fromRow >= 0 and toRow < len(column41):

        X = range(fromRow, toRow)

        for i in range(fromRow, toRow):
            Y.append(column[i][0])

    else:
        plotData()

	return X, Y

def plotData():
    # Draws plot for each mac address

    exitNum = input("Exit(y/n)? ")

    if(exitNum.upper() == 'Y'):
        exit()

    elif(exitNum.upper() == 'N'):

        columnMacForPlot = input("Enter column mac address: ")

        if columnMacForPlot == "41":

            X, Y = getRangeOfPlot(column41)

        elif columnMacForPlot == "70":

            X, Y = getRangeOfPlot(column70)

        elif columnMacForPlot == "52":

            X, Y = getRangeOfPlot(column52)

        elif columnMacForPlot == "53":

            X, Y = getRangeOfPlot(column53)

        else:
            plotData()

    else:
        plotData()

    plt.plot(X, Y, 'r')
    plt.xlabel("range")
    plt.ylabel("tempreture")
    plt.title('Tempreture plot')
    plt.show()

plotData()
```

در برنامه اول کد ما شامل یک تابع است که در مثال بعد تبدیل به پنج تابع شده است که درون یکدیگر صدا زده شده اند ابن کار باعث کمتر شدن تعداد خطهای برنامه و درنتیجه مرتب شدن برنامه و میشود.

##### برای مشاهده کد کامل برنامه بالا به این [لینک](https://github.com/ahmadabd/python-check-logger.git) مراجعه فرمایید.