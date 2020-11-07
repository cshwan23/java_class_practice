# java_class_practice
복습
package com.aaa.erp;

소속 패키지 선언
 
public class Sungjuk {

학생의 성적을 관리하는 클래스 선언
주의) 클래스 이름은 의미있게 주어야 하고 관용적으로 대문자로 시작한다.
 
속성변수  선언
- 학생 정보로 뭐가 중요할까? (1. 학생이름?-중복가능성 2. 학생 번호 ! )
- 학생 번호를 저장할 속성변수 선언
- 학생의 번호는 객채화 시킬 때 집어 넣을 거다.
- 학생의 성적을 관리하는 클래스이다.
- 그러므로 학생의 정보를 관리하는 클래스는 따로 있을거다.
private int stu_no;

- 왜 점수에 데이터는 안 넣은걸까
- 어떤 학생의 데이터를 저장할 지 모른다.
- 학생의 정보는 객체화 된 후 집어넣거나 과정 중에 집어넣을거다.
- 우리의 최종 목적은 객체다.
 
private int kor;

- 국어 점수가 저장되는 속성변수 kor 선언
 
private int eng;

- 영어 점수가  저장되는 속성변수 eng 선언
 
private int mat;

- 수학 점수가 저장되는 속성변수 mat 선언
 
public static int cnt;

- 속성 변수 앞에 static을 붙이면 n개의 객체에 공유한다.
- 이렇게 하면 되냐 안 되냐?
- 이렇게 하면 기본적으로 0 이 들어간다.
- cnt 앞에 static을 빼면 독단적이게 되서 누적되지 않는다.
 
- 클래스를 구성하는 3대 멤버 중 생성자를 만들거다.
- 생성자  하나도 선언 안해되 될까?
- 코딩상 0개 이상만 있어도 된다. 알아서 하나는 만들어주니까.
- 생성자 선언
- 생성자는 객체 생성 시 단 한번만 호출된다.
- 생성자 호출 시 외부에서 학생번호, 국어점수, 영어점수, 수학점수가 들어올거다.
- 이걸 받는게 매개변수이다.
- (주의) 생성자는 객체 생성 이후 인위적으로 다시 호출할 수 없다.
- 매개변수는 이 안에서 사용되고 제거될 것이기 때문에
- 이름이 속성변수와 똑같아도 오류 나지 않는다.
- 클래스 안에서 매개변수를 생성하는 두 곳은 어디인가?
- 메서드 괄호(안) , 생성자 괄호(안)이다.
- 매개변수를 어디에 담아놔야 영원히 저장할 수 있을까? 
public Sungjuk(int stu_no, int kor, int eng, int mat) {

- 매개변수 stu_no로 들어오는 데이터를 속성변수 sut_no에 저장하기
this.stu_no = stu_no;

- 매개변수를 속성변수에다 집어넣으려고 하는 작업이다.
- 이퀄= 왼쪽은 속성변수이고 이퀄= 오른쪽은 매개변수이여야 하는데
- 이름을 같이하면 헷갈린다.
- 속성변수와 똑같이주되 속성변수 앞에 this. 을 붙여준다.
- this.가 붙은 변수가 진짜 자기 속성변수이다.
- 내 매개변수라고 강조하는 것이다.
- this.용법은 내거라고 강조하는 것.
- 속성변수의 초기화 작업 = 대부분 생성자 안에서 발생한다.
- 외부에서 들어온 데이터를 속성변수 안에 집어 넣는 것이다.
this.kor = kor;

this eng = eng;

this mat = mat;

cnt++;

}

 
메소드 선언
메소드를 통해 얻고자 하는 것은 학생의 정보, 학생의 국어영어수학점수, 평균, 총점, 학점
 
속성변수 stu_no의 데이터를 리턴하는 메소드 선언
주로 리턴값이 있는 메서드명은 주로 뭘 많이 사용하냐면 get으로 많이 시작한다.
public int getStu_no() {

     return stu_no;

}

속성 변수 kor의 데이터를 리턴하는 메소드 선언
public int getKor() {

     return kor;

}

속성변수 eng의 데이터를 리턴하는 메서드 선언
public int getEng() {

     return eng;

}

속성변수 mat의 데이터를 리턴하는 메서드 선언
public int getMat() {

     return mat;

}

총점을 리턴하는 메서드 선언
public int getTot() {

     return kor + eng + mat;

}

평균을 리턴하는 메서드 선언
public double getAvg() {

     return getTot/3.0;

}

public void xx() {
}
메서드 안에 실행구문이 없어도 된다. 앞에 void를 붙여주면 안에 아무것도 없어도 된다.
리턴형이 있으면 리턴 데이터가 있어야 한다.
 
