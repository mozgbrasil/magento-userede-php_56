[checkmark]: https://raw.githubusercontent.com/mozgbrasil/mozgbrasil.github.io/master/assets/images/logos/logo_32_32.png "MOZG"
![valid XHTML][checkmark]

[url-method]: http://www.userede.com.br/
[requerimentos]: http://mozgbrasil.github.io/requerimentos/
[contact-userede]: http://www.userede.com.br/fale-conosco/
[tickets]: https://cerebrum.freshdesk.com/support/tickets/new
[preco]: http://www.cerebrum.com.br/preco/
[getcomposer]: https://getcomposer.org/
[uninstall-mods]: https://getcomposer.org/doc/03-cli.md#remove
[artigo-composer]: http://mozg.com.br/ubuntu/composer
[ioncube-loader]: http://www.ioncube.com/loaders.php
[acordo]: http://mozg.com.br/acordo-licenca-usuario-final/

# Mozg\Userede

## Sinopse

Integração a [Userede][url-method]

## Motivação

Atender o mercado de módulos para Magento oferecendo melhorias e um excelente suporte

## Vídeo(s) Demonstrativo

 :star: | 1 | 2 | 3 | 4
--- | --- | --- | --- | ---
A | [![Clique aqui](https://img.youtube.com/vi/oag7gee5R54/0.jpg)](https://youtu.be/oag7gee5R54 "Módulo para Magento com integração a Cielo usando o método de Cartão de Crédito e Captura manual") | [![Clique aqui](https://img.youtube.com/vi/jboYrYLG5L8/0.jpg)](https://youtu.be/jboYrYLG5L8 "Módulo para Magento com integração a Cielo usando o método de Cartão de Crédito e Captura automática e/ou Entrega automática") | _ | _
B | _ | _ | _ | _
C | _ | _ | _ | _
D | _ | _ | _ | _

## Suporte / Dúvidas

Para obter o devido suporte [Clique aqui][tickets], relatando o motivo da ocorrência o mais detalhado possível e anexe o print da tela para nosso entendimento

## Preço

[Clique aqui][preco]

## Recursos do módulo

- [✓] Transação
- [✓] Consulta
- [✓] Captura
- [✓] Reembolso
- [✓] Cancelamento

## Característica técnica

No checkout é feito o processo de autorização

No retorno de "Transação autorizada" é feito redirecionamento para a página de sucesso

Na página de sucesso é enviado infomações para o recurso de notificação da transação

Via CRON deve ser processado a notificação da transação,

No processamento da notificação caso o pagamento seja confirmado, deve ser alterado o "state/status" do pedido para "processing" ou seja "Processando", liberando as ações para processar a fatura e o envio

Quando o pedido é enviado o status é alterado para "complete" ou seja "Completo"

Antes do envio da mercadoria, sempre confira as informações do pedido, se o status da transação está sendo exibido que o pagamento foi confirmado, inclusive junto a operadora financeira se a transação foi capturada, caso algo esteja inconsistente será necessário cancelar o pedido até a correção da ocorrência

<!--

## Mozg OneClick

No módulo as Referências Recorrentes são salvas nos <a href="http://docs.magento.com/m1/ce/user_guide/payment/paypal-billing-agreements.html" target="_blank">Contratos de Faturamento</a> do Magento.

Todos os novos cartões salvos serão automaticamente salvos em Contratos de Faturamento do Magento.

-->

## Setup Cron

Para o uso do método é necessário ativar a <a href="https://pt.wikipedia.org/wiki/Crontab">CRON</a> para o <a href="https://magento.com/">Magento</a>

<a href="https://mozg.com.br/dicas/dicas-magento1#como-ativar-a-cron-no-magento">Clique aqui</a> para visualizar o documento da MOZG

Certifique-se de que ação esteja sendo executado a cada minuto

Esse módulo usa o cronjob para processar as notificações

O módulo executa as notificações que foram recebidas há pelo menos 5 minutos.

## Testando na Heroku

Gostaria de apresentar o aplicativo que disponibilizei para a plataforma Heroku

Com apenas 1 clique, o aplicativo cria sua loja virtual usando a plataforma de comércio eletrônico Magento e instala os módulos da MOZG

[https://github.com/mozgbrasil/heroku-magento#descrição](https://github.com/mozgbrasil/heroku-magento#descrição)

## Instalação - Atualização - Desinstalação - Desativação

--

Sugiro "printar" as telas com todos os procedimentos executados

Envie para nós as imagens das telas na eventualidade de quaisquer dificuldades

--

Este módulo destina-se a ser instalado usando o [Composer][getcomposer]

Execute o seguinte comando no terminal, para visualizar a existencia do Composer e sua versão

	composer --version

Caso não tenha o Composer em seu ambiente, sugiro ler o seguinte artigo [Clique aqui][artigo-composer]

--

É necessário que o servidor tenha o suporte a extensão [ionCube PHP Loader][ioncube-loader]

Execute o seguinte comando no terminal, para visualizar a existencia da extensão nesse ambiente denominado PHP CLI

	php -v

Para visualizar se essa extensão está ativa em seu servidor no ambiente denominado PHP WEB

Certique se da presença do arquivo phpinfo.php na raiz do seu projeto

	<?php phpinfo(); ?>

Caso não exista o arquivo phpinfo.php na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

Acesse o arquivo pelo browser

Em seguida pesquise pelo termo "ionCube PHP Loader"

Caso o seu servidor não tenha o suporte a extensão, entre em contato com sua empresa de hospedagem e peça para que eles ativem a extensão

Caso tenha a permissão e queira ativar a extensão, [Clique aqui][ioncube-loader]

Em "Loader Downloads API", efetue download do pacote compatível com o seu servidor

Descompacte o pacote e faça upload do arquivo "loader-wizard.php" para seu servidor, onde será demonstrado o passo a passo para a ativação da extensão

[Clique aqui](https://youtu.be/GZ2J6MLkko4) para ver os processos executados

--

Na presença do "ionCube PHP Loader" efetue o download do seguinte arquivo e coloque na raiz do seu servidor e acesse, se funcionar quer dizer que o "ionCube" está lendo esse tipo de encriptação

https://raw.githubusercontent.com/mozgbrasil/heroku-magento/master/phpinfo-ioncube-encoder10-x86-64-php_56.php

--

Para utilizar o(s) módulo(s) da MOZG é necessário aceitar o [Acordo de licença do usuário final][acordo]

--

Sugiro manter um ambiente de testes para efeito de testes e somente após os devidos testes aplicar os devidos procedimento no ambiente de produção

--

Sugiro efetuar backup da plataforma Magento e do banco de dados

--

Antes de efetuar qualquer atualização no Magento sempre mantenha o Compiler e o Cache desativado

--

Certique se da presença do arquivo composer.json na raiz do seu projeto Magento e que o mesmo tenha os parâmetros semelhantes ao modelo JSON abaixo

	{
	  "minimum-stability": "dev",
	  "prefer-stable": true,
	  "license": [
	    "proprietary"
	  ],
	  "repositories": [
	    {
	      "type": "composer",
	      "url": "https://packages.firegento.com"
	    }
	  ],
	  "extra": {
	    "magento-root-dir": "./",
	    "magento-deploystrategy": "copy",
	    "magento-force": true
	  }
	}

Caso não exista o arquivo composer.json na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

### Para instalar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer require mozgbrasil/magento-userede-php_56:dev-master

Você pode verificar se o módulo está instalado, indo ao backend em:

	STORES -> Configuration -> ADVANCED/Advanced -> Disable Modules Output

--

### Para atualizar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

Antes de efetuar qualquer processo que envolva atualização no Magento é recomendado manter o Compiler e Cache desativado

	composer update

Na ocorrência de erro, renomeie a pasta /vendor/mozgbrasil e execute novamente

Para checar a data do módulo execute o seguinte comando

	grep -ri --include=*.json 'time": "' ./vendor/mozgbrasil

--

### Para [desinstalar][uninstall-mods] o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer remove mozgbrasil/magento-userede-php_56

--

### Para desativar o módulo

1. Antes de efetuar qualquer processo que envolva atualização sobre o Magento é necessário manter o Compiler e Cache desativado

2. Caso queira desativar os módulos da MOZG renomeie a seguinte pasta app/code/local/Mozg

A desativação do módulo pode ser usado para detectar se determinada ocorrência tem relação com o módulo

## Como configurar o método de pagamento

Para configurar o método de pagamento, acesse no backend em:

	STORES -> Configuration -> Sales/Payment Methods -> Userede (powered by MOZG)

Você terá os campos a seguir

### Userede API V2 - Configurações Padrão

#### Configurações necessárias

##### • **Modo Teste ou Produção**

Deve ser informado o devido ambiente

##### • **Merchant ID para o ambiente de teste**

Efetue o cadastro no seguinte ambiente para obter os dados de integração como: MerchantId e MerchantKey

https://cadastrosandbox.userede.com.br/

##### • **Merchant Key Ambiente de teste**

Efetue o cadastro no seguinte ambiente para obter os dados de integração como: MerchantId e MerchantKey

https://cadastrosandbox.userede.com.br/

##### • **Merchant ID para o ambiente de produção**

A informação deve ser fornecido pela Userede

##### • **Merchant Key Ambiente de produção**

A informação deve ser fornecido pela Userede

#### Avançado: Processamento de Pedidos Magento

##### • **Status do pedido: ordem de criação**

Status dos pedidos recém-criados, antes da confirmação de resultado de pagamento via notificações de servidor da operadora

##### • **Status do pedido: autorização de pagamento**

Status dos pedidos após autorização confirmada por uma notificação de AUTORIZAÇÃO da operadora

##### • **Status do pedido: pagamento confirmado**

Status dos pedidos após captura confirmada por uma notificação de AUTORIZAÇÃO da operadora

##### • **Status do pedido: cancelamento de pedido**

Status dos pedidos após cancelamento confirmada por uma notificação de CANCELAMENTO da operadora

Se as encomendas já estiverem faturadas, não poderão ser canceladas

##### • **Status do pedido: captura de pagamento (produtos virtuais)**

Selecione somente o status atribuído ao estado concluído, deixe vazio para usar o mesmo que os produtos normais

##### • **Status do pedido: Reembolsado**

Status dos pedidos após reembolso confirmada por uma notificação de REEMBOLSO da operadora

##### • **Status do pedido: Reembolsado Parcial**

Status dos pedidos após reembolso (parcial) confirmada por uma notificação de REEMBOLSO_PARCIAL da operadora. Recomendamos que não defina este status e deixe Magento decidir o status.

##### • **Status do pedido: pedidos pendentes**

Status dos pedidos após notificação de PENDENCIA da operadora

##### • **Tipo de Captura**

Imediato é o padrão

Defina como manual se você quiser executar a captura de fundos manualmente mais tarde

##### • **Criar uma fatura pendente (apenas para captura manual)**

Isso criará uma fatura pendente se a notificação de AUTORIZAÇÃO for recebida.

 Nota: isto fará com que Magento empurre todas as encomendas para o estado: 'Processamento' uma vez que a factura é criada, ignorando todas as outras definições.

##### • **Status do pedido: Capturar no embarque**

Se você habilitar esta função será feito uma solicitação de captura para a operadora se você fizer o envio

##### • **Ativar Descancelar pedido**

Se uma pedido é cancelada por algum motivo, mas recebeu uma notificação de que o pagamento é autorizado, isso cancelará automaticamente o pedido

##### • **Cancelamento\Reembolso automático quando o pedido é cancelado**

Ativar / Desativar reembolso automático ao cancelar um pedido

##### • **E-mail da fatura**

Ativar / desativar atualizações de e-mails

##### • **Enviar e-mail de notificaçao do status do pedido**

Ativar / desativar e-mails de atualização para todas as alterações no status do pedido para o cliente

##### • **Ativar log de depuração**

Deve ser armazenado os processos do módulo em var/log/

O arquivo

DATE_mozg.log

se trata de log do módulo sendo um log mais detalhado contendo todos os processos inclusive das execuções realizadas pelas bibliotecas externas do módulo

O arquivo

payment_METHOD.log

#### Avançado: Userede Notificações

##### • **Ignorar notificação de reembolso**

Se o reembolso for feito na operadora, e a mesma enviar uma notificação de reembolso para o Magento, deve ser criado automaticamente uma nota de crédito. Se você definir essa configuração como 'Sim', isso não acontecerá porque ele não processará nenhuma das notificações de REEMBOLSO recebidas.

<!--
#### Avançado: Contratos de faturamento

##### • **Tipo de Contrato**

Quando ativado, os usuários podem salvar seus cartões de crédito e suas autorizações

ONECLICK exigirá a entrada do CVC para pagamentos subsequentes, enquanto RECURRING não.
-->

#### Avançado: Experiência de Checkout

##### • **Redirecionar o destino após o cancelamento**

Determina como os compradores são redirecionados após cancelar um pagamento.

##### • **Método de pagamento método de renderização**

Determina se os métodos de pagamento serão exibidos com seu logotipo ou apenas o nome.

##### • **Idioma local (opcional)**

Isso substituirá o local do cliente padrão do armazenamento do Magento.

Deixe vazio para deixar Magento decidir (Ex: nl_NL)

##### • **Código do país ISO (opcional)**

Isso irá substituir o país do endereço de faturamento do comprador ao determinar quais métodos de pagamento serão exibidos.

<!--
#### Avançado: Revisão manual

##### • **Status da revisão manual**

Esse status será acionado quando a operadora notificar o módulo Magento de que o pagamento foi incluído na revisão manual. Se você não tiver essa configuração ou não quiser um status separado, mantenha-o no padrão (por exemplo, '- Por Favor Selecione -').

#### • **Revisão Manual Status Aceito**

Apenas relevante se você não tiver uma ação definida quando você aceitar uma revisão manual. Este status será acionado quando uma notificação "MANUAL_REVIEW_ACCEPT" for recebida da operadora. Se você já pediu a operadora para definir uma ação para isso (por exemplo, captura) ou não quiser um status separado para isso, mantenha-o no padrão (por exemplo, '- Por Favor Selecione -')

#### Avançado: Dividir Pagamentos

##### • **Estratégia de reembolso**

É possível fazer pagamentos divididos com GiftCards, por favor configure aqui qual estratégia de reembolso você deseja usar
-->

### Cartão de Crédito Userede

#### • **Ativar**

Para "ativar" ou "desativar" o uso do método

#### • **Ordem de exibição**

É a ordem apresentada em métodos de entrega no passo de fechamento de pedido

#### • **Título**

Nome do método que deve ser exibido

#### • **Pagamentos aplicáveis aos países**

Você pode definir se o método deve funcionar para "Todos os Países aceito" ou "Especificar Países "

#### • **Pagamentos específicos aos países**

Você deve selecionar os países que o método deve ser funcional

#### • **Tipos de Cartão de Crédito**

Selecione as bandeiras liberadas pela operadora

#### • **Visível em**

Determine a visibilidade desse método de pagamento no frontend e/ou backend do Magento

#### • **Autenticar**

Define se o comprador será direcionado ao Banco emissor para autenticação do cartão

Para essa opção é enviado o parâmetro ReturnUrl, não deve funcionar para dominios que contenham caracteres especiais conforme as regras da Cielo

Para pedidos feito no backend não ative essa opção, pois não deve funcionar o redirecionamento para a URL de autenticação

#### • **Ativar Parcelamentos**

Define o uso de parcelas

#### • **Parcelas padrão**

Para a coluna "Moeda" informe a sigla da moeda por exemplo BRL

Para a coluna "Montante (incl.)" informe o valor mínimo para a exibição da parcela

Para a coluna "Número máximo de parcelas" informe o número de parcelas que será exibida até o valor previamente informando para a exibição da parcela

Para a coluna "Taxa de juro (%)" informe a taxa de juro usada

-

A regra para a exibição da parcela é definida com base na faixas de preços

O módulo já vem pré-configurado da seguinte forma

Até R$ 100,00 em 1 parcela

Até R$ 200,00 em 2 parcelas

Até R$ 600,00 em 3 parcelas

Até R$ 800,00 em 4 parcelas

Até R$ 10.000,00 em 5 parcelas

Até R$ 100.000,00 em 6 parcelas

Altere conforme sua necessidade

#### • **Desativar em total geral zero**

Desative esta forma de pagamento no checkout quando o total geral da cotação for 0.

### Cartão de Débito Userede

#### • **Ativar**

Para "ativar" ou "desativar" o uso do método

#### • **Ordem de exibição**

É a ordem apresentada em métodos de entrega no passo de fechamento de pedido

#### • **Título**

Nome do método que deve ser exibido

#### • **Pagamentos aplicáveis aos países**

Você pode definir se o método deve funcionar para "Todos os Países aceito" ou "Especificar Países "

#### • **Pagamentos específicos aos países**

Você deve selecionar os países que o método deve ser funcional

#### • **Tipos de Cartão de Débito**

Selecione as bandeiras liberadas pela operadora

#### • **Visível em**

Determine a visibilidade desse método de pagamento no frontend e/ou backend do Magento

#### • **Desativar em total geral zero**

Desative esta forma de pagamento no checkout quando o total geral da cotação for 0.

### Boleto Userede

#### • **Ativar**

Para "ativar" ou "desativar" o uso do método

#### • **Ordem de exibição**

É a ordem apresentada em métodos de entrega no passo de fechamento de pedido

#### • **Título**

Nome do método que deve ser exibido

#### • **Pagamentos aplicáveis aos países**

Você pode definir se o método deve funcionar para "Todos os Países aceito" ou "Especificar Países "

#### • **Pagamentos específicos aos países**

Você deve selecionar os países que o método deve ser funcional

#### • **Tipos de Boleto**

Selecione as bandeiras liberadas pela operadora

#### • **Status do pedido não pago**

Com Boleto é possível pagar menos do que o valor total. Selecione aqui o status, se este for o caso. Se você deixar isso em branco, ele tomará o status de pedido de pagamento autorizado como status padrão

#### • **Status do pedido pago em excesso**

Com Boleto é possível pagar mais do que o valor total. Selecione aqui o status, se este for o caso. Se você deixar isso em branco, ele tomará o status de pedido de pagamento autorizado como status padrão

#### • **Visível em**

Determine a visibilidade desse método de pagamento no frontend e/ou backend do Magento

### Transferência Eletrônica Userede

#### • **Ativar**

Para "ativar" ou "desativar" o uso do método

#### • **Ordem de exibição**

É a ordem apresentada em métodos de entrega no passo de fechamento de pedido

#### • **Título**

Nome do método que deve ser exibido

#### • **Pagamentos aplicáveis aos países**

Você pode definir se o método deve funcionar para "Todos os Países aceito" ou "Especificar Países "

#### • **Pagamentos específicos aos países**

Você deve selecionar os países que o método deve ser funcional

#### • **Tipos de Transferência Eletrônica**

Selecione as bandeiras liberadas pela operadora

#### • **Status do pedido não pago**

Com Boleto é possível pagar menos do que o valor total. Selecione aqui o status, se este for o caso. Se você deixar isso em branco, ele tomará o status de pedido de pagamento autorizado como status padrão

#### • **Status do pedido pago em excesso**

Com Boleto é possível pagar mais do que o valor total. Selecione aqui o status, se este for o caso. Se você deixar isso em branco, ele tomará o status de pedido de pagamento autorizado como status padrão

#### • **Visível em**

Determine a visibilidade desse método de pagamento no frontend e/ou backend do Magento

## Perguntas mais frequentes "FAQ"

### 401 Unauthorized
### Erro: Client error: `POST https://api.userede.com.br/v2/sales/` resulted in a `401 Unauthorized` response

Deve ser exibido o retorno "401 Unauthorized" na falha da autenticação

### Oque fazer após a instalação do módulo ?

1.

Crie uma conta de teste em

https://cadastrosandbox.userede.com.br/

Onde será fornecido o seu MerchantId e MerchantKey

Configure no método no Magento o seu MerchantId e MerchantKey

Para efeito de testes, pode ser usado os seguintes cartões de testes

http://mozg.com.br/dicas/dicas-magento1#cartões-de-crédito-para-testes

Efetue a finalização de um pedido sobre o ambiente de teste onde será feito o processamento da transação

Se foi exibido a tela de finalização quer dizer que foi processado sua transação

Faça interação junto a Userede solicitando homologação dessa integração e solicitando os dados para ser usados em ambiente de produção

https://suporte.userede.com.br

### Como cancelar um pedido

Para cancelar um pedido pelo magento, acesse a fatura previamente criada e clique no botão "Cancelar" em seguida acesse o pedido e clique no botão "Cancelar

### Como fazer o reembolso

Acesse a fatura previamente criada e clique no botão "Reembolso"

Obs. o botão "Reembolso" só deve ser exibido quando tiver sido feito a captura

Na visualização do pedido ao clicar no botão "Reembolsar" o Magento só exibe o botão nomeado como "Reembolso Offline", ao clicar nesse botão só é feito a ação de Reembolso para o Magento

Na visualização da fatura do pedido ao clicar no botão "Reembolsar" o Magento deve exibir os botões nomeados como "Reembolso Offline" e "Reembolso", ao clicar no botão "Reembolso" é disparado ação "Online" ou seja é disparado ação para a operadora de pagamento "Cancelar" a transação relacionada ao pedido

### Como alterar a imagem do método

Pode ser adicionado a imagem, contendo qualquer uma das nomenclaturas a seguir

- method-boleto.png
- method-creditcard.png
- method-debitcard.png
- method-eletronictransfer.png

E adicione a imagem no diretório do seu template

/skin/frontend/<TEMPLATE>/default/images/mozg_userede

### Como personalizar os arquivos phtml

Você pode personalizar o arquivo phtml editando o mesmo e em seguida adicionado o arquivo na estrutura de diretório do seu template

A seguir aplicamos o suporte a um template especifico

cp -r app/design/frontend/base/default/template/mozg_userede/ app/design/frontend/smartwave/porto/template

### Dados de contato - Userede

implantacao.operacoes@userede.com.br

Rodolfo de Lucena - <rmoreira@userede.com.br> - 11 3320-9058

ou acesse

http://userede.tasker.com.br/

ou acesse

Para entrar em contato com a [Userede][contact-userede]

## Manual

http://www.userede.com.br/suporte/desenvolvedores/

http://apidocs.userede.com.br/

## Contribuintes

Equipe Mozg

## License

[Comercial License](LICENSE.txt)

## Badges

[![Join the chat at https://gitter.im/mozgbrasil](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/mozgbrasil/)
[![Latest Stable Version](https://poser.pugx.org/mozgbrasil/magento-userede-php_56/v/stable)](https://packagist.org/packages/mozgbrasil/magento-userede-php_56)
[![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-userede-php_56/downloads)](https://packagist.org/packages/mozgbrasil/magento-userede-php_56)
[![Latest Unstable Version](https://poser.pugx.org/mozgbrasil/magento-userede-php_56/v/unstable)](https://packagist.org/packages/mozgbrasil/magento-userede-php_56)
[![License](https://poser.pugx.org/mozgbrasil/magento-userede-php_56/license)](https://packagist.org/packages/mozgbrasil/magento-userede-php_56)
[![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-userede-php_56/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-userede-php_56)
[![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-userede-php_56/d/daily)](https://packagist.org/packages/mozgbrasil/magento-userede-php_56)
[![Reference Status](https://www.versioneye.com/php/mozgbrasil:magento-userede-php_56/reference_badge.svg?style=flat-square)](https://www.versioneye.com/php/mozgbrasil:magento-userede-php_56/references)
[![Dependency Status](https://www.versioneye.com/php/mozgbrasil:magento-userede-php_56/1.0.0/badge?style=flat-square)](https://www.versioneye.com/php/mozgbrasil:magento-userede-php_56/1.0.0)

:cat2:
