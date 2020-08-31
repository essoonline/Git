Git ประกอบด้วยอะไร?
Git ประกอบด้วย Server และ Client
Server ก็จะมีผู้ให้บริการหลายที่ด้วยกัน เช่น GitHub, Bitbucket หรือเราสามารถหาโปรแกรม Git Server มาติดที่เครื่องใช้เองก็ได้
Client เป็น Plugin เมื่อถูกติดตั้งแล้วจะสามารถพิมพ์คำสั่งใน Command Line ได้ หรือเครื่องมือบางตัวอาจจะเป็นลักษณะ GUI ให้ใช้ง่ายๆ โดยทั่วไปจะดาวน์โหลด Git Client ที่ https://git-scm.com/downloads
Git แตกต่างกับ SVN อย่างไร?
Git แตกต่างกับ SVN ตรงที่
Git จะมีทั้ง Local Repository และ Remote Repository โดยทุกครั้งที่เรา commit เพื่อยืนยันคำสั่ง, มันจะเข้าไปอยู่ในส่วนของ Local ก่อน จนกว่าเราจะใช้คำสั่ง push จึงจะส่งไปเก็บใน Remote
SVN มี Remote Repository อย่างเดียว, ดังนั้นการ commit ยืนยันคำสั่ง, มันจะเข้าไปที่ remote เลย
ดังนั้น Git จึงค่อนข้างทำงานเร็วกว่า เพราะมันทำงานอยู่กับเครื่องของเราเองใน Local, และค่อนข้างคลีนและชัวร์กว่า SVN เพราะโค้ดโปรแกรมเราที่นิ่งแล้ว เราจึงค่อยส่งไปรวมใน Remote
คำสั่ง Git ที่ใช้บ่อย
คำสั่งมีมากมาย แบบที่ว่าเขียนในบทความคงไม่หมดแน่ๆ ดังนั้นในบทความนี้จะเขียนแค่คำสั่งพื้นฐานที่พอเริ่มใช้งานได้เท่านั้น รายละเอียดคงต้องทำงานจริงบ่อยๆ และศึกษาเพิ่มเติม ท่านก็จะใช้งานอย่างคล่องแคล่วเองครับ
คำสั่งพื้นฐาน
Git Config
ใช้หลังจากติดตั้งใหม่ๆ ให้ทำส่วนนี้ในครั้งแรก ครั้งเดียว
git config — global user.name “username”
git config — global user.email “your@email.com”
git config --global user.name "ekkazit"
git config --global user.email "ekkazit@gmail.com"
Git Init
เริ่มต้นการใช้งาน Git ในโฟลเดอร์ หรือไดเร็กทอรี่นั้น
cd myproject
git init
Git Status
ตรวจสอบสถานะของ repository ของเรา
git status
Git Log
คำสั่งตรวจสอบประวัติไฟล์ต่างๆ ใน repository ของเรา คล้าย git status
git log
Git Remote
เป็นคำสั่งจัดการ URL ของ repository ว่าเราจะฝากโค้ดไว้ที่ใด ตัวอย่างนี้จะเป็นการเพิ่ม URL ตั้งชื่อว่า origin
git remote add origin git@github.com:myuser/mygit.git
สำหรับการลบ URL จะใช้คำสั่ง
git remote rm origin
คำสั่งเกี่ยวกับการเพิ่มไฟล์
Git Add
เป็นการเพิ่มไฟล์ลงไปใน Staging
เพิ่มแบบระบุชื่อไฟล์
git add index.html
หรือกรณีเพิ่มหลายๆ ไฟล์ในโฟลเดอร์
git add .
Git Commit
เป็นการยืนยันการแก้ไขไฟล์จาก Staging ไปจัดเก็บใน Local Repository
git commit -m "My Comment to Add File"
โดย -m หมายถึงข้อความที่เป็น comment
Git Reset
เป็นการยกเลิกการแก้ไขไฟล์ หรือลบไฟล์ และนำไฟล์ version ปัจจุบันกลับมา
git reset index.html
หรือ
git reset --hard
หรือ
git checkout index.html
การทำงานเกี่ยวกับ Remote Repository
Git Push
เป็นการส่งข้อมูลจาก Local ไปยัง Remote Repository
git push origin master
Git Fetch
เป็นการ preview ดูว่า Local และ Remote Repository มีความแตกต่างกันหรือไม่ ซึ่งมันจะบอกว่า Local ของเราเท่ากัน, ใหม่กว่า หรือล้าสมัยกว่า Remote อยู่กี่ commit
git fetch
Git Merge
เป็นคำสั่งในการรวม Local และ Remote Repository เข้าด้วยกัน หรือทำให้ Local และ Remote เท่ากันนั่นเอง
git merge
Git Pull
เป็นการดึงโค้ดโปรแกรมที่มีการเปลี่ยนแปลงจาก Remote มายัง Local เปรียบเสมือนการใช้คำสั่ง git fetch + git merge นั่นเอง
git pull origin master
Git Clone
เป็นการดึงโค้ดโปรแกรม และไฟล์ต่างๆ จาก Remote มายัง Local
git clone git://github.com/myuser/mygit.git
