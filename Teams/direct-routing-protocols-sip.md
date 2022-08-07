---
title: Roteamento Direto do Sistema de Telefonia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocolos de Roteamento Direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a4ba1715ccf7b1ea2f0dbf12b58fd5aa6556b24
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271256"
---
# <a name="direct-routing---sip-protocol"></a>Roteamento direto – protocolo SIP

Este artigo descreve como o Roteamento Direto implementa o SIP (Protocolo de Iniciação de Sessão). Para rotear corretamente o tráfego entre um controlador de borda de sessão (SBC) e o proxy SIP, alguns parâmetros SIP devem ter valores específicos. Este artigo destina-se a administradores de voz responsáveis por configurar a conexão entre o SBC local e o serviço de proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Processando a solicitação de entrada: localizando o locatário e o usuário

Antes que uma chamada de entrada ou saída possa ser processada, as mensagens OPTIONS são trocadas entre o Proxy SIP e o SBC. Essas mensagens OPTIONS permitem que o Proxy SIP forneça os recursos permitidos ao SBC. É importante que a negociação OPTIONS seja bem-sucedida (resposta 200OK), permitindo uma comunicação adicional entre o Proxy SBC e SIP para estabelecer chamadas. Os cabeçalhos SIP em mensagens OPTIONS para o Proxy SIP são fornecidos como um exemplo abaixo:

| Nome do parâmetro | Exemplo do valor | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Por cabeçalho | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards cabeçalho | Max-Forwards:68 |
| Do Cabeçalho | Do Cabeçalho de: <sip:sbc1.adatum.biz:5058> |
| Para Cabeçalho | Para: <sip:sip.pstnhub.microsoft.com:5061> |
| Cabeçalho CSeq | CSeq: 1 CONVITE | 
| Cabeçalho de Contato | Contato: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Os cabeçalhos SIP não contêm userinfo no URI SIP em uso. De acordo com a [RFC 3261, seção 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), a parte de userinfo de um URI é opcional e PODE estar ausente quando o host de destino não tem uma noção de usuários ou quando o próprio hosst é o recurso que está sendo identificado. Se o sinal @ estiver presente em um URI SIP, o campo do usuário NÃO DEVERÁ estar vazio.
> Observe que o URI SIPS não deve ser usado com o Roteamento Direto, pois não há suporte para ele.
> Verifique a configuração do Controlador de Borda de Sessão e verifique se você não está usando cabeçalhos "Substitui" em solicitações SIP. O Roteamento Direto rejeitará solicitações SIP que têm cabeçalhos Replaces definidos.

Em uma chamada de entrada, o proxy SIP precisa localizar o locatário ao qual a chamada está destinada e localizar o usuário específico dentro desse locatário. O administrador de locatários pode configurar números não DID, por exemplo +1001, em vários locatários. Portanto, é importante encontrar o locatário específico no qual executar a pesquisa de número porque os números não DID podem ser os mesmos em várias organizações do Microsoft 365 ou Office 365.  

Esta seção descreve como o proxy SIP localiza o locatário e o usuário e executa a autenticação do SBC na conexão de entrada.

A seguir está um exemplo da mensagem de Convite SIP em uma chamada de entrada:

| Nome do parâmetro | Exemplo do valor | 
| :---------------------  |:---------------------- |
| Request-URI | INVITE SIP:+18338006777@SIP.PSTNHUB.MICROSOFT.COM SIP /2.0 |
| Por cabeçalho | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards cabeçalho | Max-Forwards:68 |
| Do Cabeçalho | Do Cabeçalho de: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| Para Cabeçalho | Para: sip:+183338006777@sbc1.adatum.biz | 
| Cabeçalho CSeq | CSeq: 1 CONVITE | 
| Cabeçalho de Contato | Contato: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Ao receber o convite, o proxy SIP executa as seguintes etapas:

