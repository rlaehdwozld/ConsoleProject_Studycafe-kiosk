# 22년 9월 20일 오전

## 오전 변경점

[com.victoree2.system]  
[SystemEx.java  // 51]

```java
case 4://언어선택
				change=!change;
				room.language = (change) ?  "kor" : "en";
				break;
```


    언어선택 토글로 바꿈


[com.victoree2.system]  
[SystemEx.java  // 27]

```java
user.load(); //로그인 체크를 위해 로그인 정보가 저장된 파일을 불러올것이다
			//관리자가 회원의 정보를 모두 보기위해 map값을 전부 가져옴
			Set<String> userMap = user.getAccount().keySet();
```

    hashmap 으로 전달하는 방식으로 바꿈	Hash


[com.victoree2.system]  
[AccountSystem.java  // 94]

```java
public AccountData login() {
		System.out.println(message(room.language, "0012"));
		System.out.println(message(room.language, "0008")+" " + message(room.language, "0009") + " : ");
		String id = scan.nextLine();
		System.out.println(message(room.language, "0010") + " " + message(room.language, "0009") + " : ");
		String password = scan.nextLine();
		AccountData returnValue=null;
```

    int 에서 AccountData로 바꾸어 계정정보를 return 하도록 바꿈
    유저DB 자체를 리턴받아서 값을 활용한 후 유저 정보를 활용할 수 있게

<br>

## 수정된 내용

    AccountData
    필드
    phonenumber -> phoneNumber
    startday,endday  : 삭제

    메소드

    AccountData 생성자 메소드 기존의 사용했던 파라미터값을 필드 변경에 따라 수정.
    AccountSystem 클래스에서 생성자 메소드 위와 동일한 이유로 수정.



    예약내역저장할 클래스 생성.
    ReadingData
    AccountData에서 삭제한 startday,endday(결제일, 결제만료일) 삽입.



    AccountSystem
    admin_check -> adminCheck 변경.


    ActionInterface
    pwReset -> pwdReset 변경.
    ActionInterface를 상속받는 하위 클래스(AdminSystem, UserSystemm) 동일하게 메소드 명칭 변경.

## 한 일

- print 정리(유저, 관리자)
- 기준 정리 (class명, 변수명 기준 잡기)