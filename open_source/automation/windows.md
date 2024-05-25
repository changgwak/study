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
app = Application(backend="uia").connect(title="통합 문서1 - Excel")
dlg = app.window(title='통합 문서1 - Excel')
edit = dlg.child_window(auto_id='TabInsert')
edit.click_input()

[using descendants(depth=1) to find child things]
https://github.com/pywinauto/pywinauto/issues/1246
https://github.com/pywinauto/pywinauto/issues/1064

[what is visiable_onley=False]
https://github.com/pywinauto/pywinauto/issues/817


[to read later when chance]
https://github.com/pywinauto/pywinauto/issues/556

########################################################

[[win32gui, win32api, win32con]]

.. mouse click event with interacting mouse cursor

.. https://timgolden.me.uk/pywin32-docs/contents.html

.. 최신 window 자체 app들은 sendmessage/postmessage 안 먹히는듯.

refer
https://gall.dcinside.com/mgallery/board/view/?id=umamusu&no=59245
https://github.com/MandarGogate/AM-AIR-MOUSE/blob/b8ffb7665cd3147c1e4d3913035600a1d8c2a6bc/Mouse-Driver.py
https://wikidocs.net/157024
https://www.cnblogs.com/zyip/p/17184391.html
https://qna.habr.com/answer?answer_id=1687411#comments_list_1687411
https://wiki.changwoo.pe.kr/project:peekwindow


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