1. Verifique o certificado. Na conexão inicial, o serviço de Roteamento Direto usa o nome FQDN apresentado no cabeçalho Contato e o corresponde ao Nome Comum ou ao Nome Alternativo da Entidade do certificado apresentado. O nome SBC deve corresponder a uma das seguintes opções:

   - Opção 1. O nome completo do FQDN apresentado no cabeçalho Contato deve corresponder ao nome Alternativo de Nome Comum/Assunto do certificado apresentado.  

   - Opção 2.  A parte de domínio do nome FQDN apresentada no cabeçalho Contato (por exemplo, adatum.biz do nome do FQDN sbc1.adatum.biz) deve corresponder ao valor curinga no Nome Comum/Nome Alternativo da Entidade (por exemplo, *.adatum.biz).

2. Tente encontrar um locatário usando o nome FQDN completo apresentado no cabeçalho Contato.  

   Verifique se o nome do FQDN do cabeçalho de contato (sbc1.adatum.biz) está registrado como um nome DNS em qualquer organização microsoft 365 ou Office 365. Se encontrado, a pesquisa do usuário será executada no locatário que tem o FQDN SBC registrado como um nome de domínio. Se não for encontrada, a Etapa 3 se aplicará.   

3. A etapa 3 só se aplicará se a Etapa 2 falhar. 

   Remova a parte do host do FQDN, apresentada no cabeçalho Contato (FQDN: sbc12.adatum.biz, depois de remover a parte do host: adatum.biz) e verifique se esse nome está registrado como um nome DNS em qualquer organização do Microsoft 365 ou Office 365. Se encontrado, a pesquisa do usuário será executada neste locatário. Se não for encontrada, a chamada falhará.

4. Usando o número de telefone apresentado no Request-URI, execute a pesquisa de número reverso dentro do locatário encontrado na Etapa 2 ou 3. Corresponder o número de telefone apresentado a um URI SIP do usuário dentro do locatário encontrado na etapa anterior.

5. Aplicar configurações de tronco. Localize os parâmetros definidos pelo administrador do locatário para este SBC.

   A Microsoft não dá suporte a ter um proxy SIP de terceiros ou Servidor do Agente de Usuário entre o proxy SIP da Microsoft e o SBC emparelhado, o que pode modificar o URI de Solicitação criado pelo SBC emparelhado.

   Os requisitos para as duas pesquisas (etapas 2 e 3) necessárias para o cenário em que um SBC está interconectado a muitos locatários (cenário de operadora) são abordados posteriormente neste artigo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisitos detalhados para o cabeçalho de contato e o Request-URI

#### <a name="contact-header"></a>Cabeçalho de contato

Para todas as mensagens SIP de entrada (OPÇÕES, CONVIDAR) para o proxy SIP da Microsoft, o cabeçalho Contato deve ter o FQDN SBC emparelhado no nome do host do URI da seguinte maneira:

Sintaxe: Contato: <sip:phone ou sip address@FQDN do SBC;transport=tls> 

De acordo [com a RFC 3261, seção 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), um campo de cabeçalho Contato PODE estar presente em uma mensagem OPTIONS. No Roteamento Direto, o cabeçalho de contato é necessário. Para mensagens INVITE no formato acima, para mensagens OPTIONS, o userinfo pode ser removido do URI SIP e somente FQDN enviado no formato da seguinte maneira:

Sintaxe: Contato: <sip:FQDN do SBC;transport=tls>

Esse nome (FQDN) também deve estar nos campos Nome Comum ou Nome Alternativo da Entidade do certificado apresentado. A Microsoft dá suporte ao uso de valores curinga dos nomes nos campos Nome Comum ou Nome Alternativo da Entidade do certificado.   

