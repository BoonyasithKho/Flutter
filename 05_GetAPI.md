# Get API
- การทำงานของ Flutter มี 2 แบบ คือ
<p align="center">
  <img src="https://imgs.developpaper.com/imgs/1908617955-5c5c2a730b8ca_articlex.png"> 
</p>

  - การทำงานแบบ Synchronous คือ การทำงานแบบตามลำดับ ต้องให้งานก่อนหน้าเสร็จก่อนถึงจะทำงานในขั้นตอนต่อไป
  - การทำงานแบบ Asynchronous หรือ Non-blocking คือ การทำงานที่สามารถสลับไปทำงานอื่นได้โดยไม่ต้องรอกัน ซึ่งต้องมีการพ่วงการใช้งานกับ Future
    - Future คือ การนำค่าที่เกิดขึ้นในอนาคตมาใช้งาน ซึ่งจะทำการเช็คข้อมูลที่เกิดขึ้นผ่าน State เช่น สมบูรณ์ (Complete), ไม่สมบูรณ์ (Incomplete) เป็นต้น เมื่อมีการทำงานแบบ Asynchronous จะมีการใช้งานร่วมกับคำสั่ง async และ await สำหรับรอให้ทำงานจนเสร็จ
        ```
        Future <return type> ชื่อ Future async {
            await .....;
        }
        ```

- API คือ วิธีเรียกใช้งานโปรแกรม เป็นรูปแบบโปรแกรมกับโปรแกรม เพื่อใช้สำหรับการแลกเปลี่ยนข้อมูลระหว่างกัน ผ่านทาง Internet โดย
    โปรแกรมต้นทาง จะเรียกว่า Server คอยเปิดและให้บริการข้อมูล
    โปรแกรมปลายทาง จะเรียกว่า Client สำหรับเรียกใช้บริการจาก Server
- การทำงานของ API
  - ผู้ให้บริการจะเป็นคนกำหนดกฏการเรียกใช้งานข้อมูล ซึ่งก่อนทำการเรียกใช้งาน API จะต้องรู้ว่าใช้คำสั่งอะไร (1 คำสั่ง = 1 API) 
  - OpenAPI คือ API ที่เปิดให้คนนอกสามารถเข้าถึงข้อมูลได้
  - Request การส่งคำขอเพื่อใช้บริการ API
  - Response การตอบกลับข้อมูลตามคำขอที่ส่งไป (ได้หรือไม่ได้)
- Web API คือ การให้บริการข้อมูลผ่าน Website โดย HTTP ซึ่งอยู่ในรูปแบบ XML และ JSON ซึ่งข้อมูล (ภาพ,เสียง,ข้อมูลทางธุรกิจ) จะเรียกว่า Resource
  - HTTP Method คือ ตัวที่บ่งบอกการกระทำกับข้อมูล
      - Get Method สำหรับร้องขอข้อมูล
      - POST Method สำหรับสร้างข้อมูลใหม่
      - PUT Method สำหรับอัพเดทข้อมูล
      - DELETE Method สำหรับลบข้อมูล
  - การใช้งาน WebAPI ใน Flutter ต้องทำการติดตั้ง HTTP Package เพื่อรับ/ส่ง ข้อมูล
      - เรียกใช้งาน WebAPI ในส่วนของ initState() 
      - กรอก url ของ API ที่ต้องการ
      - ทำการทดสอบการผลแสดงข้อมูล ถ้าแสดงผลได้ปกติแปลว่าสามารถใช้งาน API นั้นได้ โดยข้อมูลที่เข้ามาถ้าอยู่ในรูปแบบ JSON ต้องทำการแปลงให้สามารถใช่งานใน dart ได้
      
      ```
      import 'package:http/http.dart' as http;  // ต้อง import package ก่อนการเรียกใช้งาน
      
       @override
       void initState() {
          super.initState();
          getExchangeRate();
       }
       Future<void> getExchangeRate() async {
          var url = "https://covid19.ddc.moph.go.th/api/Cases/today-cases-by-provinces";
          var response = await http.get(Uri.parse(url));
          print(response.body);
       }
       ```
       - แปลง JSON object ไปใช้ใน dart ด้วย https://app.quicktype.io/
       - 
  - 
