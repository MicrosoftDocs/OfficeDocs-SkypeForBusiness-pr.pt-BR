---
title: Planejar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como planejar o bypass de mídia com o Roteamento Direto do Sistema Telefônico, o que permite encurtar o caminho do tráfego de mídia e melhorar o desempenho.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea92103789927d35ae8bdd317987f32863d4d74e
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981786"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planejar o bypass de mídia com Roteamento Direto

## <a name="about-media-bypass-with-direct-routing"></a>Sobre o bypass de mídia com o Roteamento Direto

O bypass de mídia permite reduzir o caminho do tráfego de mídia e reduzir o número de saltos em trânsito para melhor desempenho. Com o bypass de mídia, a mídia é mantida entre o SBC (Controlador de Borda de Sessão) e o cliente em vez de enviá-la por meio do Sistema de Telefone da Microsoft. Para configurar o bypass de mídia, o SBC e o cliente devem estar no mesmo local ou rede.

Você pode controlar o bypass de mídia para cada SBC usando o comando **Set-CSOnlinePSTNGateway** com o parâmetro **-MediaBypass** definido como true ou false. Se você habilitar o bypass de mídia, isso não significa que todo o tráfego de mídia permanecerá dentro da rede corporativa. Este artigo descreve o fluxo de chamadas em cenários diferentes.

Os diagramas abaixo ilustram a diferença no fluxo de chamadas com e sem bypass de mídia.

Sem bypass de mídia, quando um cliente faz ou recebe uma chamada, sinalização e fluxo de mídia entre o SBC, o Sistema de Telefone microsoft e o cliente do Teams, conforme mostrado no seguinte diagrama:

> [!div class="mx-imgBorder"]
> ![Mostra a sinalização e o fluxo de mídia sem bypass de mídia.](media/direct-routing-media-bypass-1.png)


Mas vamos supor que um usuário esteja no mesmo prédio ou rede que o SBC. Por exemplo, suponha que um usuário que está em um prédio em Frankfurt faça uma chamada para um usuário PSTN: 

- **Sem bypass de mídia**, a mídia fluirá por Amsterdã ou Dublin (onde os datacenters da Microsoft são implantados) e retornará ao SBC em Frankfurt. 

  O datacenter na Europa é selecionado porque o SBC está na Europa e a Microsoft usa o datacenter mais próximo do SBC. Embora essa abordagem não afete a qualidade da chamada devido à otimização do fluxo de tráfego nas redes da Microsoft na maioria das geografias, o tráfego tem um loop desnecessário.     

- **Com o bypass de mídia**, a mídia é mantida diretamente entre o usuário do Teams e o SBC, conforme mostrado no seguinte diagrama:

  > [!div class="mx-imgBorder"]
  > ![Mostra a sinalização e o fluxo de mídia com bypass de mídia.](media/direct-routing-media-bypass-2.png)

O bypass de mídia aproveita protocolos chamados ICE (Interactive Connectivity Establishment) no cliente do Teams e ice lite no SBC. Esses protocolos permitem que o Roteamento Direto use o caminho de mídia mais direto para uma qualidade ideal. ICE e ICE Lite são padrões WebRTC. Para obter informações detalhadas sobre esses protocolos, consulte RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Fluxo de chamadas e planejamento de firewall

O fluxo de chamadas e o planejamento de firewall dependem se o usuário tem acesso direto ao endereço IP público do SBC e se o usuário está dentro ou fora da rede.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Fluxo de chamadas se o usuário tiver acesso direto ao endereço IP público do SBC

Se o usuário tiver acesso direto ao endereço IP público do SBC, o fluxo de chamadas será o seguinte:

- Para ignorar a mídia, o cliente do Teams deve ter acesso ao endereço IP público do SBC mesmo de uma rede interna. Se a mídia direta não for desejada, a mídia poderá fluir por meio de Retransmissões de Transporte.

