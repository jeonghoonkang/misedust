# BLE 기반 시스템 기능  
## 개요
- 시스템은 BLE LED, Dust 센서, Raspi 로 구성됨
  - 시스템 조합1 BLE LED 와 Raspi + Dust 센서
  - 시스템 조합2 BLE LED 와 BLE Dust / Raspi 

## Dust LED
  - DUST 센서 데이터를 읽어서, Red / Blue / Green 등의 LED로 색깔 변환
  
### Dust + Bluetooth 모듈 작업 


## BLE 기능 요구 사항
### 하드웨어 구성
- 내장 BLE, 외장 BLE 선정 필요

### BLE 요구 기능
- 자신의 네트워크 구성 상황을 Braodcasting
- Wi-Fi, ifconfig 정보 등
- 네트워크 설정을 업데이트 
  - 네트워크 설정을 위한 KEY (암호) 업데이트
--위 기능은 beacon으로는 할수 없고 eddystone로 테스트 해보겠음
  
### 통신 프로토콜 
- Eddystone or Beacon 어느것을 사용할지 조사
- Eddystone는<br>
    https://github.com/google/eddystone/tree/master/eddystone-url/implementations/TI-CC2640 
    https://developer.estimote.com/eddystone/ 를 통해 대략 확인 가능
- BLE 단순 beacon은 페어링 방식에서 beacon을 개선해서 사용(임의수정)<br>
    ble만 있을때 0.1 sec로 beacon을 전송했을때 CR2032 동전베터리로 2주 동작함
- beacon 테스트용 코드 Sensortag 코드 확보 테스트 필요
- eddystone 테으트용 코드 eddystone 코드 확보 테스트 필요
- 추가적으로 Host Test, Simple Broadcaster, Central, Observer, Peripheral 등 프로그램이 있음<br>
   http://dev.ti.com/tirex/content/simplelink_cc2640r2_sdk_1_00_00_22/docs/blestack/html/cc2640/sample-applications.html
- BLE 요구 기능을 구현하기 위해서는 좀더 단순한 방식의 BLE 예제를 참고해볼 필요가 

### 전원 연결
- USB 어뎁터 에서 5V를 out -> 미세먼지 센서 -> ble 센서
- 커넥터 형태를 단순 USB로 하게 되면 사이즈를 매우 작게 할수도 있음
- 가장 큰 부피는 미세먼지 센서 (43x36x24mm)
- 5V 건전지 없음, 베터리 타입으로 5V 만들기 어려움 있음

### Display
- LED를 사용할것
- 3색을 사용하는게 좋을것으로 보임
- 현재 RED, GREEN, BLUE 3가지 LED를 붙임
- LED 디밍 되는지 확인 필요 (software)
- 저전력 or 확인용 or 단순기능용 버튼 필요 여부 고민
- 동작에 따른 LED를 미리 정의 할 필요 있음
- Fade in or out 구현 

### LED Working Define
- Power ON : R&G Toggle 10회(0.5초)
- Monitoring : 미세먼지 수치 X이하 Green Toggle(2초), 초과 Red Toggle(1초) 
- BLE Connect(필요?) : Blue Toggle (1초)
- 베터리 잔량(필요?) : Red & Green Toggle (0.3초)
- led 컨트롤 완료

### 기타
- 구름모양 반투명 아크릴을 붙여서 눈에 잘 띄게 할것

### Sensor Data Parsing
- SensorTag에 + Dust Task 추가 후 베터리 켜짐과 동시에 데이터 Parsing 동작하는 형태로 코드 완료
- 데이터 수신 코드 완료, PM2.5, PM10 데이터 Parsing 완료, 기본 동작은 센서에서 1초마다 ble모드로 데이터 전송


### Hardware
- TI사의 CC2650 테스트 완료
- Nordic사의 NRF51822 모듈 테스트 
