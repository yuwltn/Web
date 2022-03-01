## DTO\VO
DTO는 Data Transfer Object의 약자로<br>
VO(Value Object)랑 혼용해서 쓴다.
<br><br>

## DTO(Data Transfer Object)란?
계층간 데이터 교환을 위한 객체이다.<br>
DB가 데이터의 Service나 Controller 등으로 보낼 때 사용하는 객체를 말한다. <br>
로직을 갖고 있지 않은 순수한 데이터 객체이며 `getter/setter` 메서드만을 갖는다. 
<br><br>
즉, DB의 데이터가 `Presentation Logic Tier` 로 넘어올 때는 DTO로 변환되어 오고가는 것이다.<br>
또한 Controller Layer(ViewLayer)에서 response DTO 형태로 Client에 전달한다.
<br><br>

## VO(Value Object)란?
값 객체이다.
<br><br>

## 왜 DTO랑 VO를 혼용해서 사용할까?
DTO, VO는 결론적으로는 직접 데이터를 넣어주기 보다는 넣어진 데이터를 getter를 통해 사용하므로 주 목적은 같다.
<br>
하지만 DTO는 불변 클래스 성격과는 거리가 멀고 인스턴스 개념이다. VO는 리터럴 값 개념이다.
