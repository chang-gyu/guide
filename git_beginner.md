---
title: GIT 을 소개합니다.
separator: ---s
verticalSeparator: ---v
theme: black
revealOptions:
	slideNumber: true
---

# GIT FOR BEGINNER

### 구름네트웍스
#### 김창규
note: $ reveal-md slide/git_beginner.md -w -css asset/css/slide-1.css

---s

## GIT?
Version Control System

---v

버전 관리 시스템<br>
(Version Control System, VCS)<br><br>
<small> 프로젝트 파일의 변경 사항을 추적할 수 있도록 돕는 도구</small>

---v

## 탄생비화<br>
<small>리누스 토발즈가 Linux 커널의 소스관리를 위해 git을 직접 개발
![slide-img1.png](https://allaboutetp.files.wordpress.com/2012/03/ec8aa4ed81aceba6b0ec83b7-2012-03-19-1-16-19-am.png)
<br> 릴리즈 2~3년 이후 github이 시작된 2007년부터 폭발적인 반응을 얻음</small>

---v

### 버전관리, 왜 필요할까?

---v

- 각자가 프로젝트의 전체 이력이 있는 자신만의 저장소
- commit할 때는 원격 저장소에 연결할 필요가 없이 변경 사항을 지역 저장소에 기록
- commit의 log를 이용한 변경 파일 추적이 용이
- 이전 시점의 어떤 버전으로도 복구가능

---v
![slide-img2.png](https://backlogtool.com/git-guide/kr/img/post/intro/capture_intro1_1_2.png)
- 동시에 같은 작업을 할때 누군가의 작업은 겹쳐쓰여질 것이고 지워는일 방지

---s

## 실습하면서 익히자!

---v

## Install(for linux)
<small>git을 설치하자.</small>
<br>![slide-img3.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img3.png?raw=true)
<br>↓
<br>![slide-img4.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img4.png?raw=true)
<br><small>Install success!</small>
---v

## 사용자 설정
![slide-img5.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img5.png?raw=true)
<br>사용자 정보는 변경이력에 표시
```
$ git config --global user.name "<사용자명>"
$ git config --global user.email "<메일 주소>"
```

---v

## 새 로컬 저장소 만들기(init)
![slide-img6.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img6.png?raw=true)
```
mkdir <디렉토리명>
디렉토리 이동
git init
```
<small>새로운 로컬 저장소가 만들어졌다! </small>

---v

## 로컬 저장소 만들기(clone)

원격 저장소를 로컬 저장소로 생성
```
git clone https://github.com/packetngin/rtos.git
```

---v

## repository(저장소)
![slide-img8.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img8.png?raw=true)
<br>사용자가 변경한 모든 내용을 추적하는 공간
<br>코드의 현재 상태, 언제, 누가 코드를 변경했는지, 변경 사항을 설명하는 텍스트 로그 메시지까지 저장
---v

## 원격 저장소와 로컬 저장소

![slide-img9.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img9.png?raw=true)
<br>원격 저장소(Remote Repository)
<br><small>파일이 원격 저장소 전용 서버에서 관리되며 여러 사람이 함께 공유하기 위한 저장소</small>
<br>로컬 저장소(Local Repository)
<br><small>내 PC에 파일이 저장되는 개인 전용 저장소</small>

---v

## 파일 커밋(commit)하기
![slide-img7.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img7.png?raw=true)
```
echo "git is ver easy!" > sample.txt  
git status
git add sample.txt
```

---v

commit시에 log를 남긴다<br>
![slide-img10.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img10.png?raw=true)
```
git commit -m "[commit message]"
git status
git log
```
<small>git log를 통해 commit 확인!
<br>참고: 'git commit'만 입력하여도 log를 남길 수 있음</small>
---v

## push
로컬 저장소의 변경된 이력을 원격 저장소로 업로드
![slide-img11.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img11.png?raw=true)
<small>원격 저장소를 만드는 방법은 생략함
<br>github.com을 이용하면 간단하게 생성 가능</small>

---v
## push
<small>로컬 저장소의 변경사항을 업로드할 원격 저장소 등록하기</small>
![slide-img12.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img12.png?raw=true)
```
git remote -v //현재 등록된 원격 저장소 목록 확인
git remote add origin [remote repository address]
```

---v
## push
등록된 원격저장소로 푸싱(pushing)
<br>![slide-img13.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img13.png?raw=true)
```
git push [remote repository address] [local repository name]
```

---v

## 변경사항 확인하기(diff)
<small>'git diff' 명령어를 통해 변경사항을 추적할 수 있다!
![slide-img14.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img14.png?raw=true)
<br>sample.txt에서 단어 앞글짜가 모두 대문자로 변경됬음을 확인
<br>commit을 통해 local저장소가 업데이트 되면, 'git diff master' 명령어를 통해서 master 로컬 저장소와 현재 변경사항이 없으므로 아무 출력이 되지않음을 확인할 수 있다.</small>

---v
<small>이제 diff 명령을 통해 원격 저장소와 비교했고, 
<br>푸싱하여 다시 변경사항을 확인하면 다음과 같다.</small>
![slide-img15.png](https://github.com/chang-gyu/guide/blob/master/slide-img/slide-img15.png?raw=true)


