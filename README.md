# Mini-Project-DADS5001

This is the Mini-Project of DADS5001 Course in DATA SCIENCE AND DATA ANALYSIS MASTER DEGREE.

TOPIC: การวิเคราะห์ราคาค่าตัวนักเตะฟุตบอลพรีเมียร์ลีกกับปัจจัยต่าง ๆ

Dataset: (1) ข้อมูลค่าตัวนักฟุตบอล (2,642 row, 9 col) และ (2) สถิติการเล่น (498 row, 9 col)

/

/

<<ความน่าสนใจ>>

ในช่วงหลังจะเห็นข่าวการซื้อขายนักฟุตบอลที่มีราคาทำสถิติโลกอยู่อย่างต่อเนื่อง กลายเป็นค่าตัวนักเตะเฟ้อ และสโมสรซื้อไปจะคุ้มค่าหรือไม่ ซึ่งสิ่งที่จะบอกว่าคุ้มหรือไม่ก็คือ ผลงานในสนาม ดังนั้น จึงสนใจที่จะนำข้อมูลสถิติการเล่นในสนามของนักฟุตบอล มาวิเคราะห์เทียบกับราคาค่าตัว รวมถึงปัจจัยอื่น ๆ ที่เกี่ยวข้อง เช่น สัญชาติ เป็นต้น

/

/

<<เริ่มต้น EDA>>

> Load ข้อมูล Dataset (.csv) เข้า Google Drive ซึ่งหลังจากโหลดไปแล้ว ไม่ทราบวิธีที่จะทำให้ python ไป read จากใน google drive แบบ public (ผ่าน URL) และไม่เกิดอาการ error เช่น อ่านไฟล์ไม่ได้เนื่องจาก encoding

