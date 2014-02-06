attendance XE 출석부
====================

권고문
------
Ver2.0 버전부터 출석부모듈의 설정하는 것의 변수가 변경되었습니다.
이로 인해 변경된 변수들은 모두 설정값이 초기화 됩니다. 
부득이하게 초기화된 설정값들을 기억하지 못하여 누락되는 설정값이 없도록 출석부 모듈을 업데이트하기전에 설정값들을 스크린샷으로 남겨두시기 바랍니다.
변경되는 내역은 다음과 같습니다.

* 출석포인트
* 1등 가산점
* 2등 가산점
* 3등 가산점
* 한 해 개근 가산점
* 한 달 개근 가산점
* 한 주 개근 가산점
* 지정일 출석 여부
* 지정일
* 지정일 가산점
* 연속출석 여부
* 연속출석일
* 연속출석 포인트
* 시간제한 여부
* 시작시각
* 종료시각
* 연간 정근 가산점 사용
* 연간 정근 가산점 값 입력
* 연간 정근 포인트
* 월간 정근 가산점 사용
* 월간 정근 가산점 값 입력
* 월간 정근 포인트
* 주간 정근 가산점 사용
* 주간 정근 가산점 값 입력
* 주간 정근 포인트
* 자동출석 설정 여부
* 랜덤 포인트 사용
* 랜덤 포인트 포인트 설정
* 꽝확률 설정
* 생일 포인트 사용여부
* 생일 포인트 설정
* 회원정보 생일 수정 여부

이상 /index.php?module=admin&act=dispAttendanceAdminList 주소를 가진 페이지에서 모든설정값이 초기화 됩니다.
해당 값들은 미리 먼저 파악해뒀다가 업뎃 이후 재설정을 해주시기 바랍니다.
(개선을 위한 선택이기 때문에 값을 잊어 설정에 착오를 질 경우 출석부 모듈 개발자는 책임지지 않습니다.)


개요
----
이 소프트웨어는 'XE 출석부' 입니다.

이 소프트웨어는 GPL v2을 채택한 오픈 소스 소프트웨어로써 자유롭게 사용할 수 있는 자유 소프트웨어입니다.
이 라이선스 조건을 준수하는 조건하에 누구나 자유롭게 사용할 수 있습니다.

주요 기능
---------
* 출석채크를 할 때 인삿말을 남길 수 있음.
* 출석채크포인트를 조절 할 수 있음.
* 개근포인트및 정근포인트를 설정 할 수 있음.

Author
------
**BJ Rambo**

* website : http://sosifam.com
* email : sosifam@070805.co.kr
* 문의 : http://sosifam.com/question
* github : https://github.com/qw5414/attendance

