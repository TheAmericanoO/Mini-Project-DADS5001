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

Load ข้อมูล Dataset (.csv) เข้า Google Drive ซึ่งหลังจากโหลดไปแล้ว ไม่ทราบวิธีที่จะทำให้ python ไป read จากใน google drive แบบ public (ผ่าน URL) และไม่เกิดอาการ error เช่น อ่านไฟล์ไม่ได้เนื่องจาก encoding

![image](https://user-images.githubusercontent.com/111193026/195956550-fa0a3a0b-6a8f-4712-8cb8-e2d5d65451c5.png)

จากนั้น explore ข้อมูลนักฟุตบอล พบว่ามีชื่อซ้ำ 6 คนจึงทำการลบออก

![image](https://user-images.githubusercontent.com/111193026/195956621-ee460b2b-4cb7-4944-85a6-8c59cd268821.png)


















APPENDIX

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
