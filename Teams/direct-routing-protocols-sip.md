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
description: Protocolos de roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ab2203544e1d0e4d8679a4ad8107c2048e5b3b8
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065671"
---
# <a name="direct-routing---sip-protocol"></a>Roteamento direto-protocolo SIP

Este artigo descreve como o roteamento direto implementa o protocolo de iniciação de sessão (SIP). Para direcionar corretamente o tráfego entre um controlador de borda de sessão (SBC) e o proxy SIP, alguns parâmetros de SIP devem ter valores específicos. Este artigo destina-se a administradores de voz responsáveis por configurar a conexão entre o SBC local e o serviço de proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Processando a solicitação de entrada: encontrando o locatário e o usuário

Em uma chamada de entrada, o proxy SIP precisa encontrar o locatário para o qual a chamada está destinada e localizar o usuário específico nesse locatário. O administrador do locatário pode configurar números não-DID, por exemplo, + 1001, em vários locatários. Portanto, é importante localizar o locatário específico no qual executar a pesquisa de número, pois os números não-DID podem ser iguais em vários locatários do Office 365.  

Esta seção descreve como o proxy SIP localiza o locatário e o usuário e executa a autenticação do SBC na conexão de entrada.

Veja a seguir um exemplo da mensagem de convite SIP em uma chamada recebida:

| Nome do parâmetro | Exemplo do valor | 
| :---------------------  |:---------------------- |
| Solicitação-URI | CONVIDAR sip:+18338006777@sip.pstnhub.microsoft.com SIP/2,0 |
| Via cabeçalho | Via: SIP/2.0/TLS sbc1. adatum. biz: 5058; alias; Branch = z9hG4bKac2121518978 | 
| Cabeçalho Max-Forwards | Máx-forwards: 68 |
| Do cabeçalho | Do cabeçalho de: <SIP: 7168712781@sbc1. adatum. biz; Transport = UDP; tag = 1c747237679 |
| Para cabeçalho | Para: sip:+183338006777@sbc1.adatum.biz | 
| Cabeçalho CSeq | CSeq: 1 convite | 
| Cabeçalho de contato | Contato: <SIP: 68712781@sbc1. adatum. biz; Transport = TLS> | 

Ao receber o convite, o proxy SIP executa as seguintes etapas:

1. Verifique o certificado. Na conexão inicial, o serviço de roteamento direto usa o nome FQDN apresentado no cabeçalho do contato e o corresponde ao nome comum ou ao nome alternativo do requerente do certificado apresentado. O nome SBC deve corresponder a uma das seguintes opções:

   - Opção 1. O nome FQDN completo apresentado no cabeçalho do contato deve corresponder ao nome comum/nome alternativo do assunto do certificado apresentado.  

   - Opção 2.  A parte do domínio do nome FQDN apresentada no cabeçalho do contato (por exemplo, adatum.biz do nome FQDN sbc1.adatum.biz) deve coincidir com o valor curinga em nome comum/nome alternativo do assunto (por exemplo, *. adatum.biz).

2. Tente localizar um locatário usando o nome FQDN completo apresentado no cabeçalho do contato.  

   Verifique se o nome FQDN do cabeçalho do contato (sbc1.adatum.biz) está registrado como um nome DNS em qualquer locatário do Office 365. Se encontrado, a pesquisa do usuário é realizada no locatário que tem o FQDN do SBC registrado como um nome de domínio. Se não for encontrado, a etapa 3 será aplicada.   

3. A etapa 3 aplica-se apenas se a etapa 2 falhar. 

   Remova a porção do host do FQDN, apresentada no cabeçalho do contato (FQDN: sbc12.adatum.biz, após remover a porção do host: adatum.biz) e verifique se esse nome está registrado como um nome DNS em qualquer locatário do Office 365. Se encontrado, a pesquisa do usuário será realizada nesse locatário. Se não for encontrado, a chamada falhará.

4. Usando o número de telefone apresentado na solicitação-URI, execute a pesquisa de número reverso dentro do locatário localizado na etapa 2 ou 3. Compare o número de telefone apresentado a um URI de SIP do usuário dentro do locatário encontrado na etapa anterior.

