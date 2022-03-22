# Script2022

Windows - Instalar Node JS v16.14.0
entrar na pasta pelo explorer
cmd ->  $code .  
abrir terminal
$ npm init -y
$ npm install express ou $ npm i express
OBS.:Nunca levar a pasta do node_modules, e qdo for abrir denono é usar $ npm install
pasta Servidor / pasta src / criar arquivo index.JS
terminal $ node ./src  (chama pacote)

para  rodar a porta
index.JS
const express = require("express");
const app = express();
const PORT = 3001;
app.listen (PORT,() =>{console.log(`Rodando ${PORT}`)});
e depois $node ./src

$ npm i nodemon -D
servidor/criar arquivo .gitignore  na pasta node_modules

servidor/ criar arquivo .env   (ambiente, é um arquivo de configuração , sendo um arquivo de texto)
PORT=3100

$npm i dotenv  (permite a leitura do qrquivo .env)

executar o arquivo
$npx nodemon ./src

entre no package.json (base do projeto node)
e altere para
 "scripts": {
    "start": "node ./src", 
    "dev": "npx nodemon ./src"
  },

lista de comandos
1)$npm init -y
2)$npm i express
3)$npm i nodemon -D
4)$npm i dotenv
5)$npx nodemon ./src
6)$npm run start
7)$npm run dev - roda com o nodemon / $npm run start - roda com o Node

criar uma pasta em src chamada exemplos e criar um arquivo index.js
importação
require("express") -> não é seu
require("./exemplos") -> seu




1° modelo index.js//DEFINIR ROTA RAIZ
//app.get("/", (reg, res) => {
    //res.send("oi");
//});
//app.get("/cadastro/:nome/:idade", (reg, res) => {
 //   const { nome, idade } = reg.params;
 //   res.send(nome + idade);
//});
//http://localhost:3001/cadastro/roberta/10


index.js (importa e exporta somente)
const Matematica = require("./a");

aula 21/03
src/exemplos2/index.js
//importar
const Matematica = require("./a");
const pow = require("./b");
//exportar recurso da biblioteca 
const express = require("express");
const { Router } = require("express");
// criando rota - cada uma é uma requisição HTTP (Get, Post, Delete,)
const router = express.Router()
//localhost:3100/api/um/pow = /pow
//localhost:3100/api/dois/mes = /mes
//router.get(exports, função callback)
router.get("/pow",pow)
router.get("/mes")
// desestruturar  criando 2 variaveis somar e subtrair (tira da estrutura de JSON)
//Método é uma função dentro de uma classe para trocar a ordem  const {var,var} = new Matematica()(produz um JSON) 
const{somar,subtrair} = new Matematica();
router.get("/sum",somar);
router.get("/diff",subtrair);
// precisa exportar module ao final das rotas
module.exports = router;


src/exemplo2/index.js
const {mes,dia} = require("./c");
const router = require("express").Router();
//como são constantes e não função teremos que colocar no lugar da função (req,res)=>res.send(mes)
router.get("/mes,(req,res)=>res.send(mes)); ")
router.get("/dia,(req,res)=>res.send(dia)); ")
module.exports = router;
//qdo arquivo exporta algo recebe outro nome:módulo
//qdo a pasta tem index.js que exporta recebe o nome:package

src/index.js
