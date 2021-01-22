## 5-1 File / Exception / Log Handling

Exception : 예상이 가능한 예외, 불가능한 예외
-	발생 여부를 사전에 인지할 수 있는 예외
-	사용자의 잘못된 입력, 파일 호출 시 파일 없음
-	개발자가 반드시 명시적으로 정의 해야함
-	인터프리터 과정에서 발생하는 예외, 개발자 실수
-	리스트의 범위를 넘어가는 값 호출, 정수 0으로 나눔
-	수행 불가시 인터프리터가 자동 호출

예외 처리
-	없는 파일 호출 -> 파일 없음을 알림
-	게임 이상 종료 -> 게임 정보 저장

Exception Handling 문법
-	try ~ except 문법
try : 예외 발생 가능 코드 except <Exception Type> : 예외 발생시 대응하는 코드
for I in range(10):
try : print (10 / i)
except : ZeroDivisionError: print(“Not divided by 0”)
finally : 관계 없이 자동으로 실행
raise : 필요에 따라 강제로 Exception을 실행
assert : 특정 조건에 맞지 않을 경우 예외 발생
assert 예외 조건

File Handling 문법
기본적인 파일 종류로 text 파일과 binary 파일로 나뉨
컴퓨터는 text파일을 처리하기 위해 binary 파일로 변환시킴

Python File I/O
파이썬은 파일 처리를 위해 “open” 키워드를 사용함
f = open(“<파일이름>”, “접근 모드”)
f.close()

파일 열기 모드 : r(읽기 모드) , w(쓰기 모드), a(추가 모드)

os 모듈을 사용하여 디렉토리 다루기

pathlib :  모듈을 사용하여 path를 객체로 다룸

pickle : 파이썬의 객체를 영속화하는 built-in 객체
데이터, object 등 실행중인 정보를 저장 -> 불러와서 사용
저장해야하는 정보, 계산 결과 등 활용이 많음

logging
-	프로그램이 실행되는 동안 일어나는 정보를 기록으로 남기기
-	유저의 접근, Exception, 특정 함수의 사용
-	console 화면에 출력, 파일에 남기기, db에 남기기
-	기록된 로그를 분석하여 의미있는 결과를 도출 할 수 있음
-	실행시점에서 남겨야 하는 기록, 개발 시점에서 남겨야 하는 기록

import logging -> debug, info, warning , error, critical
-	log 관리시 가장 기본이 되는 설정 정보
-	debug : 개발 시 처리 기록을 남겨야 하는 로그 정보를 남김
-	info : 처리가 진행되는 동안의 정보를 알림
-	warning : 사용자가 잘못 입력한 정보나 처리는 가능하나 원래 개발 시 의도치 않은 정보가 들어왔을 때 알림
-	error : 잘못된 처리로 인해 에러가 났으나, 프로그램은 동작할 수 있음을 알림
-	critical : 잘못된 처리로 데이터 손실이나 더이상 프로그램이 동작할 수 없음을 알림

configparser : 프로그램의 실행 설정을 file에 저장함
section, key, value 값의 형태로 설정된 설정 파일을 사용
설정 파일을 Dict Type으로 호출 후 사용

argparser : console 창에서 프로그램 실행 시 setting 정보를 저장함 (실행 시점에)

logging formmater : log의 결과 값의 format을 저장해줄 수 있음

## 5-2 Python Data Handling

Csv : Comma Separte Value
-	Csv, 필드를 쉼표로 구분한 텍스트 파일
엑셀 양식의 데이터를 프로그램에 상관없이 쓰기 위한 데이터 형식이라고 생각하면 쉬움
탭, 빈칸등으로 구분해서 만들기도 함
엑셀에서는 다른 이름 저장 기능으로 사용 가능
파이썬에서는 간단히 csv를 처리하기 위해 csv 객체를 제공함

Web : 우리가 늘 쓰는 인터넷 공간의 정식 명칭
	요청 -> 처리 -> 응답 -> 렌더링 순으로 동작

	HTML : 웹 상의 정보를 구조적으로 표현하기 위한 언어

	정규식 : 복잡한 문자열 패턴을 정의하는 문자 표현 공식
	특정한 규칙을 가진 문자열의 집합을 추출

xml : 데이터의 구조와 의미를 설명하는 tag를 사용하여 표시하는 언어
	tag와 tag 사이에 값이 표시되고, 구조적인 정보를 표현할 수 있음
	정보의 구조에 대한 정보인 스키마와 DTD 등으로 정보에 대한 	정보에 대한 정보가 표시되며, 용도에 따라 다양한 형태로 변경 	가능
	
JSON : Java Script의 데이터 객체 표현 방식, 간결성으로 기계/인간이 모	두 이해하기 편함.
	Key:Value 형식으로 자료를 표현
	JSON 모듈을 사용하여 손 쉽게 파싱 및 저장 가능
