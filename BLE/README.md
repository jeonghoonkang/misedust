# BLE 모듈 기능  
## DustB 
### Dust + Bluetooth 모듈 작업 

## BLE 기능 요구 사항
### 하드웨어 구성
- 내장 BLE, 외장 BLE 선정 필요

### BLE 요구 기능
- 자신의 네트워크 구성 상황을 Braodcasting
- Wi-Fi, ifconfig 정보 등
- 네트워크 설정을 업데이트 
  - 네트워크 설정을 위한 KEY (암호) 업데이트
  
### 통신 프로토콜 
- Eddystone or Beacon 어느것을 사용할지 조사
- Eddystone는<br>
    https://github.com/google/eddystone/tree/master/eddystone-url/implementations/TI-CC2640 
    https://developer.estimote.com/eddystone/ 를 통해 대략 확인 가능
- BLE 단순 beacon은 페어링 방식에서 beacon을 개선해서 사용(임의수정)<br>
    ble만 있을때 0.1 sec로 beacon을 전송했을때 CR2032 동전베터리로 2주 동작함

### 전원 연결
- USB 어뎁터 에서 5V를 out -> 미세먼지 센서 -> ble 센서
- 커넥터 형태를 단순 USB로 하게 되면 사이즈를 매우 작게 할수도 있음
- 가장 큰 부피는 미세먼지 센서 (43x36x24mm)
- 5V 건전지 없음, 베터리 타입으로 5V 만들기 어려움 있음

### Display
- LED를 사용할것
- 3색을 사용하는게 좋을것으로 보임

### 기타
- 구름모양 반투명 아크릴을 붙여서 눈에 잘 띄게 할것
