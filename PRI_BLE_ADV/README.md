RPI에서 BLE Advertisement message 만들어서 보내는 방법

* RPI에 내장된 BLE로 Adbertisement를 이용해서 네트워크 상태를 보내는 기능 구현
 - bluetoothctl: 5.48 업그레이드
 - adbertisement 발생 pyhon 코드 실행
 - RPI IP를 전송하는 코드 추가
 - 단말기로 RPI에 연결해서(Pairing) 간단한 명령어나 상태 확인 


* 5.48 업그래이드 & BLE Advertisement 실행 참고 링크 
 - https://scribles.net/updating-bluez-on-raspberry-pi-5-43-to-5-48<br>
   sudo apt-get install python-gobject -y 패키지가 안깔려있음<br>
   https://scribles.net/running-ble-advertising-example-code-on-raspbian-stretch/
    
   

