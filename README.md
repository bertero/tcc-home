# SISTEMA DE PAGAMENTOS UTILIZANDO CÓDIGO QR

## PROPOSTA
O projeto consiste em um sistema de pagamentos que vem ao mercado para concorrer com o modelo padrão de adquirente e bandeira. Dentro de um contexto brasileiro, em que a economia informal representa cerca de 16% do PIB (dado de 2016), o trabalho visa trazer inclusão socioeconômica, uma vez que fornece a possibilidade da realização de pagamentos sem a necessidade de um equipamento além do próprio telefone celular.
O pagamento funciona conforme ilustrado pela Figura 1, o pagador coloca o valor a ser pago no seu aplicativo, gera um código QR, o recebedor escaneia, confirma e fim!

<div style="text-align:center">
  <img width="400px" src ="/images/pagamento.png" />
  <p>Figura 1 - Sequência lógica de pagamento.</p>
</div>

## ESPECIFICAÇÃO ARQUITETURAL
Para que fosse possível nortear a implementação do sistema, realizou-se a abstração de um modelo de referência, que resultou na segmentação do projeto em visão de negócios, engenharia e segurança, que cumprem, respectivamente, as seguintes etapas de engenharia de software: requisitos, funcionalidades e implementação.
A estrutura do sistema está ilustrada na Figura 2, com um servidor central, que se comunica com o banco de dados e os aplicativos de pagamento e recebimento.

<div style="text-align:center">
  <img width="300px" src ="/images/arquitetura.png" />
  <p>Figura 2 - Estrutura alto nível do sistema.</p>
</div>

## ESPECIFICAÇÃO DE SEGURANÇA
O aspecto de principal valor gerado no projeto é a segurança, que é também o requisito mais crítico do sistema. A partir deste fato, foram definidos os principais objetivos que devem ser cumpridos: confidencialidade e integridade dos dados transacionados entre as partes do sistema e autenticidade do usuário durante um pagamento. Para se cumprir o primeiro, aplicou-se uma camada extra de criptografia além do TLS do HTTPS, assim como representa a Figura 3. Para o segundo, foi implementada uma assinatura digital que utiliza um algoritmo de criptografia assimétrico.

<div style="text-align:center">
  <img src ="/images/seguranca.png" />
  <p>Figura 3 - Fluxo de criptografia dos dados no sentido cliente-servidor (I) e servidor-cliente (II).</p>
</div>

## IMPLEMENTAÇÃO
Como forma de cumprir outro importante requisito do sistema, o de disponibilidade, optou-se por seguir uma estrutura serverless, em que há o encapsulamento de funções, impedindo que problemas isolados derrubem o sistema todo. Por fim, utilizando recursos da Amazon AWS, o sistema foi implementado conforme a Figura 4.
Os usuários tem acesso a três possíveis interfaces com o produto: aplicativos de pagamento e recebimento (Figura 5) e painel de controle (Figura 6).

<div style="text-align:center">
  <img width="700px" src ="/images/implementacao.png" />
  <p>Figura 4 - Implementação final do sistema.</p>
</div>

<div style="text-align:center">
  <img width="700px" src ="/images/apps.png" />
  <p>Figura 5 - Aplicativos de pagamento (à esquerda) e de recebimento (à direita).</p>
</div>

<div style="text-align:center">
  <img width="700px" src ="/images/extrato.png" />
  <p>Figura 6 - Tela de extrato do painel de controle.</p>
</div>

## DETALHES
### Integrantes do Grupo
 - André Trefilio
 - Bianca Alt
 - Guilherme Bertero

### Orientadores
 - Profa. Dra. Anarosa Brandão
 - Prof. Dr. Marcos A. Simplício Jr.