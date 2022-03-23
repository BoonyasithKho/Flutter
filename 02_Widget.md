# Widget
 - Flutter จะมองทุกอย่างเกือบทั้งหมดเป็น widget
 - Widget คือ ส่วนที่ถูกใช้สร้างเป็นหน้าตาของ App หรือ User Interface (UI) โดยนำมาประกอบเรียงกันเป็นลำดับขั้นขึ้นเป็นโครงสร้าง แต่ละ widget จะถูกวางซ้อนอยู่ภายใน Parent widget และได้รับการส่งต่อสืบทอดคุณสมบัติต่างๆ จาก Parent อีกที แม้กระทั้ง application object ก็ถือเป็น widget ซึ่งเราเรียกว่า root widget 
 - MaterialApp คือ root widget
 - จำแนก Widget ตามการใช้งาน ได้ดังนี้
    - ใช้กำหนดโครงสร้าง (Structural Element) เช่น ปุ่ม button หรือ menu
    - ใช้กำหนดลักษณะ หรือรูปแบบ (Stylistic Element) เข่น font หรือ color
    - ใช้จัดวาง และกำหนดมุมมองเลเอาท์ (Aspect of Layout) เช่น padding หรือ alignment
## Layouts in Flutter

<p align="center" style="background-color:#FFFFFF;">
  <img src="https://docs.flutter.dev/assets/images/docs/ui/layout/sample-flutter-layout.png"> 
</p>

  - Row และ Column เป็นเลเอาท์ที่ใช้บ่อยที่สุดในการกำหนดตำแหน่ง widget
  - แต่ละ Row และ Column มี child widget ได้หลายตัว
  - สามารถกำหนดแนวการจัดวางของ Row สำหรับการใช้งาน vertically และ Column สามารถใช้งาน horizontally
  - You can stretch or constrain specific child widgets.
  - You can specify how child widgets use the Row’s or Column’s available space.
  - ใน Container สามารถใน widget ได้ตัวเดียวคือ child widget
    ```
    child: Text('name');
    ```
    
   - หากมีการแสดงผลมากเกินขนาดของหน้าจอต้องเปลี่ยน Row หรือ Column ให้เป็น ListView เพื่อให้สามารถทำการ Scroll ดูข้อมูลได้

```
      scrollDirection: Axis.horizontal // เลื่อนในแนวนอน
      scrollDirection: Axis.vertical,   // เลื่อนในแนวตั้ง