![image](https://user-images.githubusercontent.com/111193026/195956550-fa0a3a0b-6a8f-4712-8cb8-e2d5d65451c5.png)


> จากนั้น explore ข้อมูลนักฟุตบอล พบว่ามีชื่อซ้ำ 6 คนจึงทำการลบออก ทำให้ข้อมูลของไฟล์นักฟุตบอลเหลือ 492 row

![image](https://user-images.githubusercontent.com/111193026/195956621-ee460b2b-4cb7-4944-85a6-8c59cd268821.png)


> ต่อมาสร้างคอลัมน์ใหม่ชื่อ 'PerformanceAvg' เพื่อสร้างทำตัวแทนที่จะใช้พิจารณาความสามารถของนักฟุตบอลแต่ละคน โดยการใช้เฉลี่ยค่าในคอลัมน์ 'G+A-PK' / 'npxG+xA.1' / 'ShotCreate.1' / 'Goal Creating.1' / 'PassComplete Shots.1' / 'ShotsOnTarget.1' (ความหมายของแต่ละคอลัมน์ดูได้จาก APPENDIX) 

![image](https://user-images.githubusercontent.com/111193026/195956960-5873255a-7852-45b9-bc25-77045e697e1c.png)


> ในส่วน dataset ค่าตัวนักฟุตบอลได้ปรับหน่วยของค่าตัว (column ชื่อ Value) ให้เป็นหน่วยล้านปอนด์ เพื่อให้สามารถแสดงค่าบนกราฟได้อย่างเหมาะสม

![image](https://user-images.githubusercontent.com/111193026/195957108-291938db-9ce0-4d57-86f4-7bd210c65f6c.png)


> เนื่องด้วยชุดข้อมูลค่าความสามารถของนักเตะมีอย่างจำกัด ซึ่งชุดข้อมูลที่มีนั้นจะสามารถชี้วัดความสามารถของนักเตะได้ดีในตำแหน่งกองกลางและกองหน้า เช่น การยิงประตู การส่งให้เพื่อนร่วมทีมยิงประตู ความแม่นยำในการส่ง เป็นต้น ดังนั้น จึงคัดเลือกข้อมูลเฉพาะของนักเตะในตำแหน่งกองกลางและกองหน้ามาทำการวิเคราะห์ต่อไป โดยตัดแล้วเหลือนักฟุตบอลจำนวน 206 คน และ Merge ข้อมูลของ 2 dataset เข้าด้วยกัน

![image](https://user-images.githubusercontent.com/111193026/195958284-53af70ff-ea87-4dc5-ae85-83e416542a98.png)


> Explore data ส่วนอื่น ๆ ต่อ ทั้งการกระจายตัวของค่าตัว ค่าความสามารถของนักฟุตบอล รวมถึ่งทวีปตามสัญชาติของนักฟุตบอลด้วย

![image](https://user-images.githubusercontent.com/111193026/195957256-4f9a3ec7-0e92-4361-b38d-12378c262f3e.png)

![image](https://user-images.githubusercontent.com/111193026/195957272-0923e404-a7a9-4196-a475-bc24276f98f7.png)

![image](https://user-images.githubusercontent.com/111193026/195957291-77cf5bd7-b3ad-4a41-b5b3-e9757ba7e095.png)

![image](https://user-images.githubusercontent.com/111193026/195957306-026783e5-a707-4e5c-8dab-dc33dbee3d01.png)

![image](https://user-images.githubusercontent.com/111193026/195957487-2aa2575b-f5b9-4dbb-b69e-e1ddb139e917.png)

/

/

<<Questions & Answers>>

1. ราคาค่าตัวของนักฟุตบอล แปรผันตาม ค่าความสามารถหรือไม่?

Ans: ราคาค่าตัวของนักฟุตบอล ไม่ได้แปรผันตามค่าความสามารถเสมอไป แต่ก็พบว่าส่วนใหญ่มีแนวโน้มที่จะเป็นไปในทางที่ตั้งสมมุติฐานไว้ จากกราฟด้านล่างจะเห็นว่ามีนักฟุตบอลบางคนที่ความสามารถไม่มาก แต่ค่าตัวสูง และในทางกลับกันมีนักเตะที่ความสามารถดี แต่ค่าตัวต่ำ

![image](https://user-images.githubusercontent.com/111193026/195957866-00144ac9-29bb-4deb-bcf9-e69709a1a65d.png)


2. ค่าเฉลี่ยของความสามารถและค่าตัวของนักเตะทั้งสองตำแหน่ง (กองกลางและกองหน้า) มีลักษณะเป็นอย่างไร?

Ans: ค่าเฉลี่ยของค่าตัวนักฟุตบอลตำแหน่งกองหน้าสูงกว่าประมาณ 7 แสนปอนด์ (คิดเป็น 3%) แต่ค่าเฉลี่ยความสามารถตำแหน่งกองหน้าสูงกว่าถึง 0.3 หรือคิดเป็น 30%

![image](https://user-images.githubusercontent.com/111193026/195958325-1da41177-b3b2-4683-b307-b1464af1f9bc.png)


3. ค่าตัวของนักฟุตบอลจากแต่ละทวีปมีลักษณะเป็นอย่างไร?

Ans: อันดับค่าตัวเฉลี่ยจากสูงสุดไปต่ำสุดเป็นดังนี้ Asia -> South America -> Africa -> Europe -> North America -> Oceania

![image](https://user-images.githubusercontent.com/111193026/195958473-5d4bfdea-61e7-4b75-a8ad-c04542bd272c.png)

![image](https://user-images.githubusercontent.com/111193026/195958486-98f11b91-b344-4cb5-a186-ca64a29377cc.png)


<<ความท้าทายที่พบ>>

1. มีปัญหากับการ import ข้อมูลเข้าสู่ google colab ใช้เวลานาน
2. ข้อมูลที่ใช้มีส่วนที่ explore ไม่ทั่วถึง ทำให้ต้องค้นหาข้อมูล dataset ใหม่
3. การตัดสินใจเลือกใช้กราฟที่จะนำเสนอข้อมูล เป็นสิ่งที่ต้องพิจารณา เพราะบางทีจินตนาการไปถึงแต่ว่าปฏิบัติไม่ได้ ทำให้ใช้เวลานานในการศึกษา


<<APPENDIX>>

- Column's Description -

G+A-PK: Goals plus Assists minus Penalty Kicks made per 90 mins

xA.1 : Expected Assits made per 90 mins

npxG+xA.1 : Non-Penalty Expected Goals plus Expected Assists made per 90 mins

ShotCreate.1 : Creation of shots for teammates per 90 mins

Goal Creating.1 : Participating in creating goal per 90 mins

PassComplete : Percentage of pass completion (including short, middle, long range passing)

Shots.1	: Shots per 90 mins

ShotsOnTarget.1 : Shots On Target per 90 mins

Value : Player's Market Value
