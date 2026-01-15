# infornet_telecom
Site para validação de certificados digitais da Infornet Telecom.
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Validação de Certificado</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f0f2f5;
      padding: 50px;
    }
    h1 {
      color: #333;
    }
    input {
      padding: 10px;
      font-size: 16px;
      width: 300px;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      background-color: #4CAF50;
      color: white;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #45a049;
    }
    #resultado {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Valide seu Certificado</h1>
  <p>Digite o código do seu certificado para verificar se é válido.</p>
  
  <input type="text" id="codigo" placeholder="Digite o código do certificado">
  <br>
  <button onclick="validarCertificado()">Validar</button>
  
  <p id="resultado"></p>

  <script>
    // Lista de certificados válidos
    const certificados = {
      "INF-2026-0001": "João Silva - Emitido em 15/01/2026",
      "INF-2026-0002": "Maria Souza - Emitido em 15/01/2026",
      "INF-2026-0003": "Carlos Lima - Emitido em 15/01/2026"
    };

    function validarCertificado() {
      const codigo = document.getElementById("codigo").value.trim();
      const resultado = document.getElementById("resultado");

      if(certificados[codigo]) {
        resultado.innerHTML = `✅ Certificado válido: ${certificados[codigo]}`;
        resultado.style.color = "green";
      } else {
        resultado.innerHTML = `❌ Código inválido ou não encontrado`;
        resultado.style.color = "red";
      }
    }
  </script>
</body>
</html>
