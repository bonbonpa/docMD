# TOC

- [Git Cheat Sheet](#git-cheat-sheet)
  * [Setup Git](#setup-git)
  * [Create Repo](#create-repo)
  * [Local Repo](#local-repo)
  * [Remote Repo](#remote-repo)
  * [Branches](#branches)
  * [Undo](#undo)
  * [Remove](#remove)
  * [Sync](#sync)
  * [Generate SSH](#generate-ssh)

# Git Cheat Sheet

## Setup Git

`git config --global user.name "DevAhoy"` : ตั้งชื่อ (เปลี่ยน “DevAhoy” เป็นชื่อของคุณเอง)

`git config --global user.email "devahoy@gmail.com"` : ตั้งค่าอีเมล์ (เปลี่ยน email เป็นชื่อคุณเอง)

`git config --global color.ui auto` : ตั้ง enable สีใน command line

[TOP^](#toc)

## Create Repo

`git init` : ทำการสร้าง local repo (ระบบจะสร้างโฟลเดอร์ .git ไว้ใน directory

`git clone URL` : ทำการ clone repo จาก Server (Github/Bitbucket) มาที่ local

[TOP^](#toc)

## Local Repo

`git status` : ทำการเช็คสถานะใน directory

`git add FILENAME` : เพิ่มไฟล์ FILENAME ไปที่ staging (พร้อมสำหรับ commit)

`git add .` : เพิ่มทุกไฟล์ที่มีการแก้ไข/เปลี่ยนแปลง

`git diff` : แสดงการเปลี่ยนแปลงของไฟล์

`git diff FIRST_BRANCH SECOND_BRANCH` : ทำการเปรียบเทียบระหว่าง branch1 กับ branch2

`git log` : โชว์ log history ของ git

`git log --online` : โชว์ log history แบบ 1 บรรทัด

`git commit -m "Message"` : ทำการ commit staged บันทึกลง Project History

`git commit` : บันทึก Project History แต่ละเปิด Text Editor ขึ้นมาเพื่อใส่ commit message

`git commit --amend` : เอาไว้แก้ไข commit ล่าสุด เช่น อยากเพิ่มไฟล์ที่หลัง หลังจาก commit แล้ว (รายละเอียดเพิ่มเติม : แก้ไข git commit ล่าสุด)

[TOP^](#toc)

## Remote Repo

`git push origin master` : ทำการ push โปรเจ็คไป remote repository (origin ชื่อ remote name, master คือชื่อ default ของ branch)

`git remote add ARG1 ARG2` : เพิ่ม remote มี 2 arguments : ARG1 = remote name (default : origin) , ARG2 = remote URL

`origin vs upstream` : กรณีที่เราทำการ fork repo (เฉพาะ Github) git remote add origin URL : คือ URL repo เรา ส่วน git remote add upstream URL คือ URL ต้นฉบับที่เราทำการ fork มา

`git remote -v` : โชว์รายชื่อ remote URL

`git remote set-url ARG1 ARG2` : ตั้งค่า/เปลี่ยน remote URL (มี 2 arguments : ARG1 = remote name, ARG2 = remote URL)

`git remote rename origin destination` : เปลี่ยนชื่อ remote

`git remote rm REMOTE_NAME` : ลบ remote repository

[TOP^](#toc)

## Branches

`git branch` : โชว์ list ของ branch ทั้งหมด

`git branch BRANCH_NAME` : สร้าง branch ใหม่

`git checkout BRANCH_NAME` : ทำการเปลี่ยน branch (ย้าย HEAD ไป branch ใหม่) ต้องมี branch อยู่

`git checkout -b BRANCH_NAME` : ทำการสร้างและเปลี่ยนไป branch ใหม่ (มีค่าเท่ากับ git branch BRANCH_NAME ต่อด้วย git checkout BRANCH_NAME)

`git branch -d BRANCH_NAME` : ทำการลบ branch

`git merge BRANCH_NAME` : ทำการรวม history ของ branch

[TOP^](#toc)

## Undo

`git reset --hard HEAD` : reset local repo

`git reset COMMIT` : ทำการ undo ทุกๆอย่างกลับไปที่ COMMIT ก่อนหน้า

`git reset FILENAME` : ทำการ undo ไฟล์ที่เคย add ไป

`git revert` : ทำการ undo แล้วสร้าง commit ใหม่ (ต่างกับ reset ตรงที่ reset จะย้อนไป commit เก่า แต่ revert จะสร้าง commit ใหม่)

[TOP^](#toc)

## Remove

`git rm FILENAME` : ทำการลบไฟล์ และให้ git ทำการ untracked ไฟล์ด้วย

`git rm --cached FILENAME` : ลบไฟล์ออกจาก git repo เฉยๆ ไม่ได้ลบใน directory

[TOP^](#toc)

## Sync

`git fetch` : เช็คการเปลี่ยนแปลงจาก remote repo

`git merge` : ทำการรวมการเปลี่ยนแปลงจาก remote มาที่ local repo

`git pull` : เช็คการเปลี่ยนแปลง และรวม (เหมือนกับการทำ git fetch และต่อด้วย git merge)

`git fetch upstream` : ทำการเช็คการเปลี่ยนแปลงจากไฟล์ต้นฉบับที่เราทำการ fork มา

`git rebase` : เหมือนกับ git merge แต่จะยุบ branch ที่แตกออกมารวมกับ branch หลักเลย

[TOP^](#toc)

## Generate SSH

`ssh-keygen -t rsa -C "devahoy@gmail.com"` : ทำการ generate SSH Key ไฟล์จะถูก gen ไว้ที่ ~/.ssh/id_rsa

`ssh -T git@github.com` : ทดสอบ test SSH ว่า OK หรือไม่

[TOP^](#toc)

Additional Resoures :

TH :
http://devahoy.com/posts/introduction-to-git-and-github/
http://up1.github.io/git-guide/index.th.html
http://www.slideshare.net/dekcomgang/git-book

ENG :
http://git-scm.com/
http://rypress.com/tutorials/git/index
http://gitimmersion.com/
https://www.git-tower.com/learn/git/ebook/command-line/introduction
https://www.atlassian.com/git/tutorials/
http://rogerdudler.github.io/git-guide/
http://git-scm.com/book/en/v2
https://blog.udemy.com/git-tutorial-a-comprehensive-guide/
https://www.atlassian.com/git/tutorials/
http://www.git-tower.com/learn/
http://gitimmersion.com/
http://pcottle.github.io/learnGitBranching/

Github
https://guides.github.com/
https://help.github.com/