public String getHakjum () {
 
     평균 지역 변수
     doublie avg = getAvg();
 
     학점 지역 변수
     String myHakjum = "F";
 
     if (Avg >= 90 && Avg <= 100 ) {
          myHakjum = "A";
     } else if (Avg >= 80) {
          myHakjum = "B";
     } else if (Avg >= 70) {
          myHakjum = "C"; }
     else if (Avg >= 60) {
          myHakjum = "D";
     }
          return myHakjum;
}
 
국어 점수가 잘못되었을 경우
수정하는 건 set 디비에서 수정하는 건 update 를 주로 사용한다
매개변수가 등장. 벌어지는 일은 무엇일까
국어점수가 들어온다.
 
국어 점수를 수정하는 메서드 선언
public void setKor (int kor ) {
this.kor = kor;
}
 
영어 점수를 수정하는 메서드 선언
public void setEng (int eng) {
this.eng = eng;
}
수학 점수를 수정하는 메서드 선언
public void setMat ( int mat ) {
this.mat = mat;
}
 
이렇게 하고 실행을 시켜보자
실행이 되지 않을거다. 객체회를 하지 않아서.
이 클래스를 객체화 시켜줄 클래스를 하나 더 만들어야 한다.
->SungjukExe 클래스를 만든다.
 
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
package com.aaa.erp;
 
- Sungjuk클래스를 객체화 하고 메소드를 호출하기 위한 SungjukExe 클래스 선언
public class SungjukExe {
 
