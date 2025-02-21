# Desafio Final VTEX Hiring Coders 2021 - Grupo 03

## Montar uma loja para o patrocinador Corebiz, fazendo comunicação da API do VTEX IO com a API da AWS
<br>
Desenvolvido como parte do treinamento VTEX - Hiring Coders 2021.
<br>
<br>
<img src='https://hiringcoders-app.gama.academy/images/logo-sm.png' alt="Hiring Coders" width="auto" height="50" />  <img src='https://vtex.com/wp-content/themes/VTEXTheme/v2/images/base/vtex.svg' alt="VTEX" width="auto" height="50">  <img src='./assets/logo-corebiz-preto.png' alt="Corebiz" width="auto" height="50">  <img src='https://assets.website-files.com/5ff79f3ebebf6b12f6b7747f/5ffe04fc6284b7e90070d985_logo-gama-academy-p-500.png' alt="Gama Academy" width="auto" height="50">


***
## Regras do desafio

O desafio consistia em montar uma loja usando a temática da Corebiz e os pontos abaixo eram fundamentais no projeto:

- Manutenção do estilo do site original, trazendo identidade da Corebiz para a loja.<img src='./assets/images/tick.png' alt="Feito!" width="auto" height="30"/>
- Destaque para a missão e os valores da empresa.<img src='./assets/images/tick.png' alt="Feito!" width="auto" height="30"/>
- Integração com a API da AWS (também desenvolvida pelo grupo), gravando informações sobre os leads numa tabela DynamoDB e fazendo uso da função Lambda da AWS.<img src='./assets/images/tick.png' alt="Feito!" width="auto" height="30"/>
- Construção de uma API VTEX para listar os produtos cadastrados na nossa loja e que poderia ser utilizada por uma aplicação externa ao VTEX IO.<img src='./assets/images/tick.png' alt="Feito!" width="auto" height="30"/>
- Apresentação da relação de leads cadastrados na AWS e que se tornaram clientes efetivos (comunicação entre API VTEX e API AWS).<img src='./assets/images/tick.png' alt="Feito!" width="auto" height="30"/>
- Inclusão da mesma relação de leads no item acima no Admin da Loja (opcional)<img src='./assets/images/tick.png' alt="Feito!" width="auto" height="30"/>

A aplicação resultante ficou disponível na nuvem da VTEX, na loja HIRINGCODERS202103 (com acesso restrito aos usuários do VTEX IO).

***
## Grupo

  - [Alcides Novais da Silva](https://github.com/Alcidesns)
  - [Antonio Augusto Fonseca](https://github.com/anfonseca44)
  - [Carlos Frederico Missick](https://github.com/CarlosMissick)
  - [Djan Magno](https://github.com/djanmagno)
  - [Douglas Figueiredo](https://github.com/douglasfigueiredo)
  - [Edney Moita](https://github.com/edneymoita)
  - [João Pedro M. Póvoa](https://github.com/JPeeMP)
  - [Pedro Mascarenhas](https://github.com/pedro-drosa)
  - [Raniere Lourenço](https://github.com/raniereslourenco)
  - [Renan de Aguiar Modesto](https://github.com/rednand)

***
## Endereço da Loja

[Corebiz Store](https://corebiz--hiringcoders202103.myvtex.com/) (acesso restrito)

***
## Desenvolvido em

<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/>  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/>  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="typescript" width="40" height="40"/>  <img src="https://upload.wikimedia.org/wikipedia/commons/d/d9/Node.js_logo.svg" alt="nodejs" width="40" height="40"/>  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" width="40" height="40"/>  <img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" alt="aws" width="40" height="40"/>

***

## Dependências

Não há dependências externas ao VTEX IO

***

## Rotas AWS

POST https://n3me17g086.execute-api.us-east-2.amazonaws.com/create

DELETE https://n3me17g086.execute-api.us-east-2.amazonaws.com/delete/{email}

GET https://n3me17g086.execute-api.us-east-2.amazonaws.com/list

GET https://n3me17g086.execute-api.us-east-2.amazonaws.com/list/{email}

PUT https://n3me17g086.execute-api.us-east-2.amazonaws.com/update

***

## Loja montada

Página inicial da loja, com banner para captação de leads e listagem de serviços disponibilizados na Corebiz Store.
<br>
<br>
<img src='./assets/screenshots/home1.png'/>
<br>
<img src='./assets/screenshots/home2.png'/>
<br>
<img src='./assets/screenshots/home3.png'/>
<br>
<br>
Página de produto, apresentando o produto escolhido e todos os detalhes.
<br>
<br>
<img src='./assets/screenshots/produto.png'/>
<br>
<br>
Modal para captação de dados de clientes (componente React integrado com a API da AWS)
<br>
<br>
<img src='./assets/screenshots/leads.png'/>
<br>
<br>
Página sobre a patrocinadora Corebiz, dando destaque a missão e valores da empresa.
<br>
<br>
<img src='./assets/screenshots/sobre1.png'/>
<br>
<img src='./assets/screenshots/sobre2.png'/>
<br>
<br>
Página apresentando os prospectos que estão cadastrados na AWS e que viraram clientes efetivos.
<br>
<br>
<img src='./assets/screenshots/clientes.png'/>
<br>
<br>
Carrinho de compras, apresentando os produtos selecionados
<br>
<br>
<img src='./assets/screenshots/carrinho.png'/>
<br>
<br>
Admin da loja com a inclusão das informações dos prospectos e clientes cadastrados na AWS (parte opcional do projeto)
<br>
<br>
<img src='./assets/screenshots/admin.png'/>

***

#### Observação

Para esta implementação nosso grupo tentou duas abordagens para tentar solucionar a atualização dos dados na AWS:
- Utilizar o master data da VTEX e tentar utilizar os serviços de triggers disponíveis na plataforma a fim de criar um evento no momento da compra de um cliente e criar uma rota http put para alterar a marcação de prospecto para cliente. Esta solução não foi possível, pois a versão do masterdata na loja disponibilizada não dispunha de tal função.
- Criar um evento para ouvir todas as vezes que os clientes efetuassem uma compra e com isso poderíamos obter o orderId e conseqüentemente obter o email do usuário para alteração da marcação de cliente.
