# Tk_time
tkinter 라이브러리를 사용해서 Python 언어로 현재 시각을 알려주는 버튼을 생성하는 프로그램 개발

## 25년 다시 복습

## 창 생성

기본적으로 tkinter 라이브러리를 불러오고 창을 만드는 함수 Tk()를 생성 한 뒤 win 변수에 저장한 후 mainloop 함수로 실행한다.
```python
from tkinter import *
win = Tk()

win.mainloop()
```

## 창의 기본적인 옵션으로 geometry(창크기), title(제목), option_add(세부 옵션 전체 폰트 설정을 설정한다.

창을 생성하는 win = Tk()와 실행하는 win.mainloop() 사이에 창의 기본옵션(창크기, 제목, 세부옵션(전체폰트)를 설정한다.

```python
from tkinter import *
win = Tk()
win.geometry("300x100")
win.title("What time")
win.option_add("*Font", "궁서 20")


win.mainloop()
```

## 버튼 생성하고 배치하기

버튼을 생성하는 코드 Button()함수에 만든 창(win)을 매개변수로 넣고 btn 변수에 저장한 뒤 버튼을 배치하는 함수 pack()을 btn뒤에 붙여준다.

```python
from tkinter import *
win = Tk()
win.geometry("600x100")
win.title("What time")
win.option_add("*Font", "궁서 20")

btn = Button(win)

btn.pack()

win.mainloop()
```

버튼생성과 배치함수 사이에 버튼의 기본옵션으로 버튼안의 텍스트(text)와 가로너비(width)를 설정한다.

```python
from tkinter import *

win = Tk()
win.geometry("600x100")
win.title("What time")
win.option_add("*Font", "궁서 20")

btn = Button(win)
btn.config(text="현재 시각")
btn.config(width=30)
btn.pack()
```

win.mainloop()
```

시간 관련 함수들을 사용하기 위해서 파이썬에서 제공하는 datetime 라이브러리를 import 해준다.
```python
from datetime import datetime
```

command what_time 함수를 받고 버튼을 눌렀을 때 버튼안의 텍스트를 현재 시간으로 바꿔주는 what_time 함수를 생성한다.
```python
def what_time():
    dnow = datetime.now()
    btn.config(text=dnow)

btn.config(command=what_time)
```
## 최종코드와 현재 시간을 알려주는 버튼 프로그램

최종코드는 다음과 같다.
```python
from tkinter import *
from datetime import datetime

win = Tk()
win.geometry("600x100")
win.title("What time")
win.option_add("*Font", "궁서 20")


def what_time():
    dnow = datetime.now()
    btn.config(text=dnow)


btn = Button(win)
btn.config(text="현재 시각")
btn.config(width=30)
btn.config(command=what_time)
btn.pack()

win.mainloop()
```

다음은 생성된 프로그램의 모습이다.

버튼을 누르기 전
![현재시각](https://user-images.githubusercontent.com/58906858/151652420-cbe17627-9fe7-4291-a4bc-f239fc4519a8.png)

버튼을 누른 뒤
![현재시각1](https://user-images.githubusercontent.com/58906858/151652437-ee674c3d-5ca6-4426-80f5-0439dd2e7e12.png)

현재시각이 잘 나오는 것을 알 수 있다.




    

