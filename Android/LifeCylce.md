# LifeCylce
> 작성일자 2022/06/23 19:56</br>
> 작성자 whathe-downtown
> 오류/수정 문의 dbcjdrb1997@gmail.com
## 🍎Activitiy
- 에 보여지는 부분의 기능을 담당함
<p>Activitiy는 한 앱이 다른 앱을 호출할 때 호출 앱은 다른 앱을 전체적으로 호출 하는것이 아니라 다른 앱의 활동을 호출합니다.</p>

## 🍎LifeCycle
![스크린샷 2022-06-24 오후 2 25 18](https://user-images.githubusercontent.com/70245821/175468174-ef797a1f-4ae1-40a6-aea6-0a74fba7ab4a.png)

사용자가 앱을 탐색하고 , 나가고 , 다시 돌아오는 과정을 진행하면 수명 주기 안에서 다른 상태에 의해 전환이 됩니다. 
- 사용자 (Me) 가 앱을 사용하다가 도중에 전화 OR 다른 앱 전환 할 때 비정상 종료되는 문제
- 앱을 활발하게 사용하지 않을때 귀중한 시스템 리소스 소비되는 문제
- 가로 방향 세로 방향 전환할 경우 , 비정상 종료 OR 데이터 유실 OR 진행 상태 저장되지 않는 문제 

### 🍏순서 
onCreate() -> onStart() -> onResume() -> onPause() -> onStop() -> onRestrart() or onDesotry()<br>

### 🍏onCreate() 
- Activity가 최조 생성되고 시스템 활동을 생성할 때 실행되는 것 , 필수적인것
- 활동의 전체 수명 주기 동안 한 번만 발생한다
- savedInstanceState 매개변수를 수신 
- setContentView 에 객체에 새로운 View 생성 및 ViewGroup 구축 할 때 onCreate에서 호출 

### 🍏onStart()
- onCreate() 직후 화면 보이기전에 호출
- 네트워크 통신 및 데이터 받는 작업, 서비스 OR 리스너 등록 등의 작업

### 🍏onResume()
- 액티비티가 멈췄다가 다시 실행될 때(재개) 필요한 작업을 한다  (홈 버튼 눌른다음 다시 돌아올 때)

### 🍏onPause()
- 다른 Activity 활성되었을 때 호출한다. (홈 버튼 눌었을때)
- onPause() 상태 있다가 메모리 부족하면 Process Kill(작업관리자 삭제 ) 메모리 반환
- onPause() 실행은 매우 짧고 저장 작업을 수행하는데 부적합 

### 🍏onStop()
- Activity가 더이상 보이질 않을때 호출된다
### 🍏onRestart()

### 🍏onDesotry()
- 시스템 자원 메모리등 부족해서 앱이 종료되거나 ,finsih() 코드를 실행했을때 호출된다.

## 간단히 


🍏앱을 이렇게 실행하면</br>
onCreate() -> onStart() -> onResume() 형태로 시작되어 Activity Running 상태가 된다</br>

![스크린샷 2022-06-24 오후 5 56 16](https://user-images.githubusercontent.com/70245821/175501005-339f9119-525c-410e-aa45-0a41f96f89f4.png)


🍏 만약 홈 버튼을 누르면?!</br>
onPoause()-> onStop()</br>
![스크린샷 2022-06-24 오후 5 58 08](https://user-images.githubusercontent.com/70245821/175501370-f6eafc6d-3ffd-43eb-b73f-27d12a961ba8.png)

🍏 다시 앱에 돌아와서 재개하면?</br>
onRestart() -> onResume() -> Activity Running</br>
![스크린샷 2022-06-24 오후 5 56 16](https://user-images.githubusercontent.com/70245821/175501005-339f9119-525c-410e-aa45-0a41f96f89f4.png)

🍏 화면 가로<=> 세로 전환하면</br>
onPause() => onStop() => onDestory() => onCreate() => onStart() => onResume() => Activity Running</br>

![스크린샷 2022-06-24 오후 6 02 32](https://user-images.githubusercontent.com/70245821/175502132-481a585e-67da-4dee-84e7-7e8e3324b450.png)

