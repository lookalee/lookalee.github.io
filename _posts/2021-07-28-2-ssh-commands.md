---
layout: single
title: "유용한 리눅스 커맨드 및 ssh 커멘드 정리 (2)"
tags: [computer-architecture]
categories: computer-architecture




---

유용한 ssh 커맨드 (리눅스):

- 전체 폴더를 개인 컴퓨터에서 가상 컴퓨터로 옮기기: scp-r [Folder Name] leex7576@machineName:folderDestination
  - ex) scp-r hw-code/ leex7576@apollo.cselabs.umn.edu:CSCI2021/

유용한 터미널 커맨드 (리눅스):

- cd : 디렉토리 변경
- cd../../users/download : 디렉토리 내비게이션
- cd .. : 디렉토리 한단계 위로
- cd~ : 홈 디렉토리로 변경
- ls : 모든 폴더 리스트
- ls-l : 모든 폴더 리스트 (디테일 함께)
- ls-a : 모든 폴더 리스트 (숨겨진 폴더도 보여줌)
- mkd folderName : 새로운 디렉토리 생성
- man ls : list 매뉴얼

파일 관련 커맨드 (리눅스):

- 파일 컴파일 및 실행
  - (아웃풋 파일 이름 a.out으로 생성) gcc fileName -> ./a.out
  -  (아웃풋 파일 이름 정해서 생성) gcc -o project1 fileName -> ./project1 
- 코드 수정
  - code fileName
- 아웃풋 터미널에서 확인하기 : cat

<u>참고</u>: 

<u>참조</u>



