# Inicializando uma Aplicação Node

comando: npm init
npm init //inicialize sua aplicação Node

Você vai ver que nosso arquivo package.json foi criado e contém
main (entry point) para apontar para o nosso index.js:
...
"main": "index.js",
...

Agora que temos o package.json podemos digitar o comando node index.js
para iniciar nossa app Node! Mas isso vai gerar um erro, por que ainda não criamos o arquivo index.js que vamos usar para inicializar nosso app Node. Então agora, vamos resolver isso!

# Criando uma Simples Aplicação Node

Agora vamos criar o nosso arquivo index.js e tudo que precisamos é do comando console.log() para imprimir alguma informação na saída do nosso console quando a aplicação iniciar.
Criamos uma pasta src e dentro dela um arquivo index.js

# Executando uma Aplicação Node

Para iniciar uma Aplicação Node, você só precisa digitar:
node src/index.js

podemos criar um script para facilitar a execução no arquivo package.json:

"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node src/index.js"
  },

# Reiniciando uma Aplicação Node Quando o Arquivo Mudar:
Por padrão, o comando node index.js vai iniciar a sua aplicação, mas não vai reiniciar quando você fizer alguma atualização no arquivo. 
Temos um pacote npm que vai monitorar e reiniciar quando mudanças forem identificadas. Esse pacote é o nodemon e para intalar basta seguir o comando a seguir.

npm install nodemon --save-dev

Então quando qualquer alteração for identificada o servidor vai reiniciar como na mensagem a cima. Daqui em diante, por uma questão de praticidade, vamos usar o nodemon quando precisarmos executar a palicação..

Podemos usar o nodemon para iniciar um script do Node.

nodemon index.js

# Instalando Packages

O arquivo package.json é onde configuramos o nome da aplicação e qual arquivo usar na inicialização. Vai ser nele também que vamos definir os packages que precisamos.

Existem, basicamente, duas maneiras de adicionar packages ao nosso projeto:

    escrevendo direto no arquivo package.json
    instalando via linha de comando

Adicionanl Packages via Linha de Comando
Esse é o comando para instalar o Express e salvar a modificação no package.json:
npm install express --save
Você vai reparar que esse comando baixa o package e instala ele em uma nova pasta chamada node_modules. É aqui que são instalados os packages em projetos Node e esse comando instala apenas o package que foi chamado especificamente (Express nesse caso).

# Recapitulando

Agora, quando quisermos começar um novo projeto Node. Precisamos digitar apenas dois comando na pasta do projeto.

Com isso temos tudo que precisamos para iniciar nossa aplicação!

 npm init
  Preencher os atributos necessários para criar o package.json
 npm install express --save

 Agora vamos em frente e mergulhar em como usar o Express para configurar as bases do nosso Full-Stack.

 # Criando um servidor Usando Express

 Primeiro precisamos adicionar o Express no projeto. Vamos usar a linha de comando para instalar e salvar ele em nosso package.json.

npm install express --save

Criamos uma arquivo server.js dentro da pasta src:
src/server.js

Então, vamos atualizar o server.js para usar o Express. Começamos instanciando o Express e usando essa instância, definimos uma rota e enviamos o index.html. Então ficamos "escutando" uma porta para responder as requisições do browser.

Podemos criar um script para facilitar a execução no arquivo package.json:

// vamos começar, carregando o express e criando a app
const app = require('express')()
const path = require('path')

// então, criamos uma rota para '/'
app.get('/', (req, res) => {
  // aqui precisamos enviar o index.html para o cliente
  res.sendFile(path.join(__dirname + '/index.html'))
})

// no fim, iniciamos o serviço na porta 8001
app.listen(8001)
console.log('8001 é a porta mágica!')

"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node src/index.js",
    "start nodemon": "nodemon src/server.js"
  },



# Roteamento de Aplicações Node

Para adicionar mais páginas ao nosso site, vamos precisar de mais rotas. Isso pode ser feito usando uma feature do Express, o Express Router. Esse tende a ser um capítulo extenso do livro já que o roteamento é uma das maiores partes da nossa aplicação daqui em diante.

Esse capítulo será sobre como roteamos websites do básico ao avançado e como vamos desenvolver nossa API RESTful que vai ser consumida pela nossa Aplicação React no frontend. É muito exitante olhar lá pra frente e já começar a enxergar como isso tudo vai se encaixar! Mas vamos dar um passo de cada vez e entender como funciona o roteamente de aplicações web.



//http://stack.desenvolvedor.expert/comecando-com-node/executando-uma-app-node.html