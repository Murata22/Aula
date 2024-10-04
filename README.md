<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laguna School Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .login-container {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 20px;
            width: 300px;
            text-align: center;
        }
        .login-container h1 {
            margin-bottom: 20px;
            color: #333;
        }
        .login-container label {
            display: block;
            margin: 10px 0 5px;
            color: #666;
        }
        .login-container input[type="number"],
        .login-container input[type="password"],
        .login-container select {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .login-container button {
            background-color: #007bff;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        .login-container button:hover {
            background-color: #0056b3;
        }
        .toggle-password {
            position: absolute;
            right: 30px;
            top: 155px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <h1>LAGUNA SCHOOL</h1>
        <form id="loginForm">
            <label for="cpf">CPF:</label>
            <input type="number" id="cpf" name="cpf" required>

            <label for="password">Senha:</label>
            <input type="password" id="password" name="password" required>
            <span class="toggle-password" onclick="togglePasswordVisibility()">👁️</span>

            <label for="userType">Tipo de Usuário:</label>
            <select id="userType" name="userType" required>
                <option value="">Selecione...</option>
                <option value="aluno">Aluno</option>
                <option value="professor">Professor</option>
            </select>

            <button type="button" onclick="redirectUser()">Acessar</button>
        </form>
    </div>

    <script>
        function togglePasswordVisibility() {
            const passwordField = document.getElementById('password');
            const type = passwordField.getAttribute('type') === 'password' ? 'text' : 'password';
            passwordField.setAttribute('type', type);
        }

        function redirectUser() {
            const userType = document.getElementById('userType').value;
            if (userType === 'aluno') {
                window.location.href = 'pagina_aluno.html';
            } else if (userType === 'professor') {
                window.location.href = 'pagina_professor.html';
            } else {
                alert('Por favor, selecione um tipo de usuário.');
            }
        }
    </script>
</body>
</html>
