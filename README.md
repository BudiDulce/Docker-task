# Docker-task
خطوات توضيحية لكل اللي عملته عشان نشغل تطبيق Flask ونربطه بقاعدة بيانات PostgreSQL باستخدام docker.
1. شغلت ال  Container Ubuntu (Docker)
باستخدام ال command : docker run -d ubuntu sleep infinity 
 وده عشان تفضل شغاله فال background

 2. Dockerfile لتطبيق Flask
Dockerfile عشان نحول تطبيق الـ Flask بتاعنا لصورة Docker جاهزة للتشغيل.


 أنشأنا Dockerfileبيستخدم صورة Python كقاعدة.
نسخنا ملفات التطبيق زي app.py وملف المكتبات المطلوبة requirements.txt جوه الصورة.
 ثبتنا كل المكتبات اللي التطبيق محتاجها من ملف requirements.txt.
 جهزنا الـ Dockerfileعشان يشغل التطبيق على بورت 5000.
حددنا أمر التشغيل بتاع التطبيق اللي هو python app.py


3- Docker Compose

Flask وقاعدة بيانات PostgreSQL مع بعض في بيئة واحدة وبسهولة.

عملنا ملف docker-compose.yml.
عرفنا خدمتين (containers) جواه:
خدمة الويب (Web Service): دي اللي هتشغل تطبيق Flask بتاعنا، وهتتبني من الـ Dockerfile اللي عملناه.
    خدمة قاعدة البيانات (PostgreSQL Service): دي هتستخدم صورة PostgreSQL الرسمية.
عملنا ربط بين الخدمتين عشان تطبيق Flask يقدر يتكلم مع قاعدة البيانات.
شغلنا كل حاجة بالأمر ده:
    docker-compose up --build

4
نتأكد بقى ان كل حاجة تمام والتواصل بينا تمام ونجرب 

 
---


6. الفرق بين ARGو ENVفي Dockerfile



ARG (اختصار لـ Argument: (
    بيستخدم عشان تعرف متغيرات أثناء عملية بناءbuilding image  صورة Docker.
    قيمته بتكون موجودة بس وقت البناء وبتختفي بعد كده.
    مثال: ARG VERSION=1.0 (ممكن تستخدمها عشان تحدد إصدار معين وقت البناء).

ENV` (اختصار لـ Environment Variable):
 بيستخدم عشان تعرف متغيرات بيئية جوه الحاوية بعد ما تشتغل.
    قيمته بتفضل موجودة ومتاحة للحاوية طول ما هي شغالة.
    مثال: ENV DATABASE_URL=postgres://user:pass@db:5432/mydb (دي معلومات ممكن يحتاجها التطبيق وهو شغال)
 7- task 7 
 
 
