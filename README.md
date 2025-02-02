<!DOCTYPE html>
<html>

<head>
    <title>تسجيل دخول المريض</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-auth-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-firestore-compat.js"></script>
    <script>
        // معلومات مشروعك في Firebase (استبدل هذه القيم بمعلومات مشروعك)
        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "YOUR_AUTH_DOMAIN",
            databaseURL: "YOUR_DATABASE_URL",
            projectId: "YOUR_PROJECT_ID",
            storageBucket: "YOUR_STORAGE_BUCKET",
            messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
            appId: "YOUR_APP_ID"
        };

        // تهيئة Firebase
        firebase.initializeApp(firebaseConfig);

        // الحصول على مثيلات الخدمات
        const auth = firebase.auth();
        const db = firebase.firestore();
    </script>
</head>

<body>
    <header>
        <h1>تسجيل دخول المريض</h1>
    </header>
    <div class="container">
        <form id="patientLoginForm">
            <label for="patientName">اسم المريض:</label><br>
            <input type="text" id="patientName" name="patientName" required><br><br>

            <label for="patientEmail">البريد الإلكتروني:</label><br>
            <input type="email" id="patientEmail" name="patientEmail" required><br><br>

            <label for="patientPassword">كلمة المرور:</label><br>
            <input type="password" id="patientPassword" name="patientPassword" required><br><br>

            <label for="patientConfirmPassword">تأكيد كلمة المرور:</label><br>
            <input type="password" id="patientConfirmPassword" name="patientConfirmPassword" required><br><br>

            <label for="patientBirthdate">تاريخ الميلاد:</label><br>
            <input type="date" id="patientBirthdate" name="patientBirthdate" required><br><br>

            <label for="patientGender">الجنس:</label><br>
            <select id="patientGender" name="patientGender" required>
                <option value="male">ذكر</option>
                <option value="female">أنثى</option>
            </select><br><br>

            <button type="submit">تسجيل الدخول</button>
        </form>
    </div>

    <script>
        const patientLoginForm = document.getElementById('patientLoginForm');

        patientLoginForm.addEventListener('submit', (event) => {
            event.preventDefault(); // منع إرسال النموذج بشكل افتراضي

            // الحصول على بيانات النموذج
            const patientName = document.getElementById('patientName').value;
            const patientEmail = document.getElementById('patientEmail').value;
            const patientPassword = document.getElementById('patientPassword').value;
            const patientConfirmPassword = document.getElementById('patientConfirmPassword').value;
            const patientBirthdate = document.getElementById('patientBirthdate').value;
            const patientGender = document.getElementById('patientGender').value;

            // هنا يمكنك إضافة كود للتحقق من البيانات وتسجيل المستخدم في Firebase
            // على سبيل المثال:
            // 1. التحقق من تطابق كلمات المرور
            // 2. إنشاء مستخدم جديد في Firebase باستخدام auth.createUserWithEmailAndPassword()
            // 3. تخزين بيانات المستخدم الإضافية (الاسم، تاريخ الميلاد، الجنس) في Firestore
        });
    </script>
    <footer>
        <p>&copy; 2023 Shebl</p>
    </footer>
</body>

</html>
