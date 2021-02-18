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
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocolos de Roteamento Direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fe636029c3a058dc1a8d33cc191d7654888ec5e
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278721"
---
# <a name="direct-routing---sip-protocol"></a>Roteamento Direto – protocolo SIP

Este artigo descreve como o Roteamento Direto implementa o PROTOCOLO . Para rotear corretamente o tráfego entre um Controlador de Borda de Sessão (SBC) e o proxy SIP, alguns parâmetros SIP devem ter valores específicos. Este artigo destina-se aos administradores de voz que são responsáveis por configurar a conexão entre o SBC local e o serviço proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Processar a solicitação de entrada: encontrar o locatário e o usuário

Antes que uma chamada de entrada ou saída possa ser processada, as mensagens OPÇÕES são trocadas entre o Proxy SIP e o SBC. Essas mensagens OPÇÕES permitem que o Proxy SIP forneça os recursos permitidos ao SBC. É importante que a negociação DE OPÇÕES seja bem-sucedida (resposta 200OK), permitindo uma comunicação posterior entre SBC e Proxy SIP para estabelecer chamadas. Os headers SIP em uma mensagem OPTIONS para Proxy SIP são fornecidos como exemplo abaixo:

| Nome do parâmetro | Exemplo do valor | 
| :---------------------  |:---------------------- |
| Solicitação de URI | OPÇÕES sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Via Header | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards de dados | Max-Forwards:68 |
| Do Header | Do Header De: <sip:sbc1.adatum.biz:5058> |
| Para o Header | Para: <sip:sip.pstnhub.microsoft.com:5061> |
| Header CSeq | CSeq: 1 CONVITE | 
| Header de Contato | Contato: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Os headers SIP não contêm userinfo no URI SIP em uso. Conforme [RFC 3261, seção 19.1.1,](https://tools.ietf.org/html/rfc3261#section-19.1.1)a parte de userinfo de um URI é opcional e pode estar ausente quando o host de destino não tem uma noção de usuários ou quando o próprio hosst é o recurso que está sendo identificado. Se o sinal @ estiver presente em um URI SIP, o campo do usuário NÃO DEVE estar vazio.

Em uma chamada recebida, o proxy SIP precisa encontrar o locatário para o qual a chamada está destinada e encontrar o usuário específico dentro desse locatário. O administrador do locatário pode configurar números não DID, por exemplo, +1001, em vários locatários. Portanto, é importante encontrar o locatário específico no qual realizar a análise de número, pois os números não DID podem ser os mesmos em várias organizações do Microsoft 365 ou do Office 365.  

Esta seção descreve como o proxy SIP localiza o locatário e o usuário e executa a autenticação do SBC na conexão de entrada.

Veja a seguir um exemplo da mensagem de Convite SIP em uma chamada de entrada:

| Nome do parâmetro | Exemplo do valor | 
| :---------------------  |:---------------------- |
| Solicitação de URI | CONVIDAR SIP:+18338006777@SIP.PSTNHUB.MICROSOFT.COM SIP /2.0 |
| Via Header | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards de dados | Max-Forwards:68 |
| Do Header | From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| Para o Header | Para: sip:+183338006777@sbc1.adatum.biz | 
| Header CSeq | CSeq: 1 CONVITE | 
| Header de Contato | Contato: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Ao receber o convite, o proxy SIP executa as seguintes etapas:

1. Verifique o certificado. Na conexão inicial, o serviço roteamento direto leva o nome FQDN apresentado no título contato e o corresponde ao Nome Comum ou Ao Nome Do Assunto Alternativo do certificado apresentado. O nome SBC deve corresponder a uma das seguintes opções:

   - Opção 1. O nome FQDN completo apresentado no título contato deve corresponder ao nome de Nome Comum/Assunto Alternativo do certificado apresentado.  

   - Opção 2.  A parte de domínio do nome FQDN apresentada no header de Contato (por exemplo, adatum.biz do nome FQDN sbc1.adatum.biz) deve corresponder ao valor curinga em Nome Comum/Nome Alternativo do Assunto (por exemplo, *.adatum.biz).

2. Tente encontrar um locatário usando o nome FQDN completo apresentado no header contato.  

   Verifique se o nome FQDN do header de contato (sbc1.adatum.biz) está registrado como um nome DNS em qualquer organização do Microsoft 365 ou office 365. Se encontrado, a olhada do usuário será realizada no locatário que tem o FQDN SBC registrado como um nome de domínio. Se não for encontrado, a Etapa 3 será aplicada.   

3. A etapa 3 só se aplicará se a Etapa 2 falhar. 

   Remova a parte de host do FQDN, apresentada no header de contato (FQDN: sbc12.adatum.biz, após remover a parte do host: adatum.biz) e verifique se esse nome está registrado como um nome DNS em qualquer organização do Microsoft 365 ou office 365. Se encontrado, a procurar usuário será executada neste locatário. Se não for encontrada, a chamada falhará.

4. Usando o número de telefone apresentado no URI-solicitação, execute a procura inversa de número dentro do locatário encontrado na Etapa 2 ou 3. Corresponder o número de telefone apresentado a um URI SIP do usuário no locatário encontrado na etapa anterior.

5. Aplicar configurações de tronco. Encontre os parâmetros definidos pelo administrador do locatário para este SBC.

   A Microsoft não oferece suporte a ter um proxy SIP de terceiros ou o Servidor de Agente de Usuário entre o proxy SIP da Microsoft e o SBC emparelhado, o que pode modificar o URI de Solicitação criado pelo SBC emparelhado.

   Os requisitos para as duas buscas (etapas 2 e 3) necessárias para o cenário em que um SBC está interconectado a muitos locatários (cenário de operadora) são abordados mais adiante neste artigo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisitos detalhados para o header de contato e o URI de solicitação

#### <a name="contact-header"></a>Header de contato

Para todas as mensagens SIP de entrada (OPÇÕES, CONVIDAR) para o proxy SIP da Microsoft, o header de Contato deve ter o FQDN SBC emparelhado no nome de host do URI da seguinte forma:

Sintaxe: Contato: <:telefone ou sip address@FQDN do SBC;transport=tls> 

De acordo [com rfc 3261, seção 11.1,](https://tools.ietf.org/html/rfc3261#section-11.1)um campo de header de contato pode estar presente em uma mensagem OPÇÕES. No Roteamento Direto, o header de contato é obrigatório. Para mensagens CONVIDAR no formato acima, para as mensagens OPÇÕES, o userinfo pode ser removido do URI SIP e somente FQDN enviado no formato da seguinte maneira:

Sintaxe: Contato: <:FQDN do SBC;transport=tls>

Esse nome (FQDN) também deve estar no(s) nome(s) nome(s) do(s) nome(s) comum(s) do certificado apresentado. A Microsoft dá suporte ao uso de valores curinga dos nomes nos campos Nome Comum ou Nome Alternativo de Assunto do certificado.   

O suporte para caracteres curinga está descrito no [RFC 2818, seção 3.1.](https://tools.ietf.org/html/rfc2818#section-3.1) Especificamente:

*"Os nomes podem conter o caractere curinga que é considerado para corresponder a qualquer componente de nome de \* domínio único ou fragmentos de componente. Por exemplo, .a.com corresponde foo.a.com mas não bar.foo.a.com. f.com corresponde foo.com mas não \* \* bar.com".*

Se mais de um valor no título contato apresentado em uma mensagem SIP for enviado pelo SBC, somente a parte FQDN do primeiro valor do título contato será usada.

Como regra geral para Roteamento Direto, é importante que FQDN seja usado para preencher URI SIP em vez de IP. Uma mensagem CONVIDAR ou OPÇÕES de entrada para o Proxy SIP com o header de Contato onde o nome do host é representado por IP e não FQDN, a conexão será recusada com 403 Proibido.

#### <a name="request-uri"></a>Solicitação de URI 

Para todas as chamadas de entrada, o URI-solicitação é usado para corresponder o número de telefone a um usuário.   

Atualmente, o número de telefone deve conter um sinal de mais (+), conforme mostrado no exemplo a seguir. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Considerações sobre Record-Route de contatos e Record-Route dos headers

O proxy SIP precisa calcular o FQDN do próximo salto para novas transações de cliente na caixa de diálogo (por exemplo, Hop ou Convidar outra vez) e ao responder às Opções SIP. Os contatos ou Record-Route são usados. 

De acordo com [o RFC 3261, seção 8.1.1.8,](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)o header de contato é necessário em qualquer solicitação que possa resultar em uma nova caixa de diálogo. A Record-Route é necessária apenas se um proxy quiser permanecer no caminho de solicitações futuras em uma caixa de diálogo. Se um SBC proxy estiver em uso com a Otimização de Mídia [Local](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)para Roteamento Direto, uma rota de registro precisará ser configurada, pois o SBC proxy precisa permanecer na rota. 

A Microsoft recomenda usar somente o header de Contato se um SBC proxy não for usado:

- Por [RFC 3261, seção 20.30,](https://tools.ietf.org/html/rfc3261#section-20.30)Record-Route é usada se um proxy quiser permanecer no caminho de solicitações futuras em uma caixa de diálogo, o que não é essencial se nenhum SBC proxy estiver configurado, pois todo o tráfego passa entre o proxy SIP da Microsoft e o SBC emparelhado. 

- O proxy SIP da Microsoft usa apenas o header de Contato (não Rota de Registro) para determinar o próximo salto ao enviar Opções de ping de saída. Configurar apenas um parâmetro (Contato) em vez de dois (Contato e Rota de Registro) simplifica a administração se um SBC proxy não estiver em uso. 

Para calcular o próximo salto, o proxy SIP usa:

- Prioridade 1. Rota de Registro de nível superior. Se o Record-Route de nível superior contiver o nome FQDN, o nome FQDN será usado para fazer a conexão de entrada de saída na caixa de diálogo.

- Prioridade 2. Header de contato. Se Record-Route não existir, o proxy SIP procurará o valor do header de Contato para fazer a conexão de saída. (Esta é a configuração recomendada.)

Se o contato e Record-Route são usados, o administrador SBC deve manter seus valores idênticos, o que causa sobrecarga administrativa. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso do nome FQDN em Contato ou Record-Route

O uso de um endereço IP não tem suporte em Record-Route ou Contato. A única opção com suporte é um FQDN, que deve corresponder ao Nome Comum ou Ao Nome Alternativo de Assunto do certificado SBC (há suporte para valores curinga no certificado).

- Se um endereço IP for apresentado na Rota de Registro ou contato, a verificação de certificado falhará e a chamada falhará.

- Se o FQDN não corresponder ao valor do Nome Alternativo comum ou de assunto no certificado apresentado, a chamada falhará. 

## <a name="inbound-call-sip-dialog-description"></a>Chamada de entrada: descrição da caixa de diálogo SIP

A tabela a seguir resume as diferenças de fluxo de chamada e as semelhanças entre os modos não bypass e bypass:

| Nome do parâmetro | Modo sem bypass | Bypass mode
| :---------------------  |:---------------------- |:----------------|
| Candidatos à mídia em 183 e 200 mensagens provenientes de | Processadores de mídia | Clientes | 
| Número de 183 mensagens que o SBC pode receber | Um por sessão | Vários | 
| A chamada pode ser com resposta 183 (183) | Sim | Sim |
| A chamada pode ser sem resposta inevida (183) | Sim | Sim |

###  <a name="non-media-bypass-flow"></a>Fluxo de bypass sem mídia

Um usuário do Teams pode ter vários pontos de extremidade ao mesmo tempo. Por exemplo, o cliente Teams para Windows, o cliente Teams para iPhone e o Teams Phone (cliente Do Teams Para Android). Cada ponto de extremidade pode sinalizar um rest HTTP da seguinte forma:

-   Andamento da chamada – convertida pelo proxy SIP para a mensagem SIP 180. Ao receber a mensagem 180, o SBC deve gerar toque local.

-   Resposta de mídia – convertida pelo proxy SIP para a mensagem 183 com candidatos a mídia no protocolo SDP (Session Description Protocol). Ao receber a mensagem 183, o SBC espera se conectar aos candidatos à mídia recebidos na mensagem SDP. 

    > [!NOTE]
    > Em alguns casos, a resposta de mídia pode não ser gerada, e o ponto de extremidade pode responder com a mensagem "Chamada aceita".

-   Chamada aceita – convertida pelo proxy SIP para a mensagem SIP 200 com SDP. Ao receber a mensagem 200, espera-se que o SBC envie e receba mídia de e para os candidatos SDP fornecidos.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Vários pontos de extremidade tocando com resposta inoduz

1.  Ao receber o primeiro Convite do SBC, o proxy SIP envia a mensagem "SIP SIP/2.0 100 Tentando" e notifica todos os pontos de extremidade do usuário final sobre a chamada recebida. 

2.  Após a notificação, cada ponto de extremidade começará a tocar e enviar mensagens de "Andamento da chamada" para o proxy SIP. Como um usuário do Teams pode ter vários pontos de extremidade, o proxy SIP pode receber várias mensagens de Progresso da Chamada.

3.  Para cada mensagem de Progresso da Chamada recebida dos clientes, o proxy SIP converte a mensagem Progresso da Chamada na mensagem SIP "SIP/2.0 180 Tentando". O intervalo para enviar essas mensagens é definido pelo intervalo das mensagens de recebimento do Controlador de Chamada. No diagrama a seguir, há duas 180 mensagens geradas pelo proxy SIP. Essas mensagens vêm dos dois pontos de extremidade do Teams do usuário. Cada cliente tem uma ID de Marca exclusiva.  Todas as mensagens provenientes de um ponto de extremidade diferente serão uma sessão separada (o parâmetro "marca" no campo "Para" será diferente). Mas um ponto de extremidade pode não gerar a mensagem 180 e enviar a mensagem 183 imediatamente, conforme mostrado no diagrama a seguir.

4.  Quando um ponto de extremidade gera uma mensagem de Resposta à Mídia com os endereços IP dos candidatos a mídia do ponto de extremidade, o proxy SIP converte a mensagem recebida em uma mensagem "Andamento da Sessão SIP 183" com o SDP do cliente substituído pelo SDP do Processador de Mídia. No diagrama a seguir, o ponto de extremidade do Fork 2 atendeu à chamada. Se o tronco não for ignorado, a mensagem SIP 183 será gerada apenas uma vez (Ring Bot ou Client End Point). O 183 pode vir em um bifurcação existente ou iniciar um novo.

5.  Uma mensagem de Aceitação de Chamada é enviada com os candidatos finais do ponto de extremidade que aceitaram a chamada. A mensagem Aceitação da Chamada é convertida em mensagem SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta errada](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Vários pontos de extremidade tocando sem resposta errada

1.  Ao receber o primeiro Convite do SBC, o proxy SIP envia a mensagem "SIP SIP/2.0 100 Tentando" e notifica todos os pontos de extremidade do usuário final sobre a chamada recebida. 

2.  Após a notificação, cada ponto de extremidade começará a tocar e enviar a mensagem "Andamento da chamada" para o proxy SIP. Como um usuário do Teams pode ter vários pontos de extremidade, o proxy SIP pode receber várias mensagens de Progresso da Chamada.

3.  Para cada mensagem de Progresso da Chamada recebida dos clientes, o proxy SIP converte a mensagem Progresso da Chamada na mensagem SIP "SIP/2.0 180 Tentando".  O intervalo para enviar as mensagens é definido pelo intervalo de recebimento das mensagens do Controlador de Chamada. Na imagem abaixo, há duas 180 mensagens geradas pelo proxy SIP, o que significa que o usuário entrou em três clientes do Teams e cada cliente envia o andamento da chamada. Cada mensagem será uma sessão separada (parâmetro "marca" no campo "Para" é diferente)

4.  Uma mensagem de Aceitação de Chamada é enviada com os candidatos finais do ponto de extremidade que aceitaram a chamada. A mensagem Aceitação da Chamada é convertida em mensagem SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando sem resposta errada](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Fluxo de bypass de mídia

As mesmas mensagens (100 Tentando, 180, 183) são usadas no cenário de bypass de mídia. 

O esquema a seguir mostra um exemplo do fluxo de chamada ignorado. 

> [!NOTE]
> Os candidatos à mídia podem vir de pontos de extremidade diferentes. 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta errada](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Substitui a opção

O SBC deve dar suporte a Convidar com Substituições.

## <a name="size-of-sdp-considerations"></a>Tamanho das considerações de SDP

A interface de Roteamento Direto pode enviar uma mensagem SIP que exceda 1.500 bytes.  O tamanho do SDP causa isso principalmente. No entanto, se houver um tronco UDP atrás do SBC, ela poderá rejeitar a mensagem se for encaminhada do proxy SIP da Microsoft para o tronco não modificado. A Microsoft recomenda a remoção de alguns valores no SDP no SBC ao enviar a mensagem para os troncos UDP. Por exemplo, os candidatos ICE ou codecs não usadas podem ser removidos.

## <a name="call-transfer"></a>Transferência de chamada

O Roteamento Direto dá suporte a dois métodos para transferência de chamada:

- Opção 1. Os processos proxy SIP fazem referência ao cliente localmente e atuam como Um Árbitro conforme descrito na seção 7.1 da RFC 3892.

  Com essa opção, o proxy SIP encerra a transferência e adiciona um novo Convite. 


- Opção 2.  O proxy SIP envia o SBC Referência e atua como um Transferor conforme descrito na Seção 6 de RFC 5589.

  Com essa opção, o proxy SIP envia um Refere-se ao SBC e espera que o SBC cuide totalmente da Transferência.

O proxy SIP seleciona o método com base nos recursos relatados pelo SBC. Se o SBC indicar que ele dá suporte ao método "Consultar", o proxy SIP usará a Opção 2 para transferências de chamada.

Veja a seguir um exemplo de um SBC enviando a mensagem de que o método Referência tem suporte:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Se o SBC não indicar que Referir-se como um método com suporte, o Roteamento Direto usará a Opção 1 (proxy SIP atua como Um Árbitro). O SBC também deve sinalizar que é compatível com o método Notificar:

Exemplo de SBC indicando que não há suporte para o método Referência:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Processos proxy SIP fazem referência ao cliente localmente e atua como Um Árbitro

Se o SBC indicar que não há suporte para o método Referência, o proxy SIP atuará como Um Árbitro. 

A solicitação de Referência que vem do cliente será encerrada no proxy SIP. (A solicitação de Referência do cliente é mostrada como "Transferência de chamada para Dave" no diagrama a seguir.  Para saber mais, confira a seção 7.1 do [RFC 3892.](https://www.ietf.org/rfc/rfc3892.txt) 

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta errada](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>O proxy SIP envia o serviço Consultar o SBC e atua como um Transferor

Este é o método preferencial para transferências de chamada e é obrigatório para dispositivos que procuram certificação de bypass de mídia. A Transferência de Chamada sem que o SBC possa lidar com Referência não tem suporte no modo de bypass de mídia. 

O padrão é explicado na Seção 6 da RFC 5589. As RFCs relacionadas são:

- [Controle de chamada sip (Session Initiation Protocol) - Transfer](https://tools.ietf.org/html/rfc5589)

- ["Substitui" o Header do Protocolo de Iniciação de Sessão (SIP)](https://tools.ietf.org/html/rfc3891)

- [Mecanismo "Referred-by" (SIP) do Session Initiation Protocol](https://tools.ietf.org/html/rfc3892)

Essa opção supõe que o proxy SIP atua como um Transferor e envia uma mensagem De referência para o SBC. O SBC atua como um Transferee e lida com o serviço Consultar para gerar uma nova oferta de transferência. Há dois casos possíveis:

- A chamada é transferida para um participante PSTN externo. 
- A chamada é transferida de um usuário do Teams para outro usuário do Teams no mesmo locatário por meio do SBC. 

Se a chamada for transferida de um usuário do Teams para outro por meio do SBC, deverá ser emitido um novo convite (iniciar uma nova caixa de diálogo) para o destino de transferência (o usuário do Teams) usando as informações recebidas na mensagem Consultar. 

Para preencher os campos Para/Transferor para a transação da solicitação internamente, o proxy SIP precisa transmitir essas informações dentro dos headers REFER-TO/REFERRED-BY. 

O proxy SIP formará o REFER-TO como um URI SIP composto de um FQDN proxy SIP no nome do host e um dos seguintes:

- Um número de telefone E.164 na parte de nome de usuário do URI, caso o destino da transferência seja um número de telefone, ou

- Parâmetros x-m e x-t codificando a MRI de destino de transferência total e a ID do locatário, respectivamente 

O header REFERRED-BY é um URI SIP com MRI transferor codificado nele, bem como ID de locatário do transferor e outros parâmetros de contexto de transferência, conforme mostrado na tabela a seguir:

| Parâmetro | Valor | Descrição |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Ressonância | MRI completa do destino de transferência/transferência, conforme preenchido por CC |
| x-t | ID do locatário | ID opcional de locatário x-t preenchida por CC |
| x-ti | ID de Correlação do Transferor | ID de correlação da chamada para o transferidor |
| x-tt | Transferir URI de chamada de destino | URI de substituição de chamada codificado |

O tamanho do Refer Header pode ter até 400 símbolos nesse caso. O SBC deve dar suporte ao tratamento de Encaminhar mensagens com tamanho de até 400 símbolos.

> [!div class="mx-imgBorder"]
> ![Diagrama mostrando vários pontos de extremidade tocando com resposta errada](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Temporizador de sessão

O proxy SIP dá suporte (sempre oferece) o Temporizador de Sessão em chamadas não ignorada, mas não o oferece em chamadas ignorada. O uso do Temporizador de Sessão pelo SBC não é obrigatório.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso do parâmetro Request-URI user=phone

O proxy SIP analisa o URI-solicitação e, se o parâmetro usuário=telefone estiver presente, o serviço lidará com o Request-URI como um número de telefone, correspondendo o número a um usuário. Se o parâmetro não estiver presente, o proxy SIP aplicará heurísticas para determinar o tipo de usuário Request-URI (número de telefone ou um endereço SIP).

A Microsof recomenda sempre aplicar o parâmetro user=phone para simplificar o processo de configuração de chamada.

## <a name="history-info-header"></a>History-Info de dados

O History-Info é usado para retar as solicitações SIP e "fornecer(s) um mecanismo padrão para capturar as informações do histórico de solicitações para habilitar uma ampla variedade de serviços para redes e usuários finais". Para obter mais informações, consulte [RFC 4244 – Seção 1.1.](http://www.ietf.org/rfc/rfc4244.txt) Para o Microsoft Phone System, esse header é usado em cenários de Simulring e Encaminhamento de Chamadas.  

Se você enviar, a History-Info será habilitada da seguinte forma:

- O proxy SIP inserirá um parâmetro que contém o número de telefone associado em entradas individuais History-Info que compõem o History-Info de texto enviado para o Controlador PSTN.  Usando apenas entradas que têm o parâmetro de número de telefone, o Controlador PSTN recriará um novo History-Info e o transmitirá para o provedor de tronco SIP por meio do proxy SIP.

- History-Info será adicionado para casos de toque simultâneo e encaminhamento de chamada.

- History-Info não será adicionado para casos de transferência de chamada.

- Uma entrada de histórico individual no header History-Info terá o parâmetro de número de telefone fornecido combinado com o FQDN de Roteamento Direto (sip.pstnhub.microsoft.com) definido como a parte host do URI; um parâmetro de 'usuário=telefone' será adicionado como parte do URI SIP.  Quaisquer outros parâmetros associados ao History-Info original, exceto os parâmetros de contexto do telefone, serão passados no History-Info de texto.  

  > [!NOTE]
  > Entradas privadas (conforme determinado pelos mecanismos definidos na Seção 3.3 da RFC 4244) serão encaminhadas, assim como porque o provedor de tronco SIP é um ponto confiável.

- O History-Info de entrada é ignorado.

A seguir está o formato do header De informações do histórico enviado pelo proxy SIP:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Se a chamada foi redirecionada várias vezes, as informações sobre cada redirecionamento serão incluídas com o motivo apropriado em ordem cronológica.


Exemplo de header:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

A History-Info é protegida por um mecanismo TLS obrigatório. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Conexão SBC com Roteamento Direto e mecanismo de failover

Consulte o mecanismo de failover da seção para sinalização SIP no [Plano de Roteamento Direto.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)

## <a name="retry-after"></a>Retry-After

Se um datacenter de Roteamento Direto estiver ocupado, o serviço poderá enviar uma mensagem Retry-After com um intervalo de um segundo para o SBC. Quando o SBC receber uma mensagem 503 com um Retry-After em resposta a um CONVITE, o SBC deverá encerrar essa conexão e tentar o próximo datacenter da Microsoft disponível. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Reinicialização ice: a chamada de bypass de mídia transferida para um ponto de extremidade que não dá suporte a bypass de mídia

O SBC deve dar suporte a reinicializações ice conforme descrito no [RFC 5245, seção 9.1.1.1.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)

A reinicialização no Roteamento Direto é implementada de acordo com os seguintes parágrafos da RFC:

*Para reiniciar a ICE, um agente DEVE alterar o ice-pwd e o ice-rebootag do fluxo de mídia em uma oferta.  Observe que é permitido usar um atributo de nível de sessão em uma oferta, mas para fornecer o mesmo ice-pwd ou ice-campusag como um atributo de nível de mídia em uma oferta subsequente.  Isso não é uma alteração na senha, apenas uma alteração em sua representação e não causa uma reinicialização ICE.*

*Um agente define o restante dos campos no SDP para esse fluxo de mídia como seria em uma oferta inicial desse fluxo de mídia (consulte a Seção 4.3).  Consequentemente, o conjunto de candidatos pode incluir alguns, nenhum ou todos os candidatos anteriores para esse fluxo e PODE incluir um conjunto totalmente novo de candidatos reunidos conforme descrito na Seção 4.1.1.*

Se a chamada foi estabelecida inicialmente com bypass de mídia e a chamada é transferida para um cliente do Skype for Business, o Roteamento Direto precisa inserir um Processador de Mídia, isso porque o Roteamento Direto não pode ser usado com um cliente Skype for Business com bypass de mídia. O Roteamento Direto inicia o processo de reinicialização ICE, alterando o ice-pwd e o ice-rebootag e oferecendo novos candidatos à mídia em um reinvite. 


