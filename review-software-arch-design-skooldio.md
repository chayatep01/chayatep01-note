# รีวิวคอร์ส Software architecture design แบบสั้นๆ 

**Specialist Collaboration** <br>
เป็น Topic เกี่ยวกับการทำงานร่วมกันภายในทีม Development <br>
  **- N-tier architecture** เป็นการแบ่ง Application เป็น Layer ซึ่งการทำงานระหว่าง Layer จะเรียกผ่าน Parent ได้อย่างเดียวจะเรียกข้ามไม่ได้ 
ตัวอย่างเช่น Request handler (รองรับ, filter Request) -> Service (Logic) -> Repository (Data query) ซึ่งพอเป็น Layer จะไม่สามารถเรียกข้าม Layer ได้  

**- MVC** หรือ Model view controller ที่เรารู้จักกันดี แต่ในคอร์สนี้ทำให้ผมเข้าใจคำว่า Model ใหม่ เดิมทีผมเข้าใจว่ามันคำที่ล้อมาจาก model ของ data แต่จริงๆแล้วมันรวมไปถึงส่วนที่เป็น Business logic หรือ Internal logicอีกด้วย Controller ก็จะมีหน้าที่ในการ handle request/response โดยก่อนจะ Response ก็จะอ้างอิงการ display จาก View อีกทีนึง

**- Clean architecture** ซึ่งประกอบด้วย Entity ที่เป็น Business rules, Use cases การใช้งานในแต่ละ business rule, Interface adapter เป็นส่วนที่ต่อกับ Third party และ Driver เป็นตัว handle input output

**Business Collaboration** <br>
 เป็น Topic เกี่ยวกับการพูดคุยระหว่างทีม Business และ ทีม Development <br>

 **- Domain driven design**
   Domain discovery เป็นการ Gathering requirement โดยทำให้ง่ายต่อการเขียน Code ที่สุด <br>
   Strategic DDD การแบ่ง Domain แบบย่อยๆ <br>
- Bounded context : การใช้ภาษาของแต่ละ Area (ในคอร์สยกตัวอย่างเป็น แผนก) <br>
- Ubiquitous language : ภาษาใน Area นั้นๆ <br>
- Context mapping : การ mapping ความเข้าใจ context ของคำ <br>

**- Tactical DDD** การเขียน Code ให้ล้อกับBusiness model โดยการแบ่ง Verb และ Noun ให้ชัดๆ <br>ประกอบด้วย 5 component สำคัญ <br>
- Entity: Noun เช่นแบบ User, Course, Shipping cart
- Value object: Constant เช่น Color (สีฟ้ายังไงก็เป็นสีฟ้า), Datetime
- Service: stateless object
- Aggregate: เป็นกลุ่มของ Entity แต่สิ่งสำคัญคือ Consistency access (Aggregate root)
- Domain event: เป็นการ Centralize event โดย แต่ละ Domain จะ subscribe และหากเป็นหน้าที่รับผิดชอบของตัวเองจะนำไปรับผิดชอบต่อ

**Organization Collaboration** <br> 
เป็น Topic ในการ Collaboration ภายในองค์กร

- Conway's Law การออกแบบ Architecture ให้ล้อกับโครงสร้างขององค์กร
- Cross-functional team 1ทีมที่รับจบครบทุกfeature
- Monolith Code based 1อันใหญ่ถ้วน ข้อดีคือ config network ง่าย (มีที่เดียว) ข้อเสียคือ มีการ conflict ใน codeบ่อย ถ้าทีมใหญ่ และ เป็น Single programming language
- Multi service แต่ละทีมมี Service ที่ตัวเองรับผิดชอบ ข้อดีคือ conflict น้อย, Autonomy tech stack, Autonomy manage release ข้อเสียมีปัญหาเรื่อง network เยอะ แต่ละ service config DB ถูก Internal port ไหม
- SOA VS Microservice
    SOA : Single source of truth (Avoid duplicate data)
    Microservice : Allow duplicate data



