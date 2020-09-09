# Anotações:

Docs: https://angular.io/docs
	  https://update.angular.io

01 - Ao criar um módulo, precisa importar no AppModule. Caso crie no AngularCli 
    o import é automático.

02 - Caso queira usar algum componente dentro de um módulo qualquer 
	no AppModule, não esquecer de no exports colocar a classe.
	
03 - Sempre que fizer alteração nas classes de módulos e configurações,
	parar e subir o server.

04 - Bindings: 
		() -> Template para o Componente 
		[] -> Componente para o Template
		[()] -> Ambos 

05 - Testes:
 	 Unitário   = Jasmine (jasmine.github.io)	e o Karma
	 Integração = Protractor 

06 - Diretivas:
	*ngIf -> Quando utilizar uma árvore DOM muito grande, caso contrário 
			 usar o hidden para melhor performance.
	*ngFor ->  Exemplo: *ngFor="let curso of listaCursos; let i=index" 
	           a palavra reservada index retorna o index (rs rs)
	[ngSwitch] -> *ngSwitchCase e *ngSwitchDefault
	[ngClass] -> "{'propriedade' : valor, 'propriedade2': (valorCondicional)}"
	[ngStyle] -> "{'propriedade' : valor, 'propriedade2': (valorCondicional)}"

08 - Operador Elvis é muito bom pois não precisa fazer operações ternárias.
    Reduz a quantidade de código e aumenta a legibilidade.

09 - Ao passar parâmetros pro < ngContent > sempre atribuir o seletor que será uma 
	classe. O que n tiver a classe o ngContent simplesmente ignora.

10 - Pipes ( | )
	 https://angular.io/api - Commom
	 Tem os pipes disponíveis pelo Angular

13 - Nunca usar Pipes para realizar OrderBy ou Filtros.

# Configurações Iniciais de Projeto

01 - Definindo LOCALE para a aplicação. No AppModule adicionar:
	 import localePt from '@angular/common/locales/pt'; - O import necessário
	 registerLocaleData(localePt, 'pt'); - Antes da anotação @NgModule
	 {provide: LOCALE_ID, useValue: 'pt'} - Dentro dos providers

02 - Adicionar no AppModule o tipo de formulário a ser usado:
		Template: FormsModule
		Component: ReactiveFormsModule
	Por via das dúvidas add os 2 que da tudo certo (rs rs)

# CLI

ng new [nomeProjeto]
cd [nomeProjeto]
ng serve

ng g(enerate) c(omponent) [nome]
ng g(enerate) m(odule) [nome]
ng g(enerate) s(ervice) [nome]
ng g(enerate) d(irective) [nome]
ng g(enerate) p(ipe) [nome]
ng g(enerate) c(lass) [nome]
ng g(enerate) e(num) [nome]
ng g(enerate) i(nterface) [nome]

ng lint
ng test
ng e2e 

ng build 
ng build --prod (mimificado)

# Diretórios

e2e          - Configurações de testes
node_modules - Bibliotecas
environment  - Config de deploy/build

# Dependências

01 - Bootstrap
	1º) npm install --save bootstrap
	2º) No arquivo angular.json em styles add: "node_modules/bootstrap/dist/css/bootstrap.min.css"

02 - NGX - Bootstrap
	1º) npm install ngx-bootstrap --save

03 - MaterializeCSS
	 1º) npm install materialize-css --save
	 2º) npm install angular2-materialize --save
	 3º) No arquivo angular.json em styles add: "node_modules/materialize-css/dist/css/materialize.css"
	 4º) No index.html adicionar os icons: <link href="http://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">