!DOCTYPE html>
<html lang="ko">
<head> 
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>폼 제출 예제</title>
</head>
<body>
    <form id="myForm">
        <label for="name">이름:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">이메일:</label>
        <input type="email" id="email" name="email" required>

        <label for="message">메시지:</label>
        <textarea id="message" name="message" required></textarea>

        <button type="button" onclick="submitForm()">제출</button>
    </form>

    <script>
        function submitForm() {
            const name = document.getElementById("name").value;
            const email = document.getElementById("email").value;
            const message = document.getElementById("message").value;

            // Google Apps Script에 데이터 전송
            google.script.run.processForm(name, email, message);
        }
    </script>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>
</body>
</html>
