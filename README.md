<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>دردشة الأبطال</title>
    <style>
        /* هذا الجزء هو "الملابس" (CSS) لجعل الموقع جميلاً */
        body { font-family: sans-serif; background-color: #f0f2f5; display: flex; flex-direction: column; align-items: center; padding: 20px; }
        #chatBox { width: 300px; height: 400px; background: white; border: 2px solid #ddd; border-radius: 10px; overflow-y: auto; padding: 10px; margin-bottom: 10px; }
        input { width: 220px; padding: 10px; border-radius: 5px; border: 1px solid #ccc; }
        button { padding: 10px; background-color: #25d366; color: white; border: none; border-radius: 5px; cursor: pointer; }
        .message { background: #e1ffc7; padding: 8px; margin: 5px 0; border-radius: 5px; border-bottom: 1px solid #99f3a6; }
    </style>
</head>
<body>

    <h2>💬 غرفة دردشة الأبطال</h2>

    <div id="chatBox"></div>

    <div>
        <input type="text" id="userMessage" placeholder="اكتب رسالة لزميلك...">
        <button onclick="sendIt()">إرسال</button>
    </div>

    <script>
        // هذا هو "العقل" (JavaScript)
        function sendIt() {
            // 1. العقل يذهب للمربع ويأخذ الكلام المكتوب
            let box = document.getElementById("userMessage");
            let chat = document.getElementById("chatBox");

            if (box.value !== "") {
                // 2. يصنع "بالونة" جديدة للرسالة
                let newMsg = document.createElement("div");
                newMsg.className = "message";
                newMsg.innerText = "أنا: " + box.value;

                // 3. يضع البالونة داخل صندوق الدردشة
                chat.appendChild(newMsg);

                // 4. يمسح المربع ليكون جاهزاً للكتابة مرة أخرى
                box.value = "";
                
                // 5. يجعل الصندوق ينزل للأسفل آلياً لرؤية آخر رسالة
                chat.scrollTop = chat.scrollHeight;
            }
        }
    </script>

</body>
</html>
