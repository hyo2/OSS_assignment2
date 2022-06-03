# OSS_assignment2
리눅스 프로세스 명령어(top, ps, jobs, kill), vim에디터(매크로 사용법(q,@))
<br></br>
***

## 📌 리눅스 명령어
### ✅ top
: 시스템에서 현재 실행중인 프로세스/메모리에 대한 정보를 ***실시간***으로 출력

<p align="center">
  <img src="https://user-images.githubusercontent.com/70335241/171877735-da7fae22-f705-4942-87ea-11e431e92e3f.png"/>
 </p>
 
- top [옵션]
  |옵션|의미|
  |:------:|:----|
  |`-d [갱신시간]`|화면 갱신시간을 입력받은 초단위로 설정(default는 3초)|
  |`-u [사용자]`|입력된 사용자의 프로세스만 표시|
  |`-n [숫자]`|입력된 숫자만큼 화면 출력 갱신|
  |`-b`|batch 모드로 작동|
  |`-i`|idle 또는 좀비상태의 프로세스는 표시하지 않음|

### ✅ ps
: 현재 시스템에서 실행중인 프로세스에 대해 ***정적인*** 정보 출력
- ps [옵션]
  |옵션|의미|
  |:------:|:----:|
  |`-A` 또는 `-e`|모든 프로세스 출력|
  |`a`|터미널과 연관된 프로세스만 출력| 
  |`x`| 터미널과 연관되지 않은 프로세스만 출력|
  |`-u`|각 프로세스의 사용자 정보 표시|
  |`-r`|현재 실행중인 프로세스만 출력|
  
### ✅ jobs 
: 백그라운드로 실행중인 프로세스나 작업이 중지된 프로세스의 목록을 출력
- jobs [옵션]
  |옵션|의미|
  |:------:|:----:|
  |`-l`|프로세스 ID(PID)를 추가해서 출력|
  |`-n`|마지막 알림 이후 상태가 변경된 프로세스만 출력| 
  |`-p`|프로세스 ID만 출력|
  
### ✅ kill
: 프로세스에 특정 시그널을 보냄. 보통 프로세스에 종료신호를 보내는 데에 쓰인다.

(signal number(default는 15)나 옵션을 정하지 않으면 기본적으로 작업종료로 사용됨)
- kill [옵션]
  |옵션|의미|
  |:------:|:----:|
  |`-l` 또는 `-L`|지원하는 signal들의 이름 출력|
  |`-s sig`|이때 SIG는 signal 이름 ex) `-s KILL [PID]` : 강제종료 |
  |`-n sig`|이때 SIG는 signal number ex) `-n -9 [PID]` : 강제종료 |
 - signal name 목록(`kill -l` 실행 결과)
 <p align="center">
  <img src="https://user-images.githubusercontent.com/70335241/171931967-db65c82c-2e16-477a-9447-c3fe6f9aa995.png"/>
 </p>
 
<br></br>
***
## 📌 vim 에디터
### ✅ 매크로 사용법 - 일반모드에서 진행
- 매크로 기록 : q → <매크로 단축키 설정> → 작업 → q(종료)
- 매크로 사용
  |작업 내용|명령어|
  |:---:|:---:|
  |매크로 실행|@<설정했던 매크로 단축키>|
  |매크로 반복실행|반복횟수@<설정했던 매크로 단축키>|
  |마지막에 수행한 매크로 실행|@@|

- 매크로 저장 

  : 작성한 매크로를 저장해서 재사용 하고 싶을 시 vim 설정 파일에 기록해서 사용할 수 있음
    - 순서
  1) ~/vimrc 열기
  2) i (입력모드로 전환) 
  3) let @<만든 매크로의 단축키>='Ctrl+R Ctrl+R <매크로 단축키>' 
  4) :wq! (저장 후 종료)
