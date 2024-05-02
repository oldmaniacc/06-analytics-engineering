# 06-analytics-engineering
เข้าไปใน Folder 06-analytics-engineering

cd 06-analytics-engineering

สร้าง web server postgres ด้วย docker port 3000

docker compose up
สร้าง ENV สำหรับการเขียน code Python และเก็บ package
python -m venv ENV
Activate เพื่อเข้าไปใน ENV เพื่อเก็บ package ต่างๆ
source ENV/bin/activate
download package สำหรับการใช้งาน dbt และ postgres
pip install dbt-core dbt-postgres
สร้างระบบฐานข้อมูลใน postgres และสร้าง profiles project ชื่อ ds525
dbt init
image

เข้าไปใน Folder ds525 (ยังอยู่ใน ENV)
cd ds525
หลังจากสร้าง profiles project สร้าง file ใน folder ds525/models ด้วยชื่อ profiles.yml และนำข้อมูลทั้งหมดจาก code ด้านล่าง มาใส่ไว้ใน file profiles.yml ที่เราสร้างใน ds525/models
code /home/codespace/.dbt/profiles.yml
ทดสอบการ connection กับ postgres
ทดสอบการ connection กับ postgres
การนำข้อมูลขึ้นบน postgres จะใช้ข้อมูลจาก ds525/models .sql และใช้โครงสร้างในการ source ข้อมูลจาก _src.yml / dbt_project.yml ใช้ในการกำหนดโครงสร้างชื่อหรือประเภท tables/view ที่สร้าง และไม่สนใจโครงสร้างของ folder
จากนั้นรันคำสั่ง test เพื่อเช็ค data quality
ปิดการทำงาน docker
docker compose down
ออกจาก ENV
deactivate
