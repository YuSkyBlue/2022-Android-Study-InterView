# LifeCylce
> 작성일자 2022/06/23 19:56</br>
> 작성자 whathe-downtown
> 오류/수정 문의 dbcjdrb1997@gmail.com
## 🍎Activitiy
- 화면에 보여지는 부분의 기능을 담당함
<p>Activitiy는 한 앱이 다른 앱을 호출할 때 호출 앱은 다른 앱을 전체적으로 호출 하는것이 아니라 다른 앱의 활동을 호출합니다.</p>
1. `onCreate` : `Activity`가 **최초** 생성되고, 필요한 작업의 초기화를 수행하기 위해 호출됨
## 🍎LifeCycle
![스크린샷 2022-06-24 오후 2 25 18](https://user-images.githubusercontent.com/70245821/175468174-ef797a1f-4ae1-40a6-aea6-0a74fba7ab4a.png)

사용자가 앱을 탐색하고 , 나가고 , 다시 돌아오는 과정을 진행하면 수명 주기 안에서 다른 상태에 의해 전환이 됩니다. 
- 사용자 (Me) 가 앱을 사용하다가 도중에 전화 OR 다른 앱 전환 할 때 비정상 종료되는 문제
- 앱을 활발하게 사용하지 않을때 귀중한 시스템 리소스 소비되는 문제
- 가로 방향 세로 방향 전환할 경우 , 비정상 종료 OR 데이터 유실 OR 진행 상태 저장되지 않는 문제 

### 🍏순서 
onCreate() -> onStart() -> onResume() -> onPause() -> onStop() -> onRestrart() or onDesotry()<br>

### 🍏onCreate()
