<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=fb9aaf&height=120&section=header"/>

[![Typing SVG](https://readme-typing-svg.herokuapp.com/?color=fcb3b3&size=35&center=true&vCenter=true&width=1000&lines=print("Hello,world");Bem+Vindos+ao+Meu+Portfólio!+:%29)](https://git.io/typing-svg)

# Meu nome é Sara Alice, Tenho 23 anos e Sou estudante de Análise e Desenvolvimento de Sistemas.

<img src="https://cdn.discordapp.com/attachments/988904705117798463/1172724591781761075/Gifs.gif?ex=65615be2&is=654ee6e2&hm=a853892e22fd54ea9ef0f29fc9f3a54e8665d3b64ae4b28493fc707f10ad6ef5&" alt="GIF" width="350" height="350" style="float: right;"/>

# Aprendizado:
- Introdução à Ciência da Computação
- Linguagem de Programação Python
- Introdução ao uso de Banco de Dados e SQL
- Lógica de Programação

# Projetos:
# Banco de dados e SQL:
<details>
  <summary>Projeto Biblioteca</summary>
  <p>Projeto de desenvolvimento de Banco de dados de uma Biblioteca</p>
  
  ```SQL 
  --Criar tabela TBObra
 CREATE TABLE TBObra
 (
	CodObra	        INT NOT NULL,
	Titulo	        varchar(50) NOT NULL,
	AutorPrincipal	varchar(50) NOT NULL,
	SituacaoObra	    INT NOT NULL,
	TipoObra	        INT NOT NULL,
	CodEditora	    INT NOT NULL,
	FOREIGN KEY(CodEditora) REFERENCES TBEditora(CodEditora),
	PRIMARY KEY(CodObra)
);
---------------------------------------------
--Criar Tabela TBEditora
CREATE TABLE TBEditora 
(
	CodEditora	INT NOT NULL,
	NomeEditora	varchar(50) NOT NULL,
	Cidade	varchar(50) NOT NULL,
	PRIMARY KEY(CodEditora)
);
---------------------------------------------
--Criar tabela TBUsuario
CREATE TABLE TBUsuario 
(
	CodUsuario	INT NOT NULL,
	NomeUsuario	varchar(50) NOT NULL,
	Logradouro	varchar(50) NOT NULL,
	Numero	INT NOT NULL,
	Complemento	varchar(20) NOT NULL,
	Bairro	varchar(30) NOT NULL,
	Cidade	varchar(30) NOT NULL,
	UF	varchar(2) NOT NULL,
	CEP	varchar(10) NOT NULL,
	Telefone	varchar(15) NOT NULL,
	CPF	varchar(20) NOT NULL,
	PRIMARY KEY(CodUsuario)
);
---------------------------------------------
--Criar Tabela TBEmprestimo
CREATE TABLE TBEmprestimo 
(
	CodEmprestimo	INT NOT NULL,
	CodObra	INT NOT NULL,
	CodUsuario	INT NOT NULL,
	DataEmprestimo	Data NOT NULL,
	HorarioEmprestimo	Time NOT NULL,
	DataPrevistaRetorno	Data NOT NULL,
	MatriculaFuncionario	INT NOT NULL,
	FOREIGN KEY(CodObra) REFERENCES TBObra(CodObra),
	FOREIGN KEY(CodUsuario) REFERENCES TBUsuario(CodUsuario),
	FOREIGN KEY(MatriculaFuncionario) REFERENCES TBFuncionario(Matricula),
	PRIMARY KEY(CodEmprestimo)
);
---------------------------------------------
--Criar Tabela TBDevolucao
CREATE TABLE TBDevolucao 
(
	CodEmprestimo	INT NOT NULL,
	DataDevolucao	Data NOT NULL,
	HorarioDevolucao	Time NOT NULL,
	MatriculaFuncionario	INT NOT NULL,
	PRIMARY KEY(CodEmprestimo),
	FOREIGN KEY(MatriculaFuncionario) REFERENCES TBFuncionario(Matricula),
	FOREIGN KEY(CodEmprestimo) REFERENCES TBEmprestimo(CodEmprestimo)
);
----------------------------------------------
--Criar Tabela TBFuncionario
CREATE TABLE TBFuncionario (
	Matricula	INT NOT NULL,
	NomeFuncionario	varchar(50) NOT NULL,
	CodDepartamento	INT NOT NULL,
	FOREIGN KEY(CodDepartamento) REFERENCES TBDepartamento(CodDepartamento),
	PRIMARY KEY(Matricula)
);
----------------------------------------------
--Criar Tabela TBDepartamento
CREATE TABLE TBDepartamento
(
	CodDepartamento	INT NOT NULL,
	NomeDepartamento	varchar(50) NOT NULL,
	MatriculaChefe	INT NOT NULL,
	PRIMARY KEY(CodDepartamento)
);
---------------------------------------------
--Criar Tabela TBReserva
CREATE TABLE TBReserva 
(
	CodReserva	INT NOT NULL,
	CodUsuario	INT NOT NULL,
	CodObra	INT NOT NULL,
	DataReserva	Data NOT NULL,
	HorarioReserva	Time NOT NULL,
	DataRetirada	Data NOT NULL,
	PRIMARY KEY(CodReserva),
	FOREIGN KEY(CodObra) REFERENCES TBObra(CodObra),
	FOREIGN KEY(CodUsuario) REFERENCES TBUsuario(CodUsuario)
);
  <img src="https://github.com/saraaliice/saraaliice/blob/main/Projeto_Biblioteca.png" alt="Projeto Biblioteca" width="375" height="279"/>
````
</details>

<details>
  <summary>Projeto Lógico</summary>
  <p>Projeto de desenvolvimento de Banco de dados</p>  
  <img src="https://github.com/saraaliice/saraaliice/blob/main/Projeto_L%C3%B3gito.png" alt="Projeto Lógico" width="375" height="279"/>
</details>

<details>
  <summary>Teste Take Rate</summary>
  <p>Projeto de Take Rate para uma vaga</p>  
  <img src="https://github.com/saraaliice/saraaliice/blob/main/Imagem_teste.jpeg" alt="Teste Take Rate" width="375" height="279"/>
</details>

<details>
  <summary>Banco de Dados Clientes</summary>
  <p>Projeto de Banco de Dados</p> 
  <img src="https://github.com/saraaliice/saraaliice/blob/main/vagal_test.jpeg" alt="Banco de Dados Clientes" width="375" height="279"/>
</details>

 # Java:

<details>
  <summary>Projeto da disciplina de Linguagem de Programação Orientado a Objetos </summary>
  
  <details>
    <summary>Projeto Passageiro</summary>
    <p>Construtor de classe Passageiro</p> 
   
   ```Java
    public class Passageiro {
        private String nome;
        private String numeroDocumento;
        private String numeroTelefone;

        // Construtor
        public Passageiro(String nome, String numeroDocumento, String numeroTelefone) {
            this.nome = nome;
            this.numeroDocumento = numeroDocumento;
            this.numeroTelefone = numeroTelefone;
        }
````
   </details>

   <details>
      <summary>Projeto Voo</summary>
      <p>Construtor de classe Voo</p>

   ```Java
      public class Voo {
          private int numeroVoo;
          private String origem;
          private String destino;
          private String dataPartida;
          private String horaPartida;
          private int totalAssentos;
          private int assentosDisponiveis;

          public Voo(int numeroVoo, String origem, String destino, String dataPartida, String horaPartida, int totalAssentos) {
              this.numeroVoo = numeroVoo;
              this.origem = origem;
              this.destino = destino;
              this.dataPartida = dataPartida;
              this.horaPartida = horaPartida;
              this.totalAssentos = totalAssentos;
              this.assentosDisponiveis = totalAssentos;
          }

          public boolean reservarAssento() {
              if (assentosDisponiveis > 0) {
                  assentosDisponiveis--;
                  return true;
              } else {
                  return false;
              }
          }

          public void exibirInformacoes() {
              System.out.println("Numero do Voo:" + numeroVoo);
              System.out.println("Origem: " + origem);
              System.out.println("Destino: " + destino);
              System.out.println("Data: " + dataPartida);
              System.out.println("HoraPartida:" + horaPartida);
              System.out.println("Total de Assentos: " + totalAssentos);
              System.out.println("Assentos Disponiveis: " + assentosDisponiveis);
          }
      }
````
   </details>

   <details>
      <summary>Projeto Programa Principal</summary>
      <p>Construtor de classe Programa Principal</p> 
    
  ````Java
      public class ProgramaPrincipal {
          public static void main(String[] args) {
              Voo voo1 = new Voo(101, "Londrina", "São Paulo", "2023-11-15 10:00", 150);

              // Realizar uma reserva de assento
              if (voo1.reservarAssento()) {
                  System.out.println("Assento reservado com sucesso!");
              } else {
                  System.out.println("Não há assentos disponíveis.");
              }

              // Exibir informações do voo
              voo1.exibirInformacoes();
          }
      }
`````
   </details>
</details>

# JavaScript: 
<details>
  <summary>Gerador de Senhas aleatórias</summary>
 
```javascript
let comprimentoInput = document.getElementById("comprimento");
let incluirNumeros = document.getElementById("incluirNumeros");
let incluirLetrasMaiusculas = document.getElementById("incluirLetrasMaiusculas");
let incluirLetrasMinusculas = document.getElementById("incluirLetrasMinusculas");
let incluirSimbolos = document.getElementById("incluirSimbolos");
let botaoGerar = document.getElementById("botaoGerar");
let exibicaoSenha = document.getElementById("exibicaoSenha");

botaoGerar.addEventListener("click", gerarSenha);

function gerarSenha() {
    let comprimento = comprimentoInput.value;
    let numeros = "123456789";
    let letrasMaiusculas = "ABCDEFGHIJKLMNOPQRSTUVWXZ";
    let letrasMinusculas = "abcdefghijklmnopqrstuvwxz";
    let simbolos = "!@#$%?*;+_^~";

    let caracteres = "";

    if (incluirNumeros.checked) caracteres += numeros;
    if (incluirLetrasMaiusculas.checked) caracteres += letrasMaiusculas;
    if (incluirLetrasMinusculas.checked) caracteres += letrasMinusculas;
    if (incluirSimbolos.checked) caracteres += simbolos;

    let senha = "";

    for (let i = 0; i < comprimento; i++) {
        const indiceAleatorio = Math.floor(Math.random() * caracteres.length);
        senha += caracteres[indiceAleatorio];
    }

    exibicaoSenha.textContent = senha;
}

```
   </details>
</details>

# HTML, CSS e JavaScript:

<details>
  <summary>Site Simples</summary>
  
  <!-- Conteúdo do Site Simples -->

</details>

# Conhecimentos 
.
    <p align="center"> Linguagens:</p>
    <p align="center">
     <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/></a> 
      </a> 
      <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/>
      </a> 
      <a href="https://www.python.org" target="_blank" rel="noreferrer">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/>
      </a>  
      <a href="https://www.java.com/pt-BR/" target="_blank" rel="noreferrer">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/>
      </a> 
    </p>
    <br>
 <p align="center">Banco de Dados:
  </p>
  <p align="center"> 
    <a href="https://www.brmodeloweb.com/lang/pt-br/index.html" target="_blank" rel="noreferrer"> <img src="https://cdn.discordapp.com/attachments/988904705117798463/1172723085904990288/1ea2a29278d9b611422b2e3cc7bd2e76.png?ex=65615a7b&is=654ee57b&hm=a86896aef0cce661165c724b121dd844cb7c34b4109a801d4afaae008a4bbd05&"<alt="brmodelo" width="40" height="40"/></a>
    <a href="https://sqlitebrowser.org/" target="_blank" rel="noreferrer"> <img src="https://cdn.discordapp.com/attachments/988904705117798463/1172723304575025303/db-browser-for-sqlite-logo.png?ex=65615aaf&is=654ee5af&hm=45b468a2830b450df05223f3ae8fd1176b9593e2059ba29bc66cf66b57ae3cf9&" <alt="db browser" width="40" height="40"/></a> 
    <a href="https://www.microsoft.com/en-us/sql-server" target="_blank" rel="noreferrer"> <img src="https://www.svgrepo.com/show/303229/microsoft-sql-server-logo.svg" alt="mssql" width="40" height="40"/></a> 
    <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/></a>
  </p>
  <br>
   <p align="center">Aplicações WEB:
  </p>
  <p align="center">
    <a href="https://br.wordpress.org" target="_blank" rel="noreferrer"> <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/wordpress/wordpress-plain.svg" alt="wordpress" width="40" height="40"/></a>
    <a href="https://www.canva.com" target="_blank" rel="noreferrer"> <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/canva/canva-original.svg" alt="canva" width="40" height="40"/></a>
    <a href="https://trello.com/pt-BR" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/trello/trello-ar21.svg" alt="trello" width="40" height="40"/></a> 
    <a href="https://git-scm.com/" target="_blank" rel="noreferrer"> <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-original.svg" alt="git" width="40" height="40"/> 
    <a href="https://www.notion.so/" target="_blank" rel="noreferrer"> <img src="https://upload.vectorlogo.zone/logos/notionso/images/d9327abc-21be-4790-8a5f-752d9c12e33d.svg" alt="notion" width="40" height="40"/></a> 
  </p>
  <br>
  <p align="center">Aplicações:
  </p>
  <p align="center">
   <a href="https://www.docker.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="docker" width="40" height="40"/></a> 
  <a href="https://nodejs.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" width="40" height="40"/></a> 
  <a href="https://www.jetbrains.com/pt-br/pycharm/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/pycharm/pycharm-original.svg" alt="pycharm" width="40" height="40"/></a> 
  <a href="https://powerbi.microsoft.com/pt-br/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/microsoft_powerbi/microsoft_powerbi-icon.svg" alt="powerbi" width="40" height="40"/></a> 
  <a href="https://code.visualstudio.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/visualstudio_code/visualstudio_code-icon.svg" alt="vscode" width="40" height="40"/></a> 
  <a href="https://visualstudio.microsoft.com/pt-br/" target="_blank" rel="noreferrer"> <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/visualstudio/visualstudio-plain.svg" alt="vs" width="40" height="40"/></a> 
  </p>
</details>

# Contatos

   <div align="center"> 
<a href="https://instagram.com/saraalicem" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white"</a>
<a href = "mailto:saraalice13@gmail.com"> <img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
<a href="https://www.linkedin.com/in/sara-alice/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" style="border-radius: 30px" target="_blank"></a> 
 </div>
    </p>   
</details>  

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=fb9aaf&height=120&section=footer"/>
