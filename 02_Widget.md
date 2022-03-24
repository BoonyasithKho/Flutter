# Widget
 - Flutter จะมองทุกอย่างเกือบทั้งหมดเป็น widget
 - Widget คือ ส่วนที่ถูกใช้สร้างเป็นหน้าตาของ App หรือ User Interface (UI) โดยนำมาประกอบเรียงกันเป็นลำดับขั้นขึ้นเป็นโครงสร้าง แต่ละ widget จะถูกวางซ้อนอยู่ภายใน Parent widget และได้รับการส่งต่อสืบทอดคุณสมบัติต่างๆ จาก Parent อีกที แม้กระทั้ง application object ก็ถือเป็น widget ซึ่งเราเรียกว่า root widget 
 - MaterialApp คือ root widget
 - จำแนก Widget ตามการใช้งาน ได้ดังนี้
    - ใช้กำหนดโครงสร้าง (Structural Element) เช่น ปุ่ม button หรือ menu
    - ใช้กำหนดลักษณะ หรือรูปแบบ (Stylistic Element) เข่น font หรือ color
    - ใช้จัดวาง และกำหนดมุมมองเลเอาท์ (Aspect of Layout) เช่น padding หรือ alignment
## Layouts in Flutter

<p align="center">
  <img src="https://docs.flutter.dev/assets/images/docs/ui/layout/sample-flutter-layout.png"> 
</p>

  - Row และ Column เป็นเลเอาท์ที่ใช้บ่อยที่สุดในการกำหนดตำแหน่ง widget
  - แต่ละ Row และ Column มี child widget ได้หลายตัว
  - สำหรับจัดการ Layout ของหน้าแอพ แบบ Row เป็นการจัดเรียง Widget แบบซ้าย-ขวา ส่วน Column เป็นการจัดเรียงแบบบน-ล่าง
  - หากมีการแสดงผลมากเกินขนาดของหน้าจอต้องเปลี่ยน Row หรือ Column ให้เป็น ListView เพื่อให้สามารถทำการ Scroll ดูข้อมูลได้
     ```
      scrollDirection: Axis.horizontal // เลื่อนในแนวนอน
      scrollDirection: Axis.vertical,   // เลื่อนในแนวตั้ง
     ```
  - Container เป็น Widget ทำหน้าที่เป็น พื้นที่ที่รวบรวม Widget ต่างๆ เอาไว้ ตัว Container มี Widget ภายในสามารถแบ่งออกเป็น Layer ได้แบบนี้
<p align="center">
 <img src="https://toupawa.com/content/images/2021/02/margin-padding-border-9616dd0d7af45b95e6fcface25cd933b6b4a0fda51c1ab1bb9287bc8ed92c356.png">
</p>

  - ใน Container จะถูกกำหนดโดย Properties ที่ชื่อ child ซึ่งสามารถบรรจุ Widget ได้หลายชนิด สามารถใน เช่น Row, Column, Image หรือว่าเป็น Container เอง ตัวใดตัวหนึ่งเพียงตัวเดียว
  - Stack -> สร้างลำดับการซ้อนทับในหน้า Layout เวลาใช้งาน ให้มองภาพ 2D ให้เป็น 3D แล้วเรียบเรียงด้านหน้า-ด้านหลังของ Widget นั้น
  - ListView −> แสดงผล children widget เป็นแบบ list
  - GridView −> แสดงผล children widget เป็นแบบ gallery
  - Expanded −> ใช้สำหรับการขยาย children widget เพื่อให้เต็มพื้นที่การแสดงผล
  - Table −> แสดงผลข้อมูลในรูปแบบตาราง
  - Flow −> แสดงผลข้อมูลในรูปแบบคลิกเพื่อแสดงข้อมูล
