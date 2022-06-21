# Widget
 - Flutter จะมองทุกอย่างเกือบทั้งหมดเป็น widget
 - Widget คือ ส่วนที่ถูกใช้สร้างเป็นหน้าตาของ App หรือ User Interface (UI) โดยนำมาประกอบเรียงกันเป็นลำดับขั้นขึ้นเป็นโครงสร้าง แต่ละ widget จะถูกวางซ้อนอยู่ภายใน Parent widget และได้รับการส่งต่อสืบทอดคุณสมบัติ (Properties) ต่างๆ จาก Parent อีกที แม้กระทั้ง application object ก็ถือเป็น widget ซึ่งเราเรียกว่า root widget 
 - MaterialApp คือ root widget
 - จำแนก Widget ตามการใช้งาน ได้ดังนี้
    - ใช้กำหนดโครงสร้าง (Structural Element) เช่น ปุ่ม button หรือ menu
    - ใช้กำหนดลักษณะ หรือรูปแบบ (Stylistic Element) เข่น font หรือ color
    - ใช้จัดวาง และกำหนดมุมมองเลเอาท์ (Aspect of Layout) เช่น padding หรือ alignment
## Layouts in Flutter

<p align="center">
  <img src="https://docs.flutter.dev/assets/images/docs/ui/layout/sample-flutter-layout.png"> 
