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
</pre>
สำหรับการลบ URL จะใช้คำสั่ง
<pre>
git remote rm origin
</pre>

## คำสั่งเกี่ยวกับการเพิ่มไฟล์

### Git Add
เป็นการเพิ่มไฟล์ลงไปใน Staging
<pre>
เพิ่มแบบระบุชื่อไฟล์
git add index.html
หรือกรณีเพิ่มหลายๆ ไฟล์ในโฟลเดอร์
git add .
</pre>

### Git Commit
เป็นการยืนยันการแก้ไขไฟล์จาก Staging ไปจัดเก็บใน Local Repository
<pre>
git commit -m "My Comment to Add File"
โดย -m หมายถึงข้อความที่เป็น comment
</pre>

### Git Reset
เป็นการยกเลิกการแก้ไขไฟล์ หรือลบไฟล์ และนำไฟล์ version ปัจจุบันกลับมา
<pre>
git reset index.html
หรือ
git reset --hard
หรือ
git checkout index.html
</pre>

## การทำงานเกี่ยวกับ Remote Repository

### Git Push
เป็นการส่งข้อมูลจาก Local ไปยัง Remote Repository
<pre>
git push origin master
</pre>

### Git Fetch
เป็นการ preview ดูว่า Local และ Remote Repository มีความแตกต่างกันหรือไม่ ซึ่งมันจะบอกว่า Local ของเราเท่ากัน, ใหม่กว่า หรือล้าสมัยกว่า Remote อยู่กี่ commit
<pre>
git fetch
</pre>

### Git Merge
เป็นคำสั่งในการรวม Local และ Remote Repository เข้าด้วยกัน หรือทำให้ Local และ Remote เท่ากันนั่นเอง
<pre>
git merge
</pre>

### Git Pull
เป็นการดึงโค้ดโปรแกรมที่มีการเปลี่ยนแปลงจาก Remote มายัง Local เปรียบเสมือนการใช้คำสั่ง git fetch + git merge นั่นเอง
<pre>
git pull origin master
</pre>

### Git Clone
เป็นการดึงโค้ดโปรแกรม และไฟล์ต่างๆ จาก Remote มายัง Local
<pre>
git clone git://github.com/myuser/mygit.git
</pre>

## SSH key

1. Open Git Bash.
<br><br>
2. Paste the text below, substituting in your GitHub email address.
<pre>
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
</pre>
3. When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
<pre>
> Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter]
</pre>
4. At the prompt, type a secure passphrase. For more information
<pre>
> Enter passphrase (empty for no passphrase): [Type a passphrase]<br>
> Enter same passphrase again: [Type passphrase again]
</pre>

## Adding your SSH key to the ssh-agent
1. Ensure the ssh-agent is running. You can use the "Auto-launching the ssh-agent" instructions in "Working with SSH key passphrases", or start it manually:
<pre>
# start the ssh-agent in the background
$ eval $(ssh-agent -s)
> Agent pid 59566
</pre>
2. Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.
<pre>
$ cat ~/.ssh/id_rsa.pub
</pre>
3. Add the SSH key to your GitHub account.