     public static void main ( Stringp[] args) {
 
              이 한줄 뜻이 갖는 코딩의 의미는?
              Sungjuk sjk = new Sungjuk(1, 99, 88, 77);
1> 변수 sjk 선언하기 ( 변수 앞에 들어갈 자료형은 클래스 이름 Sungjuk임)
     new 의 역활 나중에 배움.
2> new 에 의해 수입된 클래스 중에 Sungjuk(~,~,~,~)형식의 Sungjuk은 생성자 명인다.
생성자를 가진 클래스를 찾아 메모리 공간으로 올려버린다.(= 객체화)
데이터타입또한 맞춰야 한다
3> 메모리체에 올려진 객체에서 생성자를 호출한다.
4>Sungjuk객체의 메모리 위치 주소값을 리턴해서 sjk에 저장하기
 
Sungjuk 객체의 getStu_no() 메서드를 호출하여 얻은 학생번호 출력하기
객체의 메소드 호출 형식은     객체 메모리위치주소값.메소드명(~)이다.
System.out.println("[학생번호] : " + sjk.getStu_no());
 
Sungjuk 객체의 getKor() 메서드를 호출하여 얻은 국어 점수를 출력하기
객체의 메소드 호출 형식은     객체 메모리 위치주소값.메소드명(~)이다.
System.out.println("[국어점수] : " + sjk.getKor());
 
Sungjuk 객체의 getEng() 메서드를 호출하여 얻은 영어 점수를 출력하기
객체의 메소드 호출 형식은     객체 메모리 위치주소값.메소드명(~)이다.
System.out.println("[영어점수] : " + sjk.getEng());
 
Sungjuk 객체의 getMat() 메서드를 호출하여 얻은 수학 점수를 출력하기
객체의 메소드 호출 형식은     객체 메모리 위치 주소값. 메소드명(~)이다.
System.out.println("[수학점수] : " + sjk.getMat());
 
Sungjuk 객체의 getHackjum() 메서드를 호출하여 얻은 평균을 출력하기
객체의 메소드 호출 형식은     객체 메모리 위치주소값.메소드명(~)이다.
System.out.println("([학점] : " + sjk.getHakjum());
 
System.out.println("[국어점수 수정 발생] ");
 
sjk.setKor(70);
 
System.out.println("[학생번호] : " + sjk.getSut_no());
System.out.println("[국어점수] : " + sjk.getKor());
System.out.println("[영어점수] : " + sjk.getEng());
System.out.println("[수학점수] : " + sjk.getMat());
System.out.println("[총점] : " + sjk.getTot());
System.out.println("[평균] : " + sjk.getAvg());
System.out.println("[학점] : " + sjk.getHakjum());
 
Sungjuk sjk2 = new Sungjuk(2, 70, 60, 80);
1.sjk2선언하기 변수안에 들어갈 자료형은 Sungjuk클래스
2.new라는 키워드를 가지고 메모리에 올려서 객체화를 시킨다.
3. 메모리가 올라간 객체에서 생성자를 찾아 메모리에 올릴(2, 70,60,80)을 담을 생성자가 있나없나 찾는다.
4. Sungjuk 객체의 메모리 위치 주소값을 리턴하여 sjk2에 저장하기.
 
System.out.println("[학생번호] : " + sjk2.getSut_no());
System.out.println("[국어점수] : " + sjk2.getKor());
System.out.println("[영어점수] : " + sjk2.getEng());
System.out.println("[수학점수] : " + sjk2.getMat());
System.out.println("[총점] : " + sjk2.getTot());
System.out.println("[평균] : " + sjk2.getAvg());
System.out.println("[학점] : " + sjk2.getHakjum());
 
<문제 1>
Q . public class Sungjuk { ~ }을 class Sungjuk {~ }으로 고치면?
 
A. 에러 발생
-> 어디에서? com.bbb.erp.SungjukExe 클래스에서 import com.aaa.erp.Sungjuk에서 에러 발생
이유: 수입 대상 클래스 마빡에 public이 없으면 타 패키지에서 수입이 불가능하다.
 
<문제 2>
Q. 위 Sungjuk클래스를 개체화 하기 전에
    private int kor; 로 선언된 속성변수 kor에는 뭐가 들어있나?
 
A .  0이 들어있다.
이유 : 속성변수는 데이터를 저장하지 않으면 디폴트 값이 저장된다. (= 자동 초기화)
디폴트 값이 자동으로 들어가 있는 것을 자동 초기화라고 한다.
메소드 안에 선언되는 지역 변수와 달리
속성변수는 클래스를 구성하는 중요한 요소이므로 자동 초기화가 된다.
 
<문제 3> 
Q. private int kor; 을 private double kor; 로 수정하면?
 
A . 에러 발생
에러 위치 : public int getKor() { return kor; } 에서 발생.
return kor; 코드에 실수가 리턴되는데
리턴되는 자료형은 int라고 했으므로 에러 발생.
public int getTot() { return kor+mat + eng; }에서도 에러 발생.
return kor+ mat + eng; 코드에 의해 실수가 리턴되는데
리턴되는 자료형은 int 라고 했으므로 에러 발생.
 
<문제 4> 
Q. public int getKor( ) { return kor; } 를
     public double getKor( ) { return kor; }로 수정하면?

A. 에러 없음.
double이 int 보다 크니까 변환이 된다.
리턴 자료형이 double이고 실제 리턴되는 데이터가 정수면
정수가 실수로 변하므로  
 
<문제 5>
public int getKor () { return kor; }를
int getKor() { return kor; }로 수정하면?

정답 : 에러 발생.
에러위치 -> com.bbb.erp.Sungjuk 클래스의 getKor 메소드 호출 지점
에러이유 -> 매소드 맨 앞의 접근 지정자가 default이면 타 패키지의 타클래스에서의 호출을 금지한다.
 
<문제 6> 
public int kor; 를 private final int kor; 로 수정하면?
 
정답 : 에러 없음
이유 : final이 붙은 속성변수는 예외로 자동 초기화가 되지 않기 때문에
개발자가 수동 초기화를 해야한다.
수동 초기화는 속셩 변수 선언할 때 또는 생성자 안에서 해야한다.
현재 속성변수 선언할 때는 수동 초기화를 하지 않았지만 새ㅔㅇ성자 안에서
수동 초기화 했으므로 에러가 발생하지는 않는다.
만약 생성자 안의 this.kor = kor; 을 생략하면 에러가 발생한다.
 
<문제 7> 
public Sungjuk( int stu_no, int kor, int eng, int mat ) { ~ } 를
  Sungjuk( int kor, int eng, int mat ) { ~ } 로 수정하면?
 
정답 : 에러발생
에러 위치 : com.bbb.erp.SungjukExe 클래스의 Sungjuk sjk = new Sungjuk(1,99,88,77) 지점
에러 이유 : 생성자의 접근 지정자가 default면 동일한 패키지 안의 타 클래스에서만
객체화할 때 보이고 타 패키지의 타 클래스에서 안보이게 한다. 
 
<문제 8>
 public Sungjuk( int stu_no, int kor, int eng, int mat ) { ~ } 를
 private Sungjuk( int stu_no, int kor, int eng, int mat ) { ~ } 로 수정하면?
 
정답: 에러발생
에러위치 :
com.aaa.erp.SungjukExe 클래스의 Sungjuk sjk = new Sungjuk(1, 90, 80, 70)지점
com.bbb.erp.SungjukExe 클래스의 Sungjuk sjk = new Sungjuk(1, 90, 80, 70)지점
에러 이유 : 
생성자에 private이 붙으면 그 어떤 타 클래스의 객체 생성과정중에 생성자를 찾을 수 없게 한다,.
결국 타클래스에서 객체 생성을 막는 셈이다.
생성자에 private가 붙는 클래스는 대부분 속성변수나 메소드에 static을 붙여
객체생성 없이 호출하도록 설정되어있다.
staticd은 즉 객체 생성없이 그냥 쓰라는 의미가 있다.
생성자에 private가 붙으면 생성자가 존재하나 아무에게도 보이지 않게 된다.
Math클래스는 생성자가 다 Private다. 수학적 연산에 관련된 클래스는 보안성이 필요 없다.
생성자 다 막아놓고 속성변수 static으로 다 풀어 놨다. 오히려 더 빨리 갖다 쓰라고.
 
<문9>  public Sungjuk( int stu_no, int kor, int eng, int mat ) { ~ } 를
    삭제하면?
 
정답 error
에러 위치 
com.aaa.erp.SungjukExe 클래스의 Sungjuk sjk = new Sungjuk(1, 90, 80, 70)지점
com.bbb.erp.SungjukExe 클래스의 Sungjuk sjk = new Sungjuk(1, 90, 80, 70)지점
에러 이유
public Sungjuk( int stu_no, int kor, int eng, int mat ) 가 있는 생성자를 가진 클래스를 찾아
객체화 해야 하는데 이 생성자를 삭제하면 찾을 수 없어서 객체화에 실패한다.
만약 : 생성자가 코딩상 0개면 자바는 default 생성자를 삽입해준다.
(default 생성자의 형태 : public Sungjuk( ) { } )
 
<문10>  public Sungjuk { ~ } 를 public final Sungjuk{~}로 수정한다면?
 
정답: 에러 없음
클래스 앞의 final은 자식클래스를 가지지 않겠다는 의미인데
현재 Sungjuk 클래스의 자식클래스가 없기 때문에 에러가 발생하지 않는다,
만약 임의의 어떤 클래스가 부모가 되어달라고 요청하면 그 쪽에서 에러가 난다.
 
참고) 부모자식관계는 자식이 맺는거다.
추후 상속(inheritance)에서 자세히 배운다. 참으세요..
상속이 되면 자식이 이득이다.
자식 영역에서 부모의 객체를 멤버로서 가질 수 있다.
1. 코드의 중복성을 막는다.
2. 관리하기가 쉽다. 
 
<문11> 
public Sungjuk{ ~ } 를  public abstract Sungjuk{ ~ } 로 수정하면? 
 
정답 : 에러 발생
에러 위치 ->
com.aaa.erp.SungjukExe 클래스의 Sungjuk sjk = new Sungjuk(1, 90, 80, 70)지점
com.bbb.erp.SungjukExe 클래스의 Sungjuk sjk = new Sungjuk(1, 90, 80, 70)지점
에러 이유 :
클래스 마빡에 abstract가 붙는 클래스는 객체 생성이 불가능하다.
 
클래스 마빡에 abstract가 붙는 경우
     <1> : 소유한 메소드 중에 {~ } 바디가 없는 메소드가 1개 이상 존재할 때
     <2>: 조상 클래스 중에 { ~ } 바디가 없는 메소드가 1개 이상 존재하는 클래스가 있고
              그 후손이 {~ } 바디가 없는 메소드를 재 정의 하지 않을 경우
     <3> : 1,2경우가 아닌 상태에서 그냥 객체 생성을 막은 경우
               객체화를 막으려고 . 객체 생성을 막으려고.
 
 
 
<문12>  학점을 리턴하는 메소드 선언 
         public String getHakjum() {
               ???
          }
정 답.  
  public String getHakjum() {
// 국어 영어 수학 90점이상 a 80점 이상 b 70정 이상 c 60점 이상 d 그 이하 f
 
// 평균 지역 변수
double Avg = getAvg();
 
// 학점 지역 변수
String myHakjum = "F";
 
if (Avg >= 90 && Avg <= 100 ) {
myHakjum = "A";
} else if (Avg >= 80) {
myHakjum = "B";
} else if (Avg >= 70) {
myHakjum = "C";
} else if (Avg >= 60) {
myHakjum = "D";
}
 
return myHakjum;
 
}
  //지역 변수는 선언하고 바로 데이터를 넣어주는 것이 좋은데
     안넣을 경우 else 가 꼭 들어가줘야한다. 빈틈이 없어야 한다.
 
<문제 13>
국어점수를 수정하는 메소드를 선언해달라.
 
public void setKor(int kor) {
 
this.kor = kor;
 
}
