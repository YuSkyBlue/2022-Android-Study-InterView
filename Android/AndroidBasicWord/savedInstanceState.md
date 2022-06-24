> 작성일 : 2022/06/24<br>
> 작성자 : whatthe-downtown
> 오류 신고 : dbcjdrb1997@gmail.com or Pull Requset
# savedInstanceState

- 모든 Android 활동의 onCreate 메서드에 전달되는 번들 개체에 대한 참조입니다 
- 특수한 상황에서이(가로 <=> 세로 전환)또 다른 상황은 활동이 배경화되는 경우입니다. 활동이 백그라운드 상태(일시 중지 또는 중지 후)인 경우, 언제든지 아무런 통지 없이 활동이 파기될 수 있습니다. OS가 애플리케이션을 중지하지 않고 작업을 중지하는 경우 OS는 먼저 아웃스테이트 번들을 저장하여 나중에 이전 상태로 돌아갈 수 있습니다. 번들에 저장된 데이터를 사용하여 이전 상태로 복원할 수 있는 기능이 있습니다. 
주로 super.onCreate(savedInstanceState)에 자주 사용되는데

<img width="650" alt="스크린샷 2022-06-24 오후 3 21 07" src="https://user-images.githubusercontent.com/70245821/175475153-eb7aada9-4536-4fb6-80fd-5d7649e046c0.png">
<img width="545" alt="스크린샷 2022-06-24 오후 3 21 14" src="https://user-images.githubusercontent.com/70245821/175475166-11786eac-42bf-4133-b795-1399088e728c.png">

## When is the savedInstanceState useful?
- 활동이 백그라운드 상태(일시 중지 또는 중지 후)인 경우, 언제든지 아무런 통지 없이 활동이 파기될 수 있습니다. 이때 OS가 애플리케이션을 중지하지 않고 작업을 중지하는 경우 OS는 먼저 아웃스테이트 번들을 저장하여 나중에 이전 상태로 돌아갈 수 있습니다. 즉, 쉽게 말하면 앱을 onStop or onPause() 상태에서일 경우 예고 없이 앱이 죽을 수 있는데 그 상황을 Bundle에 저장하여 하고 있던 상황을 초기화가 아닌 Rollback 할 수 있다.

# Bundle 
- Map의 형태로 구현된 데이터의 묶음(Bundle) 입니다. Map형태 Key 값 String 이며 Value Int,String ~ Serializable, Parcelable 같은 복잡한 타입도 들어올 수 있다.
- 데이터 저장 객체로 상태 저장 및 복구에 사용됩니다.
- Android는 주로 객체를 전달할 때 보통 Parcelable을 구현한 객체를 전달 합니다. 


참고자료 : <a href="https://kotlinworld.com/45"> Bunlde 이란 무엇인가 </a> </br>
참고자료 : <a href="https://tinyurl.com/2doz3xem"> Android- SavedInstanceState Bundle</a>
