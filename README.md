### Git คืออะไร ?

Git คือ version control ตัวหนึ่ง ทำหน้าที่จัดเก็บประวัติ การเปลี่ยนแปลงของไฟล์ ในโปรเจ็กต์เรา โดยที่เราสามารถย้อนกลับไปดูในเวอร์ชั่นใดก็ได้ หรือเรียกเวอร์ชั่นนั้นกลับมาใช้งานใหม่ก็ได้ รวมถึงดูได้ว่าไฟล์นั้นมีใคร? ทำอะไร? เมื่อไร? ซึ่งช่วยอำนวยความสะดวกอย่างมาก โดยเฉพาะการทำงานเป็นทีม

### Git ประกอบด้วยอะไร?
Server ก็จะมีผู้ให้บริการหลายที่ด้วยกัน เช่น GitHub, Bitbucket หรือเราสามารถหาโปรแกรม Git Server มาติดที่เครื่องใช้เองก็ได้
<br><br>
Client เป็น Plugin เมื่อถูกติดตั้งแล้วจะสามารถพิมพ์คำสั่งใน Command Line ได้ หรือเครื่องมือบางตัวอาจจะเป็นลักษณะ GUI ให้ใช้ง่ายๆ โดยทั่วไปจะดาวน์โหลด Git Client ที่ https://git-scm.com/downloads

## คำสั่งพื้นฐาน

### Git Config
ใช้หลังจากติดตั้งใหม่ๆ ให้ทำส่วนนี้ในครั้งแรก ครั้งเดียว
<pre>
git config --global user.name "username"<br>
git config --global user.email "username@gmail.com"
</pre>

### Git Init
เริ่มต้นการใช้งาน Git ในโฟลเดอร์ หรือไดเร็กทอรี่นั้น
<pre>
cd myproject<br>
git init
</pre>

### Git Status
ตรวจสอบสถานะของ repository ของเรา
<pre>
git status
</pre>

### Git Log
คำสั่งตรวจสอบประวัติไฟล์ต่างๆ ใน repository ของเรา คล้าย git status
<pre>
git log
</pre>

### Git Remote
เป็นคำสั่งจัดการ URL ของ repository ว่าเราจะฝากโค้ดไว้ที่ใด ตัวอย่างนี้จะเป็นการเพิ่ม URL ตั้งชื่อว่า origin
<pre>
git remote add origin git@github.com:myuser/mygit.git
<pre>
สำหรับการลบ URL จะใช้คำสั่ง
<pre>
git remote rm origin
</pre>
