[[pywinauto]]

What is pywinauto — pywinauto 0.6.8 documentation

PyInspect - Onject  확인 용 GUI (https://github.com/pywinauto/py_inspect.git)

윈도우 요소들을 모두 객체로 변환

pywinauto는 윈도우 소프트웨어의 셀레니움(질문)

  

→ element 순서나 정렬 기준이 있는건지 확인 필요. 뭐가 뭘 말하는지 정확히 모르겠음.

→ GUI 기반으로 작동(background로는 할 수 있는듯?). vmware 같은 VM은 제어 못함 (pyvmomi 로 vmware 제어 가능한듯). 

→ 간단 사용 결과: 마우스 클릭 이벤트 시 마우스 커서가 안 움직임.
  
  

[refer]   
: https://github.com/pywinauto/pywinauto/issues/519

[click event with the child window focus]  
```
app = Application(backend="uia").connect(title="통합 문서1 - Excel")
dlg = app.window(title='통합 문서1 - Excel')
edit = dlg.child_window(auto_id='TabInsert')
edit.click_input()
```

[using descendants(depth=1) to find child things]  
.. https://github.com/pywinauto/pywinauto/issues/1246  
.. https://github.com/pywinauto/pywinauto/issues/1064  

[what is visiable_onley=False]  
.. https://github.com/pywinauto/pywinauto/issues/817  


[to read later when chance]  
.. https://github.com/pywinauto/pywinauto/issues/556  
  
########################################################

[[win32gui, win32api, win32con]]  

.. mouse click event with interacting mouse cursor  

.. https://timgolden.me.uk/pywin32-docs/contents.html  

.. 최신 window 자체 app들은 sendmessage/postmessage 안 먹히는듯.  
  
refer  
.. https://gall.dcinside.com/mgallery/board/view/?id=umamusu&no=59245  
.. https://github.com/MandarGogate/AM-AIR-MOUSE/blob/b8ffb7665cd3147c1e4d3913035600a1d8c2a6bc/Mouse-Driver.py  
.. https://wikidocs.net/157024  
.. https://www.cnblogs.com/zyip/p/17184391.html  
.. https://qna.habr.com/answer?answer_id=1687411#comments_list_1687411  
.. https://wiki.changwoo.pe.kr/project:peekwindow  
  

[SendMessage(hWndButton1, BM_CLICK, 0, 0);]  
```
HWND hWndMsgBox = NULL; 
HWND hWndButton1 = NULL, hWndButton2 = NULL; 

hWndMsgBox = FindWindow("#32770", NULL); 
hWndButton1 = FindWindowEx(hWndMsgBox, NULL, "Button", "확인"); 
hWndButton2 = FindWindowEx(hWndMsgBox, hWndButton1, "Button", "취소"); 

SendMessage(hWndButton1, BM_CLICK, 0, 0); 
```
https://blog.saja92.net/m/entry/FindWindowEx-%ED%95%A8%EC%88%98%EB%A1%9C-%EC%B0%BE%EC%9D%80-%EB%B2%84%ED%8A%BC%EC%97%90-%ED%81%B4%EB%A6%AD-%EB%A9%94%EC%84%B8%EC%A7%80-%EB%B3%B4%EB%82%B4%EA%B8%B0

[[pywin32 와 pyautogui DPI 차이]]  

pywin32: DPI 고려 안함

pyautogui: DPI 고려함

https://github.com/asweigart/pyautogui/issues/697

##########################################################

[[uiautomation]]

https://github.com/yinkaisheng/Python-UIAutomation-for-Windows
git → python-uiautomation-for-windows

pip install uiautomation

[uiautomation] python에서 windows GUI 객체 컨트롤하기 (velog.io)

→ 간단 사용 결과: 마우스 클릭은 마우스 커서 실제 움직임 발생. 

##########################################################
[[pyvda]]

https://github.com/mrob95/pyvda

Python Virtual Desktop Accessor

#########################################################

[[RPA-Python]]

https://github.com/tebelorg/RPA-Python
  


[[rpaframework]]

https://rpaframework.org/libraries/javaaccessbridge/index.html

java bridge 도 가능

  

[[etc]]

pyautogui, clicknium -> GUI, 키보드, 마우스 기반
Power automate, autoit v3 -> Tool

1차 검토 결과: 
차세대 WebUI는 selenium + window object 기반으로 하고 vmware 나 그 이외의 것들 다 image object detection 기반으로 하는게 나을듯?

#########################################################################
""" 
window focus 없이 type 하는방법을 찾음. window 최소화 되어있어도 잘 작동.  
문제는 child를 class_name으로밖에 못 찾을듯.   
class_name 없는 놈은 uiatomation으로 child 찾고 handle 있으면(Edit 은 handle 있는듯?) SendMessage 하기.(최소화에서도 작동하는듯)   
만약 handle 없으면(click 같은거나..) rectangle 상대 좌표 기반으로 click(좌표 기반은 window 최소화하면 작동 안됨.)  
pywin32 방식의 단점이 old app은 elements를 잘 찾는데 newer app의 element는 못찾아서 uiautomation으로 찾아야되는듯.  
test5.py가 최종이고 test3.py 도 참고 할만함.  
automation.py -t 0 -n, print current active window's controls, show fullname  
automation.py -r -d 1 -t 0, print desktop(the root of control tree) and it's children(top level windows)  
windos 기본 프로그램을 uiautomation/pywinauto로 hwnd 얻어서 enter 혹은 click 보낼수 있는지 확인 필요.  
click vs clcik_at 차이?
""" 

""" 
[tree 구조 및 hwnd 확인 tool]  
spy++ : win32로 찾을 수 있는 독립적인 hwnd 까지만 보여주는 듯  
inspect: hwnd이 없는 존재도 tree(child) 끝까지 보여주는듯  

[child 찾는 법]  
win32 : hwnd 있는 존재까지만 child 찾을 수 있는듯? title/class_name 으로만 검색 가능  
uiautomation: depth까지 해서 쉽게 child object 찾을 수 있음. 하지만 그게 꼭 hwnd까지 있다는 보장은 안됨.  
pywinauto: child_window method로 title,class_name, autoid 로 하위 child 검색가능. hwnd을 항상 보장하지는 않음.  

[click event]  
background: win32gui.PostMessage 이용. windows 기본 프로그램은 안되는 경우도 있음.  
[background종류]  
when window minimize : 해당 element의 hwnd을 알고 있는 경우. 해당 element click.  
*click  
'''
win32gui.PostMessage(hwnd, win32con.WM_LBUTTONDOWN, win32con.MK_LBUTTON, 0)
win32gui.PostMessage(hwnd, win32con.WM_LBUTTONUP, win32con.MK_LBUTTON, 0)
'''
*enter
'''
win32gui.PostMessage(hwnd, win32con.WM_KEYDOWN, win32con.VK_RETURN, 0)
win32gui.PostMessage(hwnd, win32con.WM_KEYUP, win32con.VK_RETURN, 0)
'''
when not minimize and behind other window : 해당 window 내 상대좌표로 click event. parent window hwnd만 알고있고 child는 rectangle만 알고있는 상황. window 기본 프로그램중에 안 먹히는것도 있음.  

when not minimize and frontmost : 스크린의 절대좌표 기준으로 click event. 해당 window는 항상 맨 앞 window 여야됨.  

"""