- Essa é a solução recomendada quando um usuário está no mesmo edifício e/ou rede que o SBC – remova os componentes do Microsoft Cloud do caminho de mídia.

- A sinalização sempre flui pela nuvem da Microsoft.

O diagrama a seguir mostra o fluxo de chamadas quando o bypass de mídia está habilitado, o cliente é interno e o cliente pode alcançar o endereço IP público do SBC (mídia direta): 

- As setas e os valores numéricos dos caminhos estão de acordo com os [fluxos de chamada do Microsoft Teams](./microsoft-teams-online-call-flows.md).

- A sinalização SIP sempre usa os caminhos 4 e 4' (dependendo da direção do tráfego). A mídia permanece local e segue o caminho 5b.

> [!div class="mx-imgBorder"]
> ![Mostra o fluxo de chamadas com o Bypass de Mídia habilitado, o cliente é interno.](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Fluxo de chamadas se o usuário não tiver acesso ao endereço IP público do SBC

O seguinte descreve o fluxo de chamadas se o usuário não tiver acesso ao endereço IP público do SBC. 

Por exemplo, suponha que o usuário seja externo, e o administrador do locatário decidiu não abrir o endereço IP público do SBC para todos na Internet, mas apenas para o Microsoft Cloud. Os componentes internos do tráfego podem fluir por meio dos Retransmissões de Transporte do Teams. Considere o seguinte:

- Os Retransmissões de Transporte do Teams são usados.

- Para bypass de mídia, a Microsoft usa uma versão de Retransmissão de Transporte que requer a abertura das portas 50 000 a 59 999 entre os Retransmissões de Transporte do Teams e o SBC (no futuro planejamos migrar para a versão que requer 3478-3481 portas).


O diagrama a seguir mostra o fluxo de chamadas quando o bypass de mídia está habilitado, o cliente é externo e o cliente não pode alcançar o endereço IP público do Controlador de Borda de Sessão (a mídia é retransmitida pelo Teams Transport Relay).

- As setas e os valores numéricos dos caminhos estão de acordo com os [fluxos de chamada do Microsoft Teams](./microsoft-teams-online-call-flows.md).

- A mídia é retransmitida por meio dos caminhos 3, 3', 4 e 4'

> [!div class="mx-imgBorder"]
> ![Mostra o fluxo de chamadas se o usuário não tiver acesso ao IP público do SBC.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Fluxo de chamadas se um usuário estiver fora da rede e tiver acesso ao IP público do SBC

> [!NOTE]
> Essa não é uma configuração recomendada porque não aproveita os Retransmissões de Transporte do Teams. Em vez disso, você deve considerar o cenário anterior em que o usuário não tem acesso ao endereço IP público do SBC. 

O diagrama a seguir mostra o fluxo de chamadas quando o bypass de mídia está habilitado, o cliente é externo e o cliente pode alcançar o endereço IP público do SBC (mídia direta).

- As setas e os valores numéricos dos caminhos estão de acordo com o artigo [fluxos de chamadas do Microsoft Teams](./microsoft-teams-online-call-flows.md) .

- A sinalização SIP sempre usa os caminhos 3 e 3' (dependendo da direção do tráfego). A mídia flui usando o caminho 2.

> [!div class="mx-imgBorder"]
> ![Mostra o fluxo de chamadas se o usuário não tiver acesso ao IP público do SBC.](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>Uso de processadores de mídia e retransmissões de transporte

Há dois componentes no Microsoft Cloud que podem estar no caminho do tráfego de mídia: Processadores de Mídia e Retransmissões de Transporte. 

- O Processador de Mídia é um componente voltado para o público que lida com a mídia em casos não ignorados e manipula a mídia para aplicativos de voz.

   Os processadores de mídia estão sempre no caminho para chamadas não ignoradas pelo usuário final, mas nunca no caminho para chamadas ignoradas. Os processadores de mídia estão sempre no caminho para todos os aplicativos de voz, como Call Park, Atendimento Automático Organizacional e Filas de Chamadas.

- O Retransmissão de Transporte é usado para se conectar ao Serviço de Transporte mais próximo para enviar tráfego em tempo real.

   Retransmissões de transporte podem ou não estar no caminho para chamadas ignoradas — originadas ou destinadas a usuários finais — dependendo de onde o usuário está e como a rede está configurada.

O diagrama a seguir mostra dois fluxos de chamada – um com bypass de mídia habilitado e o segundo com bypass de mídia desabilitado.

> [!NOTE]
> O diagrama ilustra apenas o tráfego proveniente de usuários finais ou destinados a--.  

- O Controlador de Mídia é um microsserviço no Azure que atribui processadores de mídia e cria ofertas de SDP (Protocolo de Descrição de Sessão).

- O Proxy SIP é um componente que traduz a sinalização HTTP REST usada no Teams para SIP.    

> [!div class="mx-imgBorder"]
> ![Mostra fluxos de chamada com o Bypass de Mídia habilitado e desabilitado.](media/direct-routing-media-bypass-6.png)


A tabela a seguir resume a diferença entre processadores de mídia e retransmissões de transporte.

|  &nbsp; | Processadores de Mídia | Retransmissões de transporte|
| :--------------|:---------------|:------------|
|No caminho da mídia para chamadas não ignoradas para usuários finais | Sempre | Se o cliente não puder acessar o Processador de Mídia diretamente |
|No caminho da mídia para chamadas ignoradas para usuários finais | Nunca | Se o cliente não puder acessar o SBC no endereço IP público |
|No caminho da mídia para aplicativos de voz | Sempre | Nunca |
|Pode fazer transcodificação (B2BUA)\* | Sim | Não, apenas retransmite áudio entre pontos de extremidade |

Os intervalos de IP são:
- 52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254)
- 52.122.0.0/15 (endereços IP de 52.122.0.1 a 52.123.255.254)

\* Explicação de transcodificação: 

- Processador de Mídia é B2BUA, o que significa que ele pode alterar um codecs (por exemplo, SILK de cliente do Teams para MP e G.711 entre MP e SBC).

- Retransmissões de transporte não são B2BUA, o que significa que o codec nunca é alterado entre o cliente e o SBC — mesmo que o tráfego flua por meio de retransmissões.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Uso de Processadores de Mídia do Teams se o tronco estiver configurado para bypass de mídia

Os Processadores de Mídia do Teams são sempre inseridos no caminho da mídia nos seguintes cenários:

- A chamada é escalonada de 1:1 para uma chamada em grupo
- A chamada vai para um usuário federado do Teams
- A chamada é encaminhada ou transferida para um usuário Skype for Business

Verifique se o SBC tem acesso aos intervalos processadores de mídia e retransmissões de transporte, conforme descrito abaixo.    


## <a name="sip-signaling-fqdns"></a>Sinalização SIP: FQDNs

Para sinalização SIP, os requisitos de FQDN e firewall são os mesmos que para casos não ignorados. 

O Roteamento Direto é oferecido nos seguintes ambientes do Microsoft 365 ou Office 365:
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD Saiba mais sobre [Office 365 e ambientes do governo dos EUA](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government), como GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes de GCC do Microsoft 365, Office 365 e Office 365

Os pontos de conexão do Roteamento Direto são os três FQDNs a seguir:

- **sip.pstnhub.microsoft.com** – FQDN global – deve ser julgado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC. A atribuição é baseada em métricas de desempenho dos datacenters e proximidade geográfica com o SBC. O endereço IP retornado corresponde ao FQDN primário.

- **sip2.pstnhub.microsoft.com** – FQDN secundário – mapeia geograficamente para a região de segunda prioridade.

- **sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente para a terceira região de prioridade.

Você deve colocar esses três FQDNs para:

- Forneça uma experiência ideal (menos carregada e mais próxima do datacenter SBC atribuído consultando o primeiro FQDN).

- Forneça failover quando uma conexão de um SBC é estabelecida para um datacenter que está enfrentando um problema temporário. Para obter mais informações, confira Mecanismo de failover abaixo.


As **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** e **sip3.pstnhub.microsoft.com** FQDNs serão resolvidas em endereços IP das seguintes sub-redes:
- 52.112.0.0/14
- 52.122.0.0/15

Você precisa abrir portas para todos esses intervalos de IP em seu firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-365-gcc-dod-environment"></a>Office 365 ambiente de DoD do GCC

O ponto de conexão do Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – FQDN global. Como o ambiente Office 365 DoD existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O sip.pstnhub.dod.teams.microsoft.us FQDN será resolvido para um endereço IP da seguinte sub-rede:

- 52.127.64.0/21

Você precisa abrir portas para todos esses intervalos de IP em seu firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.  Se o firewall der suporte a nomes DNS, o sip.pstnhub.dod.teams.microsoft.us FQDN será resolvido para todas essas sub-redes IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente do GCC High

O ponto de conexão do Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – FQDN global. Como o ambiente GCC High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O sip.pstnhub.gov.teams.microsoft.us FQDN será resolvido para um endereço IP da seguinte sub-rede:

- 52.127.88.0/21

Você precisa abrir portas para todos esses intervalos de IP em seu firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.  Se o firewall der suporte a nomes DNS, o FQDN sip.pstnhub.gov.teams.microsoft.us será resolvido para todas essas sub-redes IP. 

## <a name="sip-signaling-ports"></a>Sinalização SIP: portas

Os requisitos de porta são os mesmos para todos os ambientes Office 365 em que o Roteamento Direto é oferecido:
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Você deve usar as seguintes portas:

| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Definido no SBC |
| SIP/TLS | SBC | SIP Proxy | Definido no SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Tráfego de mídia: intervalos de IP e porta

O tráfego de mídia flui entre o cliente SBC e o Teams se a conectividade direta estiver disponível ou por meio de Retransmissões de Transporte do Teams se o cliente não conseguir acessar o SBC usando o endereço IP público.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisitos para tráfego de mídia direta (entre o cliente do Teams e o SBC) 

O cliente deve ter acesso às portas especificadas (consulte tabela) no endereço IP público do SBC. 

> [!NOTE]
> Se o cliente estiver em uma rede interna, a mídia flui para o endereço IP público do SBC. Você pode configurar a fixação de cabelo em seu dispositivo NAT para que o tráfego nunca saia do equipamento de rede empresarial.

| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Cliente | SBC | 50000-50019| Definido no SBC |
| UDP/SRTP | SBC | Cliente | Definido no SBC | 50000-50019  |


> [!NOTE]
> Se você tiver um dispositivo de rede que traduz as portas de origem do cliente, verifique se as portas traduzidas serão abertas entre o equipamento de rede e o SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisitos para usar retransmissões de transporte

Os retransmissões de transporte estão no mesmo intervalo que processadores de mídia (para casos não ignorados): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes de GCC do Microsoft 365, Office 365 e Office 365

- 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 ambiente de DoD do GCC

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente do GCC High

- 52.127.88.0/21


O intervalo de portas dos Retransmissões de Transporte do Teams (aplicável a todos os ambientes) é mostrado na tabela a seguir:


| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Retransmissão de | SBC | 50 000 -59 999    | Definido no SBC |
| UDP/SRTP | SBC | Retransmissão de | Definido no SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC. Como a Microsoft tem duas versões de Retransmissão de Transporte, o seguinte é necessário:
> 
> - v4, que só pode funcionar com o intervalo de portas 50 000 a 59 999
> 
> - v6, que funciona com portas 3478-3481

Neste momento, o bypass de mídia só dá suporte à versão v4 de Retransmissões de Transporte. Apresentaremos o suporte do v6 no futuro. 

Você precisa abrir as portas 3478-3481 para transição. Quando a Microsoft apresentar suporte para retransmissões de transporte v6 com Bypass de Mídia, você não precisará reconfigurar seu equipamento de rede ou SBCs. 

### <a name="requirements-for-using-media-processors"></a>Requisitos para usar processadores de mídia

Os processadores de mídia estão sempre no caminho da mídia para aplicativos de voz e para clientes Web (por exemplo, clientes do Teams no Edge ou Google Chrome). Os requisitos são os mesmos da configuração de não bypass.


O intervalo de IP para tráfego de mídia é 

### <a name="office-365-and-office-365-gcc-environments"></a>ambientes de GCC Office 365 e Office 365

- 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 ambiente de DoD do GCC

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente do GCC High

- 52.127.88.0/21

O intervalo de portas dos Processadores de Mídia (aplicável a todos os ambientes) é mostrado na tabela a seguir:

| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Processador de Mídia | SBC | 3478-3481 e 49 152 – 53 247    | Definido no SBC |
| UDP/SRTP | SBC | Processador de Mídia | Definido no SBC | 3478-3481 e 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurar troncos separados para bypass de mídia e bypass sem mídia  

Se você estiver migrando para o bypass de mídia do bypass que não é de mídia e quiser confirmar a funcionalidade antes de migrar todo o uso para o bypass de mídia, você poderá criar um tronco separado e separar a política de Roteamento de Voz Online para rotear para o tronco de bypass de mídia e atribuir a usuários específicos. 

Etapas de configuração de alto nível:

- Identifique os usuários para testar o bypass de mídia.

- Criar dois troncos separados com FQDNs diferentes: um habilitado para bypass de mídia; o outro não. 

  Ambos os troncos apontam para o mesmo SBC. As portas para sinalização SIP do TLS devem ser diferentes. As portas para mídia devem ser as mesmas.

- Crie uma nova política de Roteamento de Voz Online e atribua o tronco de bypass de mídia às rotas correspondentes associadas ao uso de PSTN para essa política.

- Atribua a nova política de Roteamento de Voz Online aos usuários que você identificou para testar o bypass de mídia.

O exemplo a seguir ilustra essa lógica.

| Conjunto de usuários | Número de usuários | Trunk FQDN atribuído no OVRP | Bypass de mídia habilitado |
| :------------ |:----------------- |:--------------|:--------------|
| Usuários com tronco de bypass que não é de mídia | 980 | sbc1.contoso.com:5061 | False |
| Usuários com tronco de bypass de mídia | 20 | sbc2.contoso.com:5060 | Verdade | 

Ambos os troncos podem apontar para o mesmo SBC com o mesmo endereço IP público. As portas de sinalização TLS no SBC devem ser diferentes, conforme mostrado no diagrama a seguir. Observe que você precisará ter certeza de que seu certificado dá suporte a ambos os troncos. Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.

> [!div class="mx-imgBorder"]
> ![Mostra que ambos os troncos podem apontar para o mesmo SBC com o mesmo IP público.](media/direct-routing-media-bypass-7.png)

Para obter informações sobre como configurar dois troncos no mesmo SBC, confira a documentação fornecida pelo fornecedor do SBC:

 - [Documentação de implantação do AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação de implantação do Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Pontos de extremidade do cliente com suporte com bypass de mídia

Há suporte para bypass de mídia com todos os clientes autônomos do Teams Desktop, clientes Android e iOS e dispositivos de telefone do Teams. 

Para todos os outros pontos de extremidade que não dão suporte ao bypass de mídia, converteremos a chamada em não bypass mesmo que ela seja iniciada como uma chamada de bypass. Isso acontece automaticamente e não requer nenhuma ação do administrador. Isso inclui Skype for Business telefones 3PIP e clientes Web do Teams que dão suporte à chamada de Roteamento Direto (clientes baseados em WebRTC em execução no Microsoft Edge, Google Chrome, Mozilla Firefox). 
 
## <a name="see-also"></a>Confira também

[Configurar o bypass de mídia com Roteamento Direto](direct-routing-configure-media-bypass.md)
