CCaMaGui Batch to Executable 01.25.01.11
========================================
> 01.25.01.11 배치데이타를 인코딩하여 저장하도록 수정함.
              ::mode echo
              애석하게도 ::mode echo는 아직도 보완할 점이 많다. 
              여러가지 공부하며 적용해 보아도, 계획한 것과 같이 원활하게 작동하지 않는다.

> 01.00.00.00 정식 1.0 버전
              처음 계획했던 모든 기능을 구현함. 
              아직, 배치파일 오류처리 미숙등 완전하다고는 할 수 없으나, 구상한 모든 기능을 구현함.

              ::mode show
                배치화일을 직접실행했을 때와 같이 콘솔창이 열림

              ::mode hide
                사용자입력이 없는 배치파일을 콘솔창이 없이 실행하도록 함.
                (사용자입력이 있으면 무한루프에 빠지므로 주의 필요)

              ::mode echo
                사용자입력이 있으면 내장된 콘솔창이 열리고 입력대기하도록 확장된 모드입
                echo consol_show : 내장된 콘솔창을 보임.
                echo consol_hide : 내장된 콘솔창을 숨김(디폴트 값).
                pause <프롬프트> : <프롬프트>를 출력하고 사용자 입력대기
                set /p <변수>=<프롬프트> : <프롬프트>를 출력하고 사용자가 입력한 값을 <변수>에 저장
                choise /C <키> /M <프롬프트> : <프롬프트>를 출력하고 사용자의 입력키값을 반환
                timeout /t <시간(초)> : <시간(초)>간 대기후 계속 진행

> 00.24.10.26 "echo consol" 모드 추가
              echo consol_show : 사용자 모든 콘솔을 보이게 합니다.
              echo consol_hide : 사용자 모든 콘솔을 보이지 않게 합니다.
              pause : 콘솔창을 열고(echo consol_ 에 상관없이) 사용자의 입력 대기
              set /p <변수>=<프롬프트> : <변수>라는 환경변수에 사용자의 입력값을 설정
              - timeout 및 choice 명령은 아직 개발중에 있음. 지속적으로 업데이트 예정

> 00.24.10.18 <버그> 현재폴더가 실행폴더로 변경되지 않도록 수정함.

> 00.24.10.17 실행되는 파일의 경로를 참조할 수 있는 변수 처리에 누락된 변수 추가함.
              현재, 처리 가능한 변수는 다음과 같음.
              %~p : \$Core\Example\                 //경로를 참조
              %~0 : Example                         //파일이름 참조
              %~n : Example                         //파일이름 잠조
              %~x : .exe                            //파일확장자 참조
              %~nx : Example.exe                    //확장자를 포함한 파일이름 참조
              %~dp : C:\$Core\Example\              //드라이브를 포함한 화일 경로 참조
              %~dpnx : C:\$Core\Example\Example.exe //드라이브, 경로, 확장자를 포함한 화일이름 참조
              %~f0 : C:\$Core\Example\Example.exe   //드라이브, 경로, 확장자를 포함한 화일이름 참조
              %~fs0 : C:\$Core\Example\Example.exe  //드라이브, 경로, 확장자를 포함한 화일이름 참조

> 00.24.10.15 "파일 버전"이 설정한 버전으로 변경되도록 함.

> 00.24.10.15 <버그> Hide Mode에서 멋대로 끝내버리는 것 수정. 
              <버그> Icon File이 없는대도 아이콘 업데이트 시도하는 것 수정

> 00.24.10.14 실행파일 버전정보 업데이트 기능추가 

> 00.24.10.09 실행파일에 대표아이콘 적용 가능(.cmd와 같은 폴더에 동일한 파일명의 .ico 파일이 있으면 자동 인식)

> 00.24.10.07 처음

Used standard C and Windows API only.
Resorce Compiler : Borland Resource Compiler Version 5.40
Complier : C++ 5.5.1 for Win32 Copyright (c) 1993, 2000 Borland
Linker : Turbo Incremental Link 5.00 Copyright (c) 1997, 2000 Borland
Contect : ccamagui@live.com or godhyun@gmail.com
Blog : https://godonghyun.blogspot.com/