5. Aplicar configurações de tronco. Localize os parâmetros definidos pelo administrador de locatários para este SBC.

   A Microsoft não oferece suporte a um servidor de proxy SIP ou de agente de usuário de terceiros entre o proxy SIP da Microsoft e o SBC emparelhado, que pode modificar o URI de solicitação criado pelo SBC emparelhado.

   Os requisitos para as duas pesquisas (etapas 2 e 3) necessárias para o cenário em que um SBC está interconectado a vários locatários (cenário de transportadora) são abordados mais adiante neste artigo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisitos detalhados para cabeçalho e solicitação-URI de contato

#### <a name="contact-header"></a>Cabeçalho de contato

Para todas as chamadas recebidas para o proxy SIP da Microsoft, o cabeçalho do contato deve ter o o FQDN do SBC emparelhado no nome do host do URI da seguinte maneira:

Sintaxe: contato: <SIP: telefone ou SIP address@FQDN do SBC; Transport = TLS> 

Esse nome também deve estar no (s) campo (s) nome (s) nome (s) do requerente ou nome alternativo do certificado. A Microsoft oferece suporte ao uso de valores curinga do (s) nome (s) nos campos nome comum ou nome alternativo do assunto do certificado.   

O suporte para caracteres curinga está descrito no [RFC 2818, seção 3,1](https://tools.ietf.org/html/rfc2818#section-3.1). Criadas

*"Os nomes podem conter o caractere \* curinga que é considerado para corresponder a um único componente de nome de domínio ou fragmento de componente. Por exemplo, \*. a.com corresponde a foo.a.com, mas não bar.foo.a.com. f\*. com corresponde a foo.com, mas não bar.com. "*

Se mais de um valor no cabeçalho do contato apresentado em uma mensagem SIP for enviado pelo SBC, somente a parte FQDN do primeiro valor do cabeçalho do contato será usada.

#### <a name="request-uri"></a>Solicitação-URI 

Para todas as chamadas recebidas, o URI de solicitação é usado para corresponder ao número de telefone a um usuário.   

Atualmente, o número de telefone deve conter um sinal de adição (+), conforme mostrado no exemplo a seguir. 

```
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Considerações de cabeçalhos de rota de contato e registro

O proxy SIP precisa calcular o próximo FQDN de salto para as novas transações de cliente em caixa de diálogo (por exemplo, até mais ou convidar) e ao responder às opções de SIP. É usado o contato ou a rota de registro. 

De acordo com a RFC 3261, o cabeçalho do contato é necessário em qualquer solicitação que pode resultar em uma nova caixa de diálogo. A rota de registro será necessária apenas se um proxy quiser permanecer no caminho de solicitações futuras em uma caixa de diálogo. 

A Microsoft recomenda usar somente o cabeçalho do contato pelos seguintes motivos:

- Por RFC 3261, a rota de registro é usada se um proxy quiser permanecer no caminho de solicitações futuras em uma caixa de diálogo, o que não é essencial, pois todo o tráfego vai entre o proxy SIP da Microsoft e o SBC emparelhado. Não há necessidade de um servidor proxy intermediário entre o SBC e o proxy SIP da Microsoft.

- O proxy SIP da Microsoft usa apenas o cabeçalho do contato (não o caminho do registro) para determinar o próximo salto ao enviar opções de ping de saída. Configurar apenas um parâmetro (contato) em vez de dois (contato e rota de registro) simplifica a administração.

Para calcular o próximo salto, o proxy SIP usa:

- Prioridade 1. Rota de registro de nível superior. Se a rota de registro de nível superior contiver o nome FQDN ou IP, o nome FQDN ou o IP será usado para fazer a conexão de entrada na caixa de diálogo.

- Prioridade 2. Cabeçalho do contato. Se a rota de registro não existir, o proxy SIP irá procurar o valor do cabeçalho do contato para fazer a conexão de saída. (Essa é a configuração recomendada.)

Se tanto o contato quanto a rota de registro forem usados, o administrador de SBC deve manter os valores idênticos, o que causa sobrecarga administrativa. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso do nome FQDN em contato ou rota de registro

Não há suporte para o uso de um endereço IP em Record-Route ou Contact. A única opção com suporte é um FQDN, que deve corresponder ao nome comum ou ao nome alternativo do requerente do certificado SBC (há suporte para valores curinga no certificado).

- Se um endereço IP for apresentado em Record-Route ou Contact, a verificação do certificado falhará e a chamada falhará.

- Se o FQDN não coincidir com o valor do nome comum ou alternativo do sujeito no certificado apresentado, a chamada falhará. 

## <a name="inbound-call-sip-dialog-description"></a>Chamada recebida: Descrição da caixa de diálogo SIP

A tabela a seguir resume as diferenças de fluxo de chamada e as semelhanças entre os modos não bypass e bypass:

| Nome do parâmetro | Modo não bypass | Modo ignorar
| :---------------------  |:---------------------- |:----------------|
| Candidatos a mídia em 183 e 200 mensagens vindas de | Processadores de mídia | Clientes | 
| Número de mensagens 183 que o SBC pode receber | Um por sessão | Muitos | 
| A chamada pode ter uma resposta provisionada (183) | Sim | Sim |
| A chamada pode ser sem resposta provisório (183) | Sim | Sim |

###  <a name="non-media-bypass-flow"></a>Fluxo de bypass de não mídia

Um usuário do teams pode ter vários pontos de extremidade ao mesmo tempo. Por exemplo, Teams para cliente Windows, Team para cliente iPhone e telefone do Teams (cliente Android do Teams). Cada ponto de extremidade pode sinalizar um HTTP REST da seguinte maneira:

-   Andamento da chamada – convertido pelo proxy SIP para a mensagem SIP 180. Na recepção da mensagem 180, o SBC deve gerar um toque local.

-   Resposta de mídia – convertida pelo proxy SIP para a mensagem 183 com candidatos a mídia no protocolo de descrição de sessão (SDP). Na recepção da mensagem 183, o SBC espera a conexão com os candidatos à mídia recebidos na mensagem SDP. Observe que, em alguns casos, a resposta de mídia pode não ser gerada, e o ponto de extremidade pode atender com a mensagem "chamada aceita".

-   Chamada aceita – convertida pelo proxy SIP para a mensagem SIP 200 com SDP. Na recepção da mensagem 200, o SBC é esperado para enviar e receber mídia para e dos candidatos SDP fornecidos.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Vários pontos de extremidade em toque com resposta provisório

1.  Ao receber o primeiro convite do SBC, o proxy SIP envia a mensagem "SIP SIP/2.0 100 tentando" e notifica todos os pontos de extremidade do usuário final sobre a chamada recebida. 

2.  Durante a notificação, cada ponto de extremidade começará a tocar e enviar mensagens de "andamento da chamada" ao proxy SIP. Como um usuário do teams pode ter vários pontos de extremidade, o proxy SIP pode receber várias mensagens de progresso de chamada.

3.  Para cada mensagem de progresso de chamada recebida dos clientes, o proxy SIP converte a mensagem de progresso da chamada na mensagem SIP "SIP SIP/2.0 180 tentando". O intervalo para enviar tais mensagens é definido pelo intervalo das mensagens de recebimento do controlador de chamada. No diagrama a seguir, há 2 180 mensagens geradas pelo proxy SIP. Essas mensagens são provenientes dos dois pontos de extremidade das equipes do usuário. Cada um dos clientes tem uma ID de marca exclusiva.  Todas as mensagens recebidas de um ponto de extremidade diferente serão uma sessão separada (o parâmetro "tag" no campo "para" será diferente). Mas um ponto de extremidade pode não gerar a mensagem 180 e enviar a mensagem 183 imediatamente, conforme mostrado no diagrama a seguir.

4.  Depois que um ponto de extremidade gerar uma mensagem de resposta de mídia com os endereços IP dos candidatos à mídia do ponto de extremidade, o proxy SIP converterá a mensagem recebida para uma mensagem "andamento da sessão SIP 183" com o SDP do cliente substituído pelo SDP do processador de mídia. No diagrama a seguir, o ponto de extremidade da bifurcação 2 atendeu na chamada. Se o tronco não for bypass, a mensagem SIP do 183 será gerada apenas uma vez (um bot ou ponto final do cliente). O 183 pode vir em uma bifurcação existente ou iniciar uma nova.

5.  Uma mensagem de aceitação de chamadas é enviada com os candidatos finais da empresa que aceitou a chamada. A mensagem de aceitação da chamada é convertida para a mensagem SIP 200. 

![Diagrama mostrando vários pontos de extremidade tocando com resposta de provisório](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Vários pontos de extremidade tocando sem resposta provisório

1.  Ao receber o primeiro convite do SBC, o proxy SIP envia a mensagem "SIP SIP/2.0 100 tentando" e notifica todos os pontos de extremidade do usuário final sobre a chamada recebida. 

2.  Após a notificação, cada ponto de extremidade começará a tocar e enviar a mensagem "andamento da chamada" ao proxy SIP. Como um usuário do teams pode ter vários pontos de extremidade, o proxy SIP pode receber várias mensagens de progresso de chamada.

3.  Para cada mensagem de progresso de chamada recebida dos clientes, o proxy SIP converte a mensagem de progresso da chamada na mensagem SIP "SIP SIP/2.0 180 tentando".  O intervalo para enviar as mensagens é definido pelo intervalo de recebimento das mensagens do controlador de chamada. Na imagem abaixo, há 2 180 mensagens geradas pelo proxy SIP, o que significa que o usuário se registrou em três clientes do Teams e cada cliente envia o andamento da chamada. Todas as mensagens serão uma sessão separada ("marca" de parâmetro no campo "para" é diferente)

4.  Uma mensagem de aceitação de chamadas é enviada com os candidatos finais da empresa que aceitou a chamada. A mensagem de aceitação da chamada é convertida para a mensagem SIP 200. 

![Diagrama mostrando vários pontos de extremidade tocando sem resposta de provisório](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Fluxo de bypass de mídia

As mesmas mensagens (100 tentando, 180, 183) são usadas no cenário de bypass de mídia. 

O esquema abaixo mostra um exemplo do fluxo de chamadas de ignorar chamadas. Observe que os candidatos à mídia podem vir de diferentes pontos de extremidade. 

![Diagrama mostrando vários pontos de extremidade tocando com resposta de provisório](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opção substitui

O SBC deve dar suporte a INVITE com substituições.

## <a name="size-of-sdp-considerations"></a>Tamanho das considerações do SDP

A interface de roteamento direto pode enviar uma mensagem SIP excedendo 1.500 bytes.  O tamanho do SDP causa principalmente isso. No entanto, se houver um tronco UDP por trás do SBC, ele pode rejeitar a mensagem se ele for encaminhado do proxy Microsoft SIP para o tronco não modificado. A Microsoft recomenda a remoção de alguns valores no SDP no SBC ao enviar a mensagem para os troncos UDP. Por exemplo, os candidatos à ICE ou codecs não utilizados podem ser removidos.

## <a name="call-transfer"></a>Transferência de chamadas

O roteamento direto dá suporte a dois métodos para transferência de chamadas:

- Opção 1. Os processos de proxy SIP se referem ao cliente localmente e atuam como um referee, conforme descrito na seção 7,1 da RFC 3892.

  Com essa opção, o proxy SIP encerra a transferência e adiciona um novo convite. 


- Opção 2.  O proxy SIP envia a referência ao SBC e age como um transferíment como se descrever na seção 6 da RFC 5589.

  Com essa opção, o proxy SIP envia uma referência ao SBC e espera que o SBC manipule a transferência totalmente.

O proxy SIP seleciona o método com base nas funcionalidades relatadas pelo SBC. Se o SBC indicar que ele dá suporte ao método "refer", o proxy SIP usará a opção 2 para transferências de chamadas.

Veja a seguir um exemplo de um SBC que envia a mensagem informando que o método refer tem suporte:

```
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Se o SBC não indicar que se referem ao método com suporte, o roteamento direto usará a opção 1 (o proxy SIP age como um referee). O SBC também deve sinalizar que ele dá suporte ao método Notify:

Exemplo de SBC que indica que não há suporte para o método de referência:

```
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Os processos de proxy SIP se referem ao cliente localmente e atuam como um referee

Se o SBC indicou que o método refer não é compatível, o proxy SIP atua como um referee. 

A solicitação de referência que vem do cliente será terminada no proxy SIP. (A solicitação de referência do cliente é mostrada como "transferência de chamada para Dave" no diagrama a seguir.  Para obter mais informações, consulte a seção 7,1 da [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

![Diagrama mostrando vários pontos de extremidade tocando com resposta de provisório](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Proxy SIP envie a referência ao SBC e age como um transferíment

Esse é o método preferido para transferências de chamadas e é obrigatório para dispositivos que buscam certificação bypass de mídia. A transferência de chamadas sem o SBC não pode fazer referência não é compatível com o modo de bypass de mídia. 

O padrão é explicado na seção 6 da RFC 5589. Os RFCs relacionados são:

- [Controle de chamada SIP (Session Initiation Protocol)-transferência](https://tools.ietf.org/html/rfc5589)

- [Cabeçalho "substitui" do protocolo de início de sessão (SIP)](https://tools.ietf.org/html/rfc3891)

- [Mecanismo de "referido por" de protocolo de início de sessão (SIP)](https://tools.ietf.org/html/rfc3892)

Essa opção pressupõe que o proxy SIP atue como um transferíment e envia uma mensagem de referência ao SBC. O SBC atua como um transferida e manipula a referência para gerar uma nova oferta para transferência. Há dois casos possíveis:

- A chamada é transferida para um participante PSTN externo. 
- A chamada é transferida de um usuário do teams para outro usuário do teams no mesmo locatário por meio do SBC. 

Se a chamada for transferida de um usuário do teams para outro por meio do SBC, espera-se que o SBC emita um novo Invite (iniciar uma nova caixa de diálogo) para o destino da transferência (o usuário do Teams) usando as informações recebidas na mensagem de referência. 

Para preencher os campos para/transferíment para a transação da solicitação internamente, o proxy SIP precisa transmitir essas informações dentro dos cabeçalhos refere-se a/REFERENCIAdo. 

O proxy SIP formará a opção fazer como um URI SIP formado por um FQDN do proxy SIP no nome do host e qualquer um dos seguintes:

- Um número de telefone E. 164 na parte username do URI, caso o destino da transferência seja um número de telefone ou

- parâmetros x-m e x-t codificando a ID de locatário e MRI de destino da transferência completa, respectivamente 

O cabeçalho REFERENCIAdo é um URI de SIP com o transferível MRI codificado, bem como a ID do locatário do transportador e outros parâmetros de contexto de transferência, conforme mostrado na tabela a seguir:

| Parâmetro | Valor | Descrição |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | ENCONTRA | MRI completa do transportador/destino de transferência conforme preenchido pelo CC |
| x-t | ID do locatário | ID de locatário opcional de ID de locatário x-t como preenchido pelo CC |
| x-ti | ID de correlação do transportador | ID de correlação da chamada para o transferidar |
| x-TT | URI da chamada de destino de transferência | URI de substituição de chamadas codificadas |

Nesse caso, o tamanho do cabeçalho de referência pode ter até 400 símbolos. O SBC deve dar suporte a manipulação de mensagens com tamanho de até 400 símbolos.

![Diagrama mostrando vários pontos de extremidade tocando com resposta de provisório](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Temporizador de sessão

O proxy SIP dá suporte (sempre oferece) o temporizador da sessão em chamadas sem bypass, mas não o oferece em chamadas ignoradas. O uso do temporizador de sessão pelo SBC não é obrigatório.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso do parâmetro Request-URI User = Phone

O proxy SIP analisa o URI da solicitação e, se o parâmetro User = Phone estiver presente, o serviço manipulará o URI da solicitação como um número de telefone, correspondendo ao número para um usuário. Se o parâmetro não estiver presente, o proxy SIP aplica heurística para determinar o tipo de usuário da solicitação-URI (número de telefone ou endereço SIP).

Microsof recomenda sempre aplicar o parâmetro User = Phone para simplificar o processo de configuração de chamadas.

## <a name="history-info-header"></a>Histórico-cabeçalho de informações

O cabeçalho histórico-informações é usado para redirecionar solicitações SIP e "fornecer (s) um mecanismo padrão para capturar as informações do histórico de solicitações para habilitar uma ampla variedade de serviços para redes e usuários finais." Para obter mais informações, consulte [RFC 4244 – seção 1,1](http://www.ietf.org/rfc/rfc4244.txt). Para o Microsoft Phone System, esse cabeçalho é usado nos cenários SimulRing e encaminhamento de chamadas.  

Se estiver enviando, o histórico-informações será habilitado da seguinte maneira:

- O proxy SIP inserirá um parâmetro contendo o número de telefone associado em entradas do histórico-informações individuais que compõem o cabeçalho do histórico-informações enviado ao controlador PSTN.  Usando somente entradas com o parâmetro número de telefone, o controlador PSTN recriará um novo cabeçalho de informações de histórico e passará para o provedor de tronco SIP via proxy SIP.

- History-info header será adicionado para casos de toque simultâneo e encaminhamento de chamadas.

- History-info header não será adicionado para casos de transferência de chamadas.

- Uma entrada de histórico individual no cabeçalho reconstruído histórico de informações terá o parâmetro de número de telefone fornecido combinado com o FQDN (sip.pstnhub.microsoft.com) definido como a parte do host do URI; um parâmetro de "User = Phone" será adicionado como parte do URI SIP.  Todos os outros parâmetros associados ao cabeçalho do histórico original-informações, exceto para parâmetros de contexto de telefone, serão passados no cabeçalho reconstruído histórico-informações.  Observe que as entradas privadas (conforme determinado pelos mecanismos definidos na seção 3,3 da RFC 4244) serão encaminhadas como ocorre porque o provedor de tronco SIP é um par confiável.

- Histórico de entrada-as informações são ignoradas.

Veja a seguir o formato do cabeçalho do histórico de informações enviado pelo proxy SIP:

```
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Se a chamada foi redirecionada várias vezes, as informações sobre cada redirecionamento são incluídas com o motivo apropriado em ordem cronológica.


Exemplo de cabeçalho:

```
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

O histórico-informações é protegido por um mecanismo TLS obrigatório. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Conexão SBC para mecanismo de roteamento direto e de failover

Consulte o mecanismo de failover de seção para sinalização SIP em [planejar para roteamento direto](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Repetir-após

Se um datacenter de roteamento direto estiver ocupado, o serviço poderá enviar uma mensagem Retry-After com um intervalo de um segundo para o SBC. Quando o SBC recebe uma mensagem 503 com um cabeçalho Retry-After em resposta a um convite, o SBC deve terminar essa conexão e experimentar o próximo Datacenter da Microsoft disponível. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Reinicialização do ICE: ignorar chamada de mídia transferida para um ponto de extremidade que não é compatível com bypass de mídia

O SBC deve dar suporte a reinícios de ICE conforme descrito em [RFC 5245, seção 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

A reinicialização no roteamento direto é implementada de acordo com os seguintes parágrafos da RFC:

*Para reiniciar o ICE, um agente deve alterar o Ice-pwd e o Ice-ufrag para o fluxo de mídia em uma oferta.  Observe que é permitido usar um atributo no nível da sessão em uma oferta, mas fornecer o mesmo Ice-pwd ou Ice-ufrag como um atributo em nível de mídia em uma oferta subsequente.  Isso não é uma alteração na senha, apenas uma alteração em sua representação e não causa uma reinicialização do ICE.*

*Um agente define o restante dos campos no SDP para este fluxo de mídia como seria uma oferta inicial desse fluxo de mídia (consulte a seção 4,3).  Consequentemente, o conjunto de candidatos pode incluir alguns, nenhum ou todos os candidatos anteriores desse fluxo e pode incluir um conjunto totalmente novo de candidatos coletados, conforme descrito na seção 4.1.1.*

Se a chamada foi inicialmente estabelecida com o bypass de mídia, e a chamada for transferida para um cliente Skype for Business, o roteamento direto precisará inserir um processador de mídia--isso ocorre porque o roteamento direto não pode ser usado com um cliente Skype for Business com o bypass de mídia. O direcionamento direto inicia o processo de reinicialização ICE alterando o Ice-pwd e Ice-ufrag e oferecendo novos candidatos à mídia em um convite. 


