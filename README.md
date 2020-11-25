# MQTT Server with Node.js
## MQTT Server
MQTT ย่อมาจาก Message Queuing Telemetry Transport เป็น Protocol ที่ออกแบบมาเพื่อการเชื่อมต่อแบบ M2M (machine-to-machine) หรือก็คืออุปกรณ์กับอุปกรณ์ด้วยกันเอง MQTT ถูกออกแบบโดยใช้สถาปัตยกรรมแบบ Client/Server ซึ่งมี topology แบบ hub-and-spoke ผ่านเครือข่าย TCP/IP เป็นหลัก 

### Features

- ทำให้สามารถเชื่อมโยงการสื่อสารกับอุปกรณ์ต่าง ๆ ได้ผ่านเครือข่ายอินเทอร์เน็ต
- MQTT Protocol นี้จะมีน้ำหนักเบามากกว่าการใช้ HTTP Protocol 
- ออกแบบมาเพื่อใช้งานกับอุปกรณ์อิเล็กทรอนิกส์ขนาดเล็กโดยเฉพาะ ใช้ Bandwidth ต่ำ 
- ใช้หลักการ Publisher / Subscriber ผ่านตัวกลางที่เรียกว่า Broker

### Mosquitto MQTT Broker
Eclipse Mosquitto เป็น open source (EPL/EDL licensed) ที่ใช้สำหรับทำเป็น Broker ในระบบ MQTT Protocal ซึ่งติดตั้งและใช้งานได้ง่าย

#### Install Mosquitto MQTT Broker

```
    $ sudo apt-get install mosquitto mosquitto-clients
```
### ทดสอบการทำงาน 
- terminal ขึ้นมาจำนวน 2 terminal  
- terminal แรกจะทำหน้าที่เป็น subscriber โดยในที่นี้จะทำการ subscribe ไปยัง topic ที่มีชื่อว่า test ด้วยคำสั่ง

```
   $ mosquitto_sub -h localhost -t test
```
- terminal ที่สองจะทำหน้าที่เป็น publisher โดยในที่นี้จะทำการส่งข้อความว่า hello world ไปยัง topic test ด้วยคำสั่ง
```
   $ mosquitto_pub -h localhost -t test -m "hello world"
```