O suporte para curingas é descrito na [RFC 2818, seção 3.1](https://tools.ietf.org/html/rfc2818#section-3.1). Especificamente:

*"Os nomes podem conter o caractere curinga \* que é considerado para corresponder a qualquer componente de nome de domínio único ou fragmento de componente. Por exemplo, \*.a.com corresponde foo.a.com mas não bar.foo.a.com. f.com\* corresponde foo.com mas não bar.com."*

Se mais de um valor no cabeçalho Contato apresentado em uma mensagem SIP for enviado pelo SBC, somente a parte FQDN do primeiro valor do cabeçalho Contato será usada.

Como regra geral para Roteamento Direto, é importante que o FQDN seja usado para popular o URI SIP em vez do IP. Uma mensagem INVITE ou OPTIONS de entrada para o Proxy SIP com o cabeçalho Contato em que o nome do host é representado por IP e não FQDN, a conexão será recusada com 403 Proibido.

#### <a name="request-uri"></a>Request-URI 

Para todas as chamadas de entrada, o Request-URI é usado para corresponder o número de telefone a um usuário.   

Atualmente, o número de telefone deve conter um sinal de adição (+), conforme mostrado no exemplo a seguir. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>Do Cabeçalho

Para todas as chamadas recebidas, o Cabeçalho De é usado para corresponder o número de telefone do chamador com a lista de números de telefone bloqueados do chamador.

O número de telefone deve conter um + conforme mostrado no exemplo a seguir.

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>Considerações sobre cabeçalhos de Record-Route contato e de Record-Route

O proxy SIP precisa calcular o FQDN do próximo salto para novas transações de cliente na caixa de diálogo (por exemplo, Bye ou Re-Invite) e ao responder às Opções SIP. Contact ou Record-Route são usados. 

De acordo com [o RFC 3261, seção 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), o cabeçalho Contato é necessário em qualquer solicitação que possa resultar em uma nova caixa de diálogo. O Record-Route só será necessário se um proxy quiser permanecer no caminho de solicitações futuras em uma caixa de diálogo. Se um SBC de proxy estiver em uso com a Otimização de Mídia [Local](./direct-routing-media-optimization.md) para Roteamento Direto, uma rota de registro precisará ser configurada, pois o SBC do proxy precisa permanecer na rota. 

A Microsoft recomenda usar apenas o cabeçalho Contato se um SBC de proxy não for usado:

- De acordo com a [RFC 3261, seção 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), o Record-Route será usado se um proxy quiser permanecer no caminho de solicitações futuras em uma caixa de diálogo, o que não é essencial se nenhum proxy SBC estiver configurado, pois todo o tráfego fica entre o proxy SIP da Microsoft e o SBC emparelhado. 

- O proxy SIP da Microsoft usa apenas o cabeçalho Contact (não Record-Route) para determinar o próximo salto ao enviar opções de ping de saída. Configurar apenas um parâmetro (Contato) em vez de dois (Contato e Rota de Registro) simplificará a administração se um proxy SBC não estiver em uso. 

Para calcular o próximo salto, o proxy SIP usa:

- Prioridade 1. Rota de registro de nível superior. Se o Record-Route de nível superior contiver o nome do FQDN, o nome do FQDN será usado para fazer a conexão na caixa de diálogo de saída.

- Prioridade 2. Cabeçalho de contato. Se Record-Route não existir, o proxy SIP pesquisará o valor do cabeçalho Contato para fazer a conexão de saída. (Essa é a configuração recomendada.)

Se Contact e Record-Route forem usados, o administrador do SBC deverá manter seus valores idênticos, o que causa sobrecarga administrativa. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso do nome do FQDN em Contato ou Record-Route

Não há suporte para o uso de um endereço IP no Record-Route ou contato. A única opção com suporte é um FQDN, que deve corresponder ao Nome Comum ou ao Nome Alternativo da Entidade do certificado SBC (há suporte para valores curinga no certificado).

- Se um endereço IP for apresentado em Rota de registro ou Contato, a verificação de certificado falhará e a chamada falhará.

- Se o FQDN não corresponder ao valor do Nome Alternativo comum ou da Entidade no certificado apresentado, a chamada falhará. 

## <a name="inbound-call-sip-dialog-description"></a>Chamada de entrada: descrição da caixa de diálogo SIP

A tabela a seguir resume as diferenças de fluxo de chamadas e as semelhanças entre os modos de bypass e não bypass:

| Nome do parâmetro | Modo sem bypass | Modo de bypass
| :---------------------  |:---------------------- |:----------------|
| Candidatos à mídia em 183 e 200 mensagens provenientes de | Processadores de mídia | Clientes | 
| Número de 183 mensagens que o SBC pode receber | Um por sessão | Vários | 
| A chamada pode ser com resposta provisória (183) | Sim | Sim |
| A chamada pode ser sem resposta provisória (183) | Sim | Sim |

###  <a name="non-media-bypass-flow"></a>Fluxo de bypass que não é de mídia

Um usuário do Teams pode ter vários pontos de extremidade ao mesmo tempo. Por exemplo, cliente do Teams para Windows, cliente do Teams para iPhone e Telefone do Teams (cliente Android do Teams). Cada ponto de extremidade pode sinalizar um REST HTTP da seguinte maneira:

-   Progresso da chamada – convertido pelo proxy SIP para a mensagem SIP 180. Ao receber a mensagem 180, o SBC deve gerar toque local.

-   Resposta de mídia – convertida pelo proxy SIP para a mensagem 183 com candidatos à mídia no protocolo SDP. Ao receber a mensagem 183, o SBC espera se conectar aos candidatos à mídia recebidos na mensagem SDP. 

    > [!NOTE]
    > Em alguns casos, a resposta de mídia pode não ser gerada e o ponto de extremidade pode responder com a mensagem "Chamada Aceita".

-   Chamada aceita – convertida pelo proxy SIP para a mensagem SIP 200 com SDP. Ao receber a mensagem 200, espera-se que o SBC envie e receba mídia de e para os candidatos SDP fornecidos.

    > [!NOTE]
    > O Roteamento Direto não dá suporte a Convite de Oferta Atrasada (Convidar sem SDP).

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Vários pontos de extremidade tocando com resposta provisória

1.  Ao receber o primeiro Convite do SBC, o proxy SIP envia a mensagem "SIP SIP/2.0 100 Tentando" e notifica todos os pontos de extremidade do usuário final sobre a chamada de entrada. 

2.  Após a notificação, cada ponto de extremidade começará a tocar e enviar mensagens de "Progresso da chamada" para o proxy SIP. Como um usuário do Teams pode ter vários pontos de extremidade, o proxy SIP pode receber várias mensagens de Progresso da Chamada.

3.  Para cada mensagem de Progresso da Chamada recebida dos clientes, o proxy SIP converte a mensagem Progresso da Chamada para a mensagem SIP "SIP SIP/2.0 180 Toque". O intervalo para enviar essas mensagens é definido pelo intervalo das mensagens de recebimento do Controlador de Chamada. No diagrama a seguir, há duas 180 mensagens geradas pelo proxy SIP. Essas mensagens são provenientes dos dois pontos de extremidade do Teams do usuário. Cada um dos clientes tem uma ID de marca exclusiva.  Cada mensagem proveniente de um ponto de extremidade diferente será uma sessão separada (o parâmetro "tag" no campo "Para" será diferente). Mas um ponto de extremidade pode não gerar a mensagem 180 e enviar a mensagem 183 imediatamente, conforme mostrado no diagrama a seguir.

4.  Depois que um ponto de extremidade gera uma mensagem de Resposta de Mídia com os endereços IP dos candidatos à mídia do ponto de extremidade, o proxy SIP converte a mensagem recebida em uma mensagem "Progresso da Sessão SIP 183" com o SDP do cliente substituído pelo SDP do Processador de Mídia. No diagrama a seguir, o ponto de extremidade do Fork 2 atendeu à chamada. Se o tronco não for ignorado, a mensagem SIP 183 será gerada apenas uma vez (Ring Bot ou Ponto de Extremidade do Cliente). O 183 pode vir em uma bifurcação existente ou iniciar um novo.

5.  Uma mensagem de Aceitação da Chamada é enviada com os candidatos finais do ponto de extremidade que aceitaram a chamada. A mensagem aceitação da chamada é convertida em mensagem SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta provisória.](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Vários pontos de extremidade tocando sem resposta provisória

1.  Ao receber o primeiro Convite do SBC, o proxy SIP envia a mensagem "SIP SIP/2.0 100 Tentando" e notifica todos os pontos de extremidade do usuário final sobre a chamada de entrada. 

2.  Após a notificação, cada ponto de extremidade começará a tocar e enviará a mensagem "Andamento da chamada" para o proxy SIP. Como um usuário do Teams pode ter vários pontos de extremidade, o proxy SIP pode receber várias mensagens de Progresso da Chamada.

3.  Para cada mensagem de Progresso da Chamada recebida dos clientes, o proxy SIP converte a mensagem progresso da chamada para a mensagem SIP "SIP SIP/2.0 180 Trying".  O intervalo para enviar as mensagens é definido pelo intervalo de recebimento das mensagens do Controlador de Chamada. Na imagem abaixo, há duas 180 mensagens geradas pelo proxy SIP, o que significa que o usuário fez logon em três clientes do Teams e cada cliente envia o progresso da chamada. Cada mensagem será uma sessão separada (o parâmetro "tag" no campo "Para" é diferente)

4.  Uma mensagem de Aceitação da Chamada é enviada com os candidatos finais do ponto de extremidade que aceitaram a chamada. A mensagem aceitação da chamada é convertida em mensagem SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando sem resposta provisória.](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Fluxo de bypass de mídia

As mesmas mensagens (100 Tentando, 180, 183) são usadas no cenário de bypass de mídia. 

O esquema a seguir mostra um exemplo do fluxo de chamada de bypass. 

> [!NOTE]
> Os candidatos à mídia podem vir de diferentes pontos de extremidade. 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta provisória.](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opção Replaces

O SBC deve dar suporte a Convidar com Substituições.

## <a name="size-of-sdp-considerations"></a>Tamanho das considerações de SDP

A interface de Roteamento Direto pode enviar uma mensagem SIP que excede 1.500 bytes.  O tamanho do SDP causa isso principalmente. No entanto, se houver um tronco UDP atrás do SBC, ele poderá rejeitar a mensagem se ela for encaminhada do proxy SIP da Microsoft para o tronco não modificado. A Microsoft recomenda a remoção de alguns valores no SDP no SBC ao enviar a mensagem para os troncos UDP. Por exemplo, os candidatos a ICE ou codecs não utilizados podem ser removidos.

## <a name="call-transfer"></a>Transferência de chamadas

O Roteamento Direto dá suporte a dois métodos para transferência de chamada:

- Opção 1. Processos de proxy SIP Consulte o cliente localmente e atue como um Referee, conforme descrito na seção 7.1 do RFC 3892.

  Com essa opção, o proxy SIP encerra a transferência e adiciona um novo Convite. 


- Opção 2.  O proxy SIP envia a referência ao SBC e atua como um transferor, conforme descrito na Seção 6 da RFC 5589.

  Com essa opção, o proxy SIP envia uma referência ao SBC e espera que o SBC manipule totalmente a transferência.

O proxy SIP seleciona o método com base nos recursos relatados pelo SBC. Se o SBC indicar que ele dá suporte ao método "Refer", o proxy SIP usará a Opção 2 para transferências de chamada.

Veja a seguir um exemplo de um SBC enviando a mensagem de que há suporte para o método Refer:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Se o SBC não indicar que Refer como um método com suporte, o Roteamento Direto usará a Opção 1 (o proxy SIP atua como um Referee). O SBC também deve sinalizar que dá suporte ao método Notify:

Exemplo de SBC que indica que não há suporte para o método Refer:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Processos de proxy SIP Consulte o cliente localmente e atue como um Referee

Se o SBC indicou que o método Refer não tem suporte, o proxy SIP atua como um Referee. 

A solicitação De referência proveniente do cliente será encerrada no proxy SIP. (A solicitação De referência do cliente é mostrada como "Transferência de chamada para Dave" no diagrama a seguir.  Para obter mais informações, consulte a seção 7.1 do [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta provisória.](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>O proxy SIP envia o recurso Referir-se ao SBC e atua como um Transferor

Esse é o método preferencial para transferências de chamadas e é obrigatório para dispositivos que buscam a certificação de bypass de mídia. Não há suporte para a transferência de chamada sem que o SBC possa manipular Refer no modo de bypass de mídia. 

O padrão é explicado na Seção 6 da RFC 5589. Os RFCs relacionados são:

- [Controle de chamada SIP (Protocolo de Iniciação de Sessão) – Transferência](https://tools.ietf.org/html/rfc5589)

- [Cabeçalho "Substitui" do protocolo SIP](https://tools.ietf.org/html/rfc3891)

- [Mecanismo "Referenciado por" do PROTOCOLO SIP](https://tools.ietf.org/html/rfc3892)

Essa opção pressupõe que o proxy SIP atua como um Transferor e envia uma mensagem De referência para o SBC. O SBC atua como um Transferee e manipula a referência para gerar uma nova oferta para transferência. Há dois casos possíveis:

- A chamada é transferida para um participante PSTN externo. 
- A chamada é transferida de um usuário do Teams para outro usuário do Teams no mesmo locatário por meio do SBC. 

Se a chamada for transferida de um usuário do Teams para outro por meio do SBC, espera-se que o SBC emita um novo convite (inicie uma nova caixa de diálogo) para o destino de transferência (o usuário do Teams) usando as informações recebidas na mensagem De referência. 

Para preencher os campos De/Transferor para a transação da solicitação internamente, o proxy SIP precisa transmitir essas informações dentro dos cabeçalhos REFER-TO/REFERRED-BY. 

O proxy SIP formará o REFER-TO como um URI SIP composto por um FQDN de proxy SIP no nome do host e um dos seguintes:

- Um número de telefone E.164 na parte de nome de usuário do URI, caso o destino da transferência seja um número de telefone ou

- Parâmetros x-m e x-t que codificam a MRI de destino de transferência completa e a ID do locatário, respectivamente 

O cabeçalho REFERRED-BY é um URI SIP com a MRI do transferor codificada nele, bem como a ID do locatário do transferor e outros parâmetros de contexto de transferência, conforme mostrado na tabela a seguir:

| Parâmetro | Valor | Descrição |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Ressonância | MRI completa do destino de transferência/transferência, conforme preenchido pelo CC |
| x-t | ID do locatário | ID de locatário opcional da ID do locatário x-t, conforme preenchido pelo CC |
| x-ti | ID de Correlação do Transferidor | ID de correlação da chamada para o transferidor |
| x-tt | Transferir URI de chamada de destino | URI de substituição de chamada codificado |

O tamanho do Cabeçalho de Referência pode ter até 400 símbolos nesse caso. O SBC deve dar suporte ao tratamento de mensagens de referência com tamanho de até 400 símbolos.

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta provisória.](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Temporizador de sessão

O proxy SIP dá suporte (sempre oferece) o Temporizador de Sessão em chamadas sem bypass, mas não o oferece em chamadas de bypass. O uso do Temporizador de Sessão pelo SBC não é obrigatório.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso do parâmetro Request-URI user=phone

O proxy SIP analisa o Request-URI e, se o parâmetro user=phone estiver presente, o serviço manipulará o Request-URI como um número de telefone, correspondendo o número a um usuário. Se o parâmetro não estiver presente, o proxy SIP aplicará heurística para determinar o tipo de usuário Request-URI (número de telefone ou um endereço SIP).

A Microsoft recomenda sempre aplicar o parâmetro user=phone para simplificar o processo de configuração de chamada.

## <a name="history-info-header"></a>History-Info cabeçalho

O cabeçalho History-Info é usado para redirecionar solicitações SIP e "fornecer(s) um mecanismo padrão para capturar as informações do histórico de solicitações para habilitar uma ampla variedade de serviços para redes e usuários finais". Para obter mais informações, [consulte RFC 4244 – Seção 1.1](http://www.ietf.org/rfc/rfc4244.txt). Para o Sistema de Telefonia da Microsoft, esse cabeçalho é usado em cenários de Simulring e Encaminhamento de Chamadas.  

Se estiver enviando, o History-Info será habilitado da seguinte maneira:

- O proxy SIP inserirá um parâmetro que contém o número de telefone associado em entradas History-Info individuais que compõem o cabeçalho History-Info enviado ao Controlador PSTN.  Usando apenas entradas que têm o parâmetro de número de telefone, o Controlador PSTN recriará um novo cabeçalho History-Info e o passará para o provedor de tronco SIP por meio do proxy SIP.

- History-Info cabeçalho será adicionado para casos simultâneos de encaminhamento de chamadas e anel.

- History-Info cabeçalho não será adicionado para casos de transferência de chamada.

- Uma entrada de histórico individual no cabeçalho History-Info recriado terá o parâmetro de número de telefone fornecido combinado com o FQDN de Roteamento Direto (sip.pstnhub.microsoft.com) definido como a parte host do URI; um parâmetro 'user=phone' será adicionado como parte do URI SIP.  Todos os outros parâmetros associados ao cabeçalho History-Info original, exceto os parâmetros de contexto do telefone, serão passados no cabeçalho History-Info re-construído.  

  > [!NOTE]
  > As entradas privadas (conforme determinado pelos mecanismos definidos na Seção 3.3 da RFC 4244) serão encaminhadas como estão porque o provedor de tronco SIP é um par confiável.

- Os History-Info entrada são ignorados.

A seguir está o formato do cabeçalho Histórico-informações enviado pelo proxy SIP:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Se a chamada tiver sido redirecionada várias vezes, as informações sobre cada redirecionamento serão incluídas com o motivo apropriado em ordem cronológica.


Exemplo de cabeçalho:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

O History-Info é protegido por um mecanismo TLS obrigatório. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Conexão SBC com o mecanismo de roteamento direto e failover

Consulte o mecanismo de failover da seção para sinalização SIP [no Plano de Roteamento Direto](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Retry-After

Se um datacenter de Roteamento Direto estiver ocupado, o serviço poderá enviar uma mensagem Retry-After com um intervalo de um segundo para o SBC. Quando o SBC recebe uma mensagem 503 com um cabeçalho Retry-After em resposta a um INVITE, o SBC deve encerrar essa conexão e tentar o próximo datacenter da Microsoft disponível.

## <a name="handling-retries-603-response"></a>Tratamento de repetições (resposta 603)
Se um usuário final observar várias chamadas perdidas para uma chamada após a recusa da chamada de entrada, isso significa que o mecanismo de repetição do provedor de tronco SBC ou PSTN está configurado incorretamente. O SBC deve ser reconfigurado para interromper os esforços de repetição na resposta 603.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Reinicialização do ICE: chamada de bypass de mídia transferida para um ponto de extremidade que não dá suporte a bypass de mídia

O SBC deve dar suporte a reinicializações de ICE, conforme descrito na [RFC 5245, seção 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

A reinicialização no Roteamento Direto é implementada de acordo com os seguintes parágrafos do RFC:

*Para reiniciar o ICE, um agente DEVE alterar o ice-pwd e o ice-logag para o fluxo de mídia em uma oferta.  Observe que é permitido usar um atributo de nível de sessão em uma oferta, mas fornecer o mesmo ice-pwd ou ice-upload como um atributo de nível de mídia em uma oferta subsequente.  Essa não é uma alteração na senha, apenas uma alteração em sua representação e não causa uma reinicialização do ICE.*

*Um agente define o restante dos campos no SDP para esse fluxo de mídia como faria em uma oferta inicial desse fluxo de mídia (consulte a Seção 4.3).  Consequentemente, o conjunto de candidatos PODE incluir alguns, nenhum ou todos os candidatos anteriores para esse fluxo e PODE incluir um conjunto totalmente novo de candidatos reunidos conforme descrito na Seção 4.1.1.*

Se a chamada foi estabelecida inicialmente com bypass de mídia e a chamada é transferida para um cliente do Skype for Business, o Roteamento Direto precisa inserir um Processador de Mídia– isso ocorre porque o Roteamento Direto não pode ser usado com um cliente Skype for Business com bypass de mídia. O Roteamento Direto inicia o processo de reinicialização do ICE alterando o ice-pwd e o ice-linkag e oferecendo novos candidatos à mídia em um reinvite.
