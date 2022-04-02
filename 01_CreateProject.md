# Create Project
1. Open VS CODE
2. Press CTRL+Shift+P
3. type 'Flutter new Project'
4. Select Folder
5. Defind Project Name
6. Wait...
7. Create Project Finished
8. Press F5 to Start Debugging (Select Device to use for Result)
9. Emulator will show first Project of flutter for press '+' to increase counter result.
10. Structure of Project
    - Folder Lib เก็บไฟล์ที่แยกหน้าแอพต่าง ๆ ที่นามสกุล .dart ซึ่งการทำงานบนหน้าจอต่าง ๆ จะอยู่ในโฟลเดอร์นี้
    - pubspec.yaml ใช้สำหรับการตั้งค่าต่าง ๆ ให้กับโปรเจคหรือการเรียกใช้งานไลบราลีต่าง ๆ การประกาศไลบราลี ไอคอน ต้องทำการตั้งค่าในไฟล์นี้
    - android, ios ใช้สำหรับการเก็บโปรเจคของ Application แต่ละระบบเอาไว้ เมื่อทำการรันจะมีการเก็บลงตามระบบปฏิบัติการ สามารถทำการแก้ไขจะเป็นการดำเนินการในแต่ละระบบปฏิบัติการ เช่น 
        - เปลี่ยนชื่อ App ใน Android แต่ไม่ได้เปลี่ยนใน iOS จะทำใหชื่อแอพใน 2 ระบบปฏิบัติการไม่เหมือนกัน ถ้าต้องการให้เหมือนกันต้องเปลี่ยนทั้ง 2 โฟลเดอร์
        - เปลี่ยน Icon App ด้วย Flutter_launcher_icons หากมีปัญหาไม่สามารถเปลี่ยน icon ได้ (วิธีแก้ https://stackoverflow.com/questions/70611977/flutter-flutter-launcher-icons-error-pub-finished-with-exit-code-255)
