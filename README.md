<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=fb9aaf&height=120&section=header"/>

[![Typing SVG](https://readme-typing-svg.herokuapp.com/?color=fcb3b3&size=35&center=true&vCenter=true&width=1000&lines=print("Hello,world");Welcome+to+My+Portfolio!+:%29)](https://git.io/typing-svg)

# My name is Sara Alice, I'm 25 years old, and I'm a student of Analysis and Systems Development.

<div style="display: flex; justify-content: flex-end; align-items: center; height: 100vh;">
    <img src="https://cdn.discordapp.com/attachments/988904705117798463/1319669448373833838/Gifs_1.gif?ex=6766cd72&is=67657bf2&hm=952d144a525f9e5f42093051bce57b286e6e20d4255fc3d379034366c189e953&" 
         alt="GIF" 
         width="350" 
         height="350" />
</div>


# Learning:
-Introduction to Computer Science

-Python Programming Language

-Introduction to Database Usage and SQL

-Programming Logic

# Projects:
# Database and SQL
<details>
  <summary>Library Project</summary>
  <p>Library Database development project</p>
  
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
```
  <img src="https://github.com/saraaliice/saraaliice/blob/main/Projeto_Biblioteca.png" alt="Projeto Biblioteca" width="375" height="279"/>
</details>

<details>
  <summary>Logic Project</summary>
  <p>Database development project</p>
	
```SQL
*/

CREATE TABLE TBEstado (
    IDUF                  varchar(2)      NOT NULL,
    NomeEstado            varchar(50)     NOT NULL,
    PRIMARY KEY(IDUF)
);
--------------------------------------------------------------

--Cadastrar(inserir)dados em TBEstado
insert into TBEstado values
('SP','SÃO PAULO'),
('RJ','RIO DE JANEIRO'),
('PR','PARANA');
--------------------------------------------------------------
insert into TBEstado values
('MS','MATO GROSSO DO SUL');
---------------------------------------------------------------

--Código para ver os registros
Select*From TBEstado;

--Criar a tabela TBCidade
CREATE TABLE TBCidade 
(
	IDCidade	          INT          NOT NULL,
	NomeCidade	      varchar(50)  NOT NULL,
	CodUF	              varchar(2)   NOT NULL,
	PRIMARY KEY(IDCidade),
	FOREIGN KEY(CodUF) REFERENCES TBEstado(IDUF)
);
-------------------------------------------------------

--Cadastro de Cidades(Linguagem SQL)
Insert Into TBCidade VALUES
(01,'SÃO JOSÉ DO RIO PRETO','SP'),
(02,'CURITIBA','PR'),
(03,'BUZIOS','RJ');
--------------------------------------------------------
--Registro não cadastro 
Insert Into TBCidade VALUES
(04,'CAMPO GRANDE','MS');
--------------------------------------------------------
--Criar Tabela TBDepartamento
CREATE TABLE TBDepartamento 
(
	IDDepartamento	        INT            NOT NULL,
	NomeDepartamento	        varchar(50)    NOT NULL,
	OrcamentoDepartamento	    decimal(10, 2) NOT NULL,
	PRIMARY KEY(IDDepartamento)
);
---------------------------------------------------------
--Cadastrar 3 Departamentos
Insert Into TBDepartamento Values
(10,'Informatica',1500.50),
(20,'Financeiro',30500.75),
(30,'Recursos Humanos',50375.51);
----------------------------------------------------------
--Listar/Mostrar/Recuperar os Dados
Select *from TBDepartamento
----------------------------------------------------------
--Criando a Tabela TBFuncionario
CREATE TABLE TBFuncionario
 (
	IDFuncionario	         INT              NOT NULL,
	NomeFuncionario	     varchar(50)      NOT NULL,
	Telefone	             INT              NOT NULL,
	CPF	                 INT              NOT NULL,
	RG	                 varchar(12)      NOT NULL,
	Email	                 varchar(30)      NOT NULL,
	DataAdmissao	         date             NOT NULL,
	Endereco	             varchar(50)      NOT NULL,
	Numero	             INT              NOT NULL,
	Bairro	             varchar(50)      NOT NULL,
	CodDepartamento	     INT              NOT NULL,
	CodCidade	             INT              NOT NULL,
	PRIMARY KEY(IDFuncionario),
	FOREIGN KEY(CodDepartamento) REFERENCES TBDepartamento(IDDepartamento),
	FOREIGN KEY(CodCidade) REFERENCES TBCidade(IDCidade)
);
-----------------------------------------------------------------
--Criar a Tabela TBEquipamento
CREATE TABLE TBEquipamento
 (
	IDEquipamento	             INT             NOT NULL,
	NomeEquipamento	         varchar(50)     NOT NULL,
	DataCompra	             Date            NOT NULL,
	ValorEquipamento	         decimal(10,2)   NOT NULL,
	EstadoEquipamento	         varchar(300)    NOT NULL,
	RequisitosSegurança	     varchar(200)    NOT NULL,
	PRIMARY KEY(IDEquipamento)
);
-------------------------------------------------------------------
--Criar a Tabela TBProjeto
CREATE TABLE TBProjeto
 (
	IDProjeto           	   INT               NOT NULL,
	DescricaoProjeto	       varchar(200)      NOT NULL,
	DataInicioProjeto	       DateTime          NOT NULL,
	DataFimProjeto	       DateTime          NOT NULL,
	CustoGeralProjeto	       decimal(10, 2)    NOT NULL,
	CodDepartamento	       INT               NOT NULL,
	FOREIGN KEY(CodDepartamento) REFERENCES TBDepartamento(IDDepartamento),
	PRIMARY KEY(IDProjeto)
);
----------------------------------------------------------------------
--Criar a Tabela TBFuncionarioProjeto
CREATE TABLE TBFuncionarioProjeto 
(
	CodFuncionario	             INT               NOT NULL,
	CodEquipamento	             INT               NOT NULL,
	CodProjeto	                 INT               NOT NULL,
	Data	                         DateTime          NOT NULL,
	DataInicio	                 date              NOT NULL,
	DataFim	                     date              NOT NULL,
	Custo	                         decimal(10,2)     NOT NULL,
	FOREIGN KEY(CodFuncionario) REFERENCES TBFuncionario(IDFuncionario),
	FOREIGN KEY(CodProjeto) REFERENCES TBProjeto(IDProjeto),
	FOREIGN KEY(CodEquipamento) REFERENCES TBEquipamento(IDEquipamento),
	PRIMARY KEY(CodFuncionario,CodEquipamento,CodProjeto,Data)
);
````
  <img src="https://github.com/saraaliice/saraaliice/blob/main/Projeto_L%C3%B3gito.png" alt="Projeto Lógico" width="375" height="279"/>
</details>

<details>
  <summary>Teste Take Rate</summary>
  <p>Take Rate project for a vacancy</p>  
  <img src="https://github.com/saraaliice/saraaliice/blob/main/Imagem_teste.jpeg" alt="Teste Take Rate" width="375" height="279"/>
</details>

<details>
  <summary>Customer Database</summary>
  <p>Database Project</p> 
  <img src="https://github.com/saraaliice/saraaliice/blob/main/vagal_test.jpeg" alt="Banco de Dados Clientes" width="375" height="279"/>
</details>

 # Java

<details>
  <summary>Project for the Object-Oriented Programming Language course </summary>
  
  <details>
    <summary>Passageiro</summary>
    <p>Passenger class constructor</p> 
   
   ```Java
    public class Passageiro {
        private String nome;
        private String numeroDocumento;
        private String numeroTelefone;

        public Passageiro(String nome, String numeroDocumento, String numeroTelefone) {
            this.nome = nome;
            this.numeroDocumento = numeroDocumento;
            this.numeroTelefone = numeroTelefone;
        }
````
   </details>

   <details>
      <summary>Voo</summary>
      <p>Flight class constructor</p>

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
      <summary>Main Program</summary>
      <p>Main Program class constructor</p> 
    
  ````Java
      public class ProgramaPrincipal {
          public static void main(String[] args) {
              Voo voo1 = new Voo(101, "Londrina", "São Paulo", "2023-11-15 10:00", 150);

              if (voo1.reservarAssento()) {
                  System.out.println("Assento reservado com sucesso!");
              } else {
                  System.out.println("Não há assentos disponíveis.");
              }


              voo1.exibirInformacoes();
          }
      }
`````
   </details>
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
