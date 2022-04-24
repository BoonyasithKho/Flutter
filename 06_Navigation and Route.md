# Navigation and Route
- Navigator Widget คือ กลุ่มของ widget หรือ class ที่ใช้ร่วมกับ route ในการจัดการ widget ย่อยมาแอพ โดยมีการจัดวางโครงสร้างแบบ stack ซึ่งเป็นการซ้อนทับตามลำดับจากล่างขึ้นบน โดยแผนที่นำมาเรียงต่อกันคือส่วนของ Widget ย่อย แผนที่แสดงผลจะถูกแสดงซ้อนทับหน้าอื่น ๆ ไว้
- Operator ของ Stack มีสองตัวคือ
  - push : เป็นการนำสมาชิกมาไว้บนสุดของ stack 
    ```
    Navigator.push(
      context, 
      MaterialPageRoute(
        builder: (
          BuildContext context) {
            return Text("Page 2");
    }));
    ```
  - pop : เป็นการนำสมาชิกชั้นบนสุดออกจาก stack
  - SystemNavigator.pop() => ปิดแอพเพื่อออกไปหน้า Menu เครื่อง
- การทำเมนูแบบ Tab มีองค์ประกอบอยู่ 3 ส่วน คือ
  - DefaultTabController : ควบคุมระบบโดยรวมของ Tab Menu ทั้งหมด เช่น การกำหนดจำนวนเมนู เป็นต้น
  - TabBarView : แสดง Widget หน้าตาของแอพตรงส่วนของ Tab ที่เรากำลังทำงาน
  - TabMenu : ส่วนของเมนูที่แสดงใน Tab
 
