# Button and Icon
 - floatingActionButton ปุ่มที่มีลักษณะการแสดงผลแบบลอย ๆ ในมุมล่างขวามือ การใช้ปุ่มสามารถใส่ icon ได้ ด้วยการนำใส่ไปใน child:icon
   ```
   floatingActionButton: FloatingActionButton(
          onPressed: () {},
          child: Icon(Icons.add),
   )
   ```
   หากต้องการให้มีการเปลี่ยน State หลังจากการกด floattingButton ให้มีการกำหนดการเปลี่ยน state ใน onPressed
   ```
   ....
       onPressed: (){
         setState(() {
           number++;
         )};
       },
   ```
   สามารถทำการแยก setState() ออกเป็นฟังก์ชันแยกได้ เพื่อให้สะดวกต่อการแก้ไข
   