Thanks to...
------------
* 소녀시대..(나에게 힘을 주니깐..)
* 몽실아빠 (http://pomelove.com)
* [@BNU](https://github.com/BNU)

참고사항
--------
출석부모듈 1.6.5 버전부터 주간개근 함수 조건문이 바뀌었습니다.
다음과같이 수정을 해주셔야 합니다.
각 스킨 파일에서 다음 문구를 찾으세요.
각스킨의 index.html 파일에 있습니다.

$weekly->weekly == 7 && $selected_date == $week->sunday

이문구를 
$weekly->weekly == 7 && $selected_date == $week->sunday1

으로 바꿔주시기 바랍니다 (제일끝부분에 1을 추가하여 주시기 바랍니다.
단, 기본 스킨은 해당 모듈설치시 같이 변경이 되기 때문에 수정사항을 거치지 않아도 됩니다.

아울러 1.7.5 버전부터 어드민 페이지에서 수집현황 동의 팻말들을 최상단에 배치하였습니다.
많은 유저분들의 참여가 필요해서 상단에 배치하였습니다. 동의하지 않을경우 제공하지 않음을 클릭하시면 뜨지않습니다.

업뎃 사항 
---------
**Ver. 2.0**
* 어드민 페이지 내의 config_data 함수를 모두 제거.
* 모듈 설정값을 config 로잡고 모든 설정값 추가.
* 년간 개근 포인트의 함수가 바르지 않아 포인트 지급이 되지 않던 문제 개선.


**Ver. 1.8.5**
* php5.4 버전에서 사용할 수 없던 문제 개선 ( [@smaker](https://github.com/smaker) ) [#26](https://github.com/qw5414/attendance/pull/26)
* 랜덤포인트에서 사용을 하지 않는 코드 삭제
* 사용자 환경 수집 캐시파일 위치 변경
* php5.4 호환성으로 인한 관리자임의 출석기록 오류 개선.

**Ver. 1.8.3**
* 타 모듈에서 트리거 디스플레이 사용되는 모듈들과 충돌이 일어나는 문제 개선 (이것으로 인해서 홈페이지내에서 설정이 먹히지 않았습니다. 정보 제공 : 몽실아빠)
* 회원의 회원정보중에 생일을 수정할 수 있도록 옵션 주도록 개선.
* $lang값의 부재를 다 채워 넣었..(하앍..????????????????????????????)

**Ver. 1.8.2**
* 생일 포인트 설정 관련 추가
* 생일 포인트는 module config 를 사용하도록 개선
* 생일포인트를 사용한다고 설정하였을때 출석부의 의해 회원정보중 생일을 수정할 수 없도록 개선(삭제도 못하도록 변경)

**Ver. 1.8.1**
* 어드민 페이지에서 사용자 환경수집을 동의 혹은 거부 하엿을경우 잘못된 링크로 연결되던 현상개선.
* 출석부 기본 스킨의 어드민으로 연결되는 링크 수정

**Ver. 1.8.0**
* 오타수정
* 1.7.4 버전의 호환성 개선  ( [@BNU](https://github.com/BNU) )

**Ver. 1.7.9**
* 꽝확률, 랜덤 포인트 설명이 $lang 변수로 만들지 못하고 잘못된 영어로만 들어간 것 개선

**Ver. 1.7.8**
* 랜덤포인트에 꽝걸릴수 있도록 개선
* 꽝일경우 기본 출석부스킨에 랜덤포인트 항목에 "꽝"이라는 문구가 뜨도록 개선.
* xe1.5 호환성 개선. #13 #14 

**Ver. 1.7.7**
* 랜덤 포인트 이벤트 마련
* 랜덤 포인트설정에서 최솟값의 숫자가 최댓값보다 크거나 같을 경우 작동하지 않도록 구성.
* 랜덤 포인트설정으로 인한 $lang 구문 추가
* 사용자 정보수집을 동의하였을경우 사용자정보 수집관련 iframe 구문은 어드민 아래쪽에서 나타나도록 개선.
* 사용자 스킨에서 {$data->today_random} 변수를 사용하면 랜덤 포인트로 받은 포인트만 개별적으로 뜨도록 개선

**Ver. 1.7.5**
* XE 1.5 버전에서 어드민페이지가 보이지 않던 현상 개선
* 사용자 수집현황을 어드민페이지에서 최상단에 보이도록 배치

**Ver. 1.7.4**
* 쉬운설치를 위한 재 압축 및 업로드

**Ver. 1.7.3** 
* xe1.4버전에서 어드민 페이지가 정상적으로 안뜰거라 생각하고 admin페이지 부분에 1.4를위한 코드 입력.
* 기존 제작자의 이름 수정 및 전체 적인 코드 최적화
* 기본 스킨 최적화

**Ver. 1.7.2** 
* 연간 개근하였을경우 매달 말일날 연간 개근항목이 뜨던 현상 개선.

**Ver. 1.7.1** 
* 출책 금지시간을 설정하여도 출책이 가능하던 문제점 개선

**Ver. 1.7**
* 사용자정보수집기능추가.(동의 동의안함 버튼으로 작동).
* 관리자 환경 대폭개선.
* 모바일 스킨을 선택하지 못하던 문제개선.
* 모바일 스킨설정페이지 추가
