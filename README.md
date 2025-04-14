// server.js
const express = require('express');
const path = require('path');
const dotenv = require('dotenv');
const app = express();
dotenv.config();

const PORT = process.env.PORT || 3000;

app.use(express.static(path.join(__dirname, 'public')));

app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

app.listen(PORT, () => {
  console.log(`Servidor rodando na porta ${PORT}`);
});

// .env
/*
POSTGRES_DBNAME=troca_valores
POSTGRES_USER=admin
POSTGRES_PASSWORD=suasenha
SUPORTE_EMAIL=exchangeofvaluesinvestimento@gmail.com
*/

// public/index.html
/*
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Troca de Valores</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>Troca de Valores</h1>
    <p class="sub">Diga não à transfobia - Plataforma que apoia a comunidade trans</p>
  </header>
  <main>
    <section class="jogos">
      <button onclick="abrirJogo('roleta')">Jogar Roleta</button>
      <button onclick="abrirJogo('dados')">Jogar Dados</button>
      <button onclick="abrirJogo('cartas')">Jogar Cartas</button>
      <button onclick="abrirJogo('investimentos')">Simular Investimento</button>
    </section>
    <section class="apoio">
      <img src="lgbtqia/trans-banner.png" alt="Bandeira Trans" />
      <p>Respeito, inclusão e diversidade!</p>
    </section>
  </main>
  <footer>
    <a href="painel/login.html">Login</a> |
    <a href="painel/carteira.html">Carteira</a> |
    <a href="painel/denuncia.html">Denunciar</a> |
    <a href="painel/adm.html">Painel ADM</a>
  </footer>
  <script src="script.js"></script>
</body>
</html>
*/

// public/style.css
/*
body {
  background-color: #000;
  color: #fff;
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 0;
  padding: 0;
}

header {
  background: #111;
  padding: 20px;
  border-bottom: 2px solid red;
}

.sub {
  color: red;
  font-weight: bold;
}

.jogos button {
  margin: 10px;
  padding: 15px;
  font-size: 16px;
  background-color: red;
  border: none;
  color: white;
  cursor: pointer;
  border-radius: 8px;
  transition: 0.3s;
}

.jogos button:hover {
  background-color: #fff;
  color: red;
}

.apoio {
  margin-top: 30px;
}

.apoio img {
  max-width: 200px;
}
footer a {
  color: red;
  margin: 10px;
  text-decoration: none;
}
*/

// public/script.js
/*
function abrirJogo(tipo) {
  if (tipo === 'roleta') jogoRoleta();
  if (tipo === 'dados') jogoDados();
  if (tipo === 'cartas') jogoCartas();
  if (tipo === 'investimentos') jogoInvestimentos();
}

function jogoRoleta() {
  const resultado = Math.floor(Math.random() * 37);
  alert('Resultado da roleta: ' + resultado);
  const audio = new Audio('assets/sounds/roleta.mp3');
  audio.play();
}

function jogoDados() {
  const resultado = Math.floor(Math.random() * 6) + 1;
  alert('Você rolou um dado: ' + resultado);
  const audio = new Audio('assets/sounds/dado.mp3');
  audio.play();
}

function jogoCartas() {
  const cartas = ['Ás', 'Rei', 'Rainha', 'Valete', '10', '9'];
  const sorteada = cartas[Math.floor(Math.random() * cartas.length)];
  alert('Carta sorteada: ' + sorteada);
  const audio = new Audio('assets/sounds/cartas.mp3');
  audio.play();
}

function jogoInvestimentos() {
  const ganho = (Math.random() * 500 - 200).toFixed(2);
  const msg = ganho > 0 ? 'Lucro de R$' + ganho : 'Prejuízo de R$' + Math.abs(ganho);
  alert('Simulação concluída: ' + msg);
  const audio = new Audio('assets/sounds/investimento.mp3');
  audio.play();
}
*/

// painel/login.html
/*
<!DOCTYPE html>
<html lang="pt-BR">
<head><meta charset="UTF-8"><title>Login</title><link rel="stylesheet" href="../style.css"></head>
<body>
  <h2>Login</h2>
  <form>
    <input type="text" placeholder="Usuário" required><br>
    <input type="password" placeholder="Senha" required><br>
    <button type="submit">Entrar</button>
  </form>
</body>
</html>
*/

// painel/carteira.html
/*
<!DOCTYPE html>
<html lang="pt-BR">
<head><meta charset="UTF-8"><title>Carteira</title><link rel="stylesheet" href="../style.css"></head>
<body>
  <h2>Carteira Virtual</h2>
  <p>Saldo: R$ 0,00</p>
  <p>Apostas mínimas: R$30,00 (via Pix - CPF Itaú)</p>
  <p>Saques a partir de R$200,00</p>
</body>
</html>
*/

// painel/denuncia.html
/*
<!DOCTYPE html>
<html lang="pt-BR">
<head><meta charset="UTF-8"><title>Denúncia</title><link rel="stylesheet" href="../style.css"></head>
<body>
  <h2>Denunciar Infração</h2>
  <form>
    <textarea placeholder="Descreva a infração..." rows="6" cols="40"></textarea><br>
    <button type="submit">Enviar denúncia</button>
  </form>
</body>
</html>
*/

// painel/adm.html
/*
<!DOCTYPE html>
<html lang="pt-BR">
<head><meta charset="UTF-8"><title>Painel ADM</title><link rel="stylesheet" href="../style.css"></head>
<body>
  <h2>Painel Administrativo</h2>
  <ul>
    <li>Gerenciar usuários</li>
    <li>Ver apostas</li>
    <li>Aplicar banimentos</li>
    <li>Ver denúncias</li>
  </ul>
</body>
</html>
*/

// Estrutura esperada:
// - server.js
// - .env
// - public/
//     - index.html
//     - style.css
//     - script.js
//     - assets/sounds/roleta.mp3, dado.mp3, cartas.mp3, investimento.mp3
//     - lgbtqia/trans-banner.png
//     - painel/login.html, carteira.html, denuncia.html, adm.html
// - Banco PostgreSQL (configurado via Render com usuário, senha e banco definidos no .env)

