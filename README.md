<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gerador de Senhas</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Gerador de Senhas</h1>
        <div class="password-display">
            <input type="text" id="password" readonly>
            <button onclick="generatePassword()">Gerar Senha</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}

.container {
    text-align: center;
    background-color: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.password-display {
    margin-top: 20px;
}

#password {
    width: 300px;
    padding: 10px;
    font-size: 24px;
    border: 1px solid #ccc;
    border-radius: 5px;
    text-align: center;
    margin-bottom: 10px;
}

button {
    padding: 15px 30px;
    font-size: 18px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    background-color: #007bff;
    color: #fff;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #0056b3;
}
function generatePassword() {
    let length = 12;
    let charset = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()_+?><:{}[]";
    let password = "";
    for (let i = 0; i < length; i++) {
        let randomChar = charset.charAt(Math.floor(Math.random() * charset.length));
        password += randomChar;
    }
    document.getElementById('password').value = password;
}