</p>

  - Row และ Column เป็นเลเอาท์ที่ใช้บ่อยที่สุดในการกำหนดตำแหน่ง widget โดย Row Widget ใช้ในการแสดงผลในแนวนอน ส่วน Column Widget ใช้ในการแสดงผลในแนวตั้ง
  - แต่ละ Row และ Column มี child widget ได้หลายตัว
  - สำหรับจัดการ Layout ของหน้าแอพ แบบ Row เป็นการจัดเรียง Widget แบบซ้าย-ขวา ส่วน Column เป็นการจัดเรียงแบบบน-ล่าง
  - หากมีการแสดงผลมากเกินขนาดของหน้าจอต้องเปลี่ยน Row หรือ Column ให้เป็น ListView เพื่อให้สามารถทำการ Scroll ดูข้อมูลได้
     ```
      scrollDirection: Axis.horizontal // เลื่อนในแนวนอน
      scrollDirection: Axis.vertical,   // เลื่อนในแนวตั้ง
     ```
  - Container เป็น Widget ทำหน้าที่เป็น พื้นที่ที่รวบรวม Widget ต่างๆ เอาไว้ (กล่องใส่ของ) ตัว Container มี Widget ภายในสามารถแบ่งออกเป็น Layer ได้แบบนี้
    <p align="center">
     <img src="https://toupawa.com/content/images/2021/02/margin-padding-border-9616dd0d7af45b95e6fcface25cd933b6b4a0fda51c1ab1bb9287bc8ed92c356.png">
    </p>

    - ใน Container จะถูกกำหนดโดย Properties ที่ชื่อ child ซึ่งสามารถบรรจุ Widget ได้หลายชนิด เช่น Row, Column, Image หรือว่าเป็น Container เอง ตัวใดตัวหนึ่งเพียงตัวเดียว
    - สามารถกำหนดขนาด รูปร่าง หรือจัดวางตำแหน่ง รวมไปถึงการแสดงลวดลายให้สวยงามได้ โดยใช้จะมีการขยายเต็มหน้าจอสำหรับการจัดวาง UI ให้เหมาะสมกับขนาดหน้าจอ
    - BoxDecoration ใช้สำหรับกำหนดรูปร่างของ Container เช่น สี ลักษณะรูปร่างของ Container
      ```
      Container(
        decoration: BoxDecoration(color: Colors.green,borderRadius: BorderRadius.circular(40)),
        height: 50,
      ),
      ```
    - Padding ใช้กำหนดระยะห่างของ Widget ออกจากขอบของ Layout หรือหน้าจอแสดงผล
      ```
      Padding(
          padding: const EdgeInsets.all(8.0),
          child: Column(...),
      ),
  - Stack -> สร้างลำดับการซ้อนทับในหน้า Layout เวลาใช้งาน ให้มองภาพ 2D ให้เป็น 3D แล้วเรียบเรียงด้านหน้า-ด้านหลังของ Widget นั้น
  - ListView −> แสดงผล children widget เป็นแบบ list
  - GridView −> แสดงผล children widget เป็นแบบ gallery
  - Expanded −> ใช้สำหรับการขยายความสูง children widget เพื่อให้เต็มพื้นที่การแสดงผล โดยผ่าน Flex Properties
  - Table −> แสดงผลข้อมูลในรูปแบบตาราง
  - Flow −> แสดงผลข้อมูลในรูปแบบคลิกเพื่อแสดงข้อมูล
## การใช้งาน Widget
  - ทำการ Import Lib >> import 'package:flutter/material.dart';
  - การเรียกใช้งาน widget จะต้องทำการเรียกใช้งานผ่าน fn. runApp() ต้องทำการระบุ widget ที่จะใช้งานลงไป ทำให้ได้ runApp(app); ตัวแปร app จะทำการเรียกใช้งาน MaterialApp(title: "My App",home: Text("Hello Dart"); ที่มี properties : title: "My App",home: Text("Hello Dart") หน้าจอจะแสดงผล Hello Dart ออกทางหน้าจอโดยไม่มีการจัดวางโครงสร้าง
  - การจัด Layout หน้าแอพด้วย Scaffold Widget จะมีการคำนวณระยะห่างระหว่างแอพกับหน้าจอ Emulator ให้อัตโนมัติ ใน Scaffold สามารถกำหนดการวาง Properties ของส่วนต่าง ๆ ได้ เช่น appBar เป็นส่วนของเมนูด้านบนแอพ และ body เป็นส่วนไว้สำหรับการแสดง Widget ที่ต้องการ
  - สามารถทำการเปลี่ยน Theme ของ App ได้ด้วยการใช้ Properties : theme ใน MaterialApp Widget ด้วยการกำหนด theme: ThemeData(primartSwatch: Colors.green)
  - สามารถสร้าง Widget ได้ 2 แบบ ซึ่งทั้งสองแบบสามารถเปลี่ยนไปเป็นอีกรูปแบบนึงได้
    1) Stateless Widget เป็น Widget ที่ไม่สามารถเปลี่ยนค่าได้ใช้สำหรับสร้าง Widget แบบคงที่ เช่น ข้อความ ไอคอน
    2) Stateful Widget เป็น Widget ที่สามารถเปลี่ยนแปลงค่าได้หรือทำงานได้หลาย State เช่น Checkbox Slider Textfield
  - การเรียกใช้งานในส่วน Main ให้ทำการเปลี่ยน runApp(app) -> runApp(MyApp()); เพื่อให้แยกส่วนการใช้งานออกจากกัน
  - Center widget เป็น widget ที่ใช้ครอบ widget อื่น ๆ เพื่อบังคับการแสดงผลให้อยู่กลางจอภาพ
  - การตกแต่ง Text Widget สามารถทำการเพิ่ม properties style: TextStyle(fontsize: 50,color: Colors.Blue), เข้าไปใน widget เพื่อทำการปรับสี และกำหนดขนาดของตัวอักษร
  - การนำภาพเข้ามาใช้ใน Flutter โดยใช้ Image Widget แล้วทำการกำหนด Path ของภาพ ถ้่านำภาพมาจาก url ก็ใช้ NetworkImage('URL')
  - Column Widget เป็นการนำ Widget มาเรียงลำดับในแนวตั้ง 
    ```
    Column(
     mainAxisAlignment: MainAxisAlignment.spaceEvenly, 
     Children: [
      Text('Hello Flutter'),
      Image(image: NetworkImage('URL')]);
    ```
    โดย mainAxisAlignment เป็น Property วางตำแหน่ง item ใน Column
  - Row Widget เป็นการนำ Widget มาเรียงลำดับในแนวนอน โดย เขียนคล้าย ๆ Column Widget
  - Listview Widget เป็น Widget ที่แสดงข้อมูลแบบรายการ เมื่อมีการแสดงผลเกินพื้นที่หน้าจอสามารถทำการเลื่อนหน้าจอหรือ Scroll Down ได้
    - List คือ โครงสร้างข้อมูลที่จัดการเกี่ยวกับกลุ่มข้อมูล
    - Listview จะใช้ในกรณีที่ต้องการแสดงผลรายการขนาดเล็ก (4-10 รายการ)
    ```
    List<Widget> data = [];
    data.add("สิ่งที่จะเพิ่มเข้าไปใน List");
    ```
    - สามารถนำ List ออกเป็นฟังก์ชันเพื่อให้ง่ายต่อการเรียกใช้งาน ดังนี้
    ```
    List<Widget> getData(int count) {
      List<Widget> data = [];
      for (var i = 0 ; i < count ; i++){
         data.add(Text("รายการที่ ${i+1}"));
      }
      return data;
    }
    ```
      ซึ่งเวลาเรียกใช้งานก็เรียกผ่าน ฟังก์ชัน getData(กำหนดค่าที่ต้องการให้แสดงจำนวนรายการ)
    - ListTile กำหนดรายละเอียดต่าง ๆ ของ List แต่ละรายการ เช่น หัวข้อ (title) และหัวข้อย่อย (subtitle)
    ```
    var menu = ListTile(
        title: Text(
          "เมนูที่ ${i + 1}",
          style: const TextStyle(color: Colors.blue),
        ),
        subtitle: Text("รายการย่อยที่ ${i + 1}"),
      );

    data.add(menu);
    ```
    - Listview.builder จะใช้ในกรณีที่มีการแสดงรายการจำนวนมาก ซึ่งเหมาะกับการแสดงผลข้อมูลจากฐานข้อมูลที่ไม่รู้ขีดจำกัด แต่สามารถกำหนดจำนวนการแสดงขีดจำกัดได้โดยระบุจำนวนรายการผ่าน Property ชื่อว่า itemcount
    ```
    ListView.builder(
      itemBuilder: (BuildContext context, int index) {
        return ListTile(
          title: Text("เมนูที่ ${index + 1}"),
        );
      },
      itemCount: 10,
    )
    ```
## State Widget
  - State คือ จำนวนหน้าต่างของแอพพลิเคชัน หากมีจำนวนหน้าต่างของแอพจำนวน 2 หน้า จะถือว่ามีจำนวน State ทั้งหมด 2 State
### Stateless Widget
   - Stateless Widget เป็น Widget ที่ไม่มีการเปลี่ยนแปลงตัวเอง การแสดงผลจะมีลักษณะคงที่ไม่เปลี่ยนแปลง
   - 

### Stateful Widget
   - Stateful Widget เป็น Widget ที่สามารถเปลี่ยนแปลงค่าได้ด้วยการ setState ตามที่ต้องการ
   - วงจรการทำงาน : initState() -> build() -> dispose()
     - initState() คือ Method ที่ถูกเรียกให้ทำงานครั้งเดียวหลังจากที่ state ถูกสร้างเรียบร้อยแล้ว สามารถที่จะเปลี่ยนแปลงข้อมูลของ Widget ได้
     - build() คือ Method ที่ใช้ในการสร้าง Widget หรือ Widget Tree ของแอพพฃิเคชัน ถ้าต้องการให้ Widget ของแอพมีหน้าตาแบบใดก็ให้เขียน Method build โดยจะถูกเรียกใช้งานเมื่อมีการเปลี่ยนแปลงข้อมูลใน State โดยทำงานผ่าน method setState()
     - dispose() คือ Method ที่ถูกใช้เมื่อ widget หรือ state หายไปจากหน้าแอพหรือให้หยุดทำงานและนำออกจากระบบ
