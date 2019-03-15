---
title: Planejar o bypass de mídia com o roteamento direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Leia este tópico para saber como planejar o bypass de mídia com roteamento direto de sistema do telefone.
ms.openlocfilehash: 39fc46fb95fef1d78f6f6cc946693f05c7c1f865
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631007"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planejar o bypass de mídia com o roteamento direto

## <a name="about-media-bypass-with-direct-routing"></a>Sobre o bypass de mídia com o roteamento direto

Bypass de mídia permite diminuir o caminho de tráfego de mídia e reduzir o número de saltos em trânsito para melhor desempenho. Com o bypass de mídia, será mantida entre o controlador de borda de sessão (SBC) e o cliente em vez de enviá-la por meio do sistema de telefone da Microsoft. Para configurar o media bypass, o SBC e o cliente devem ser no mesmo local ou rede

Você pode controlar o bypass de mídia para cada SBC usando o comando **Set-CSOnlinePSTNGateway** com o parâmetro **- MediaBypass** definido como true ou false. Se você habilitar o bypass de mídia, isso significa que todo o tráfego de mídia permanecerão dentro da rede corporativa. Este artigo descreve o fluxo de chamadas em diferentes cenários.    

Os diagramas a seguir ilustram a diferença no fluxo de chamadas com e sem desvio de mídia.

Sem bypass de mídia, quando um cliente faz ou recebe uma chamada, sinalização e mídia flua entre o SBC, o sistema de telefone da Microsoft e o cliente de equipes, conforme mostrado no diagrama a seguir:

![Mostra a sinalização e fluxo de mídia sem desvio de mídia](media/direct-routing-media-bypass-1.png)


Mas vamos supor que um usuário está na mesma rede como o SBC ou construção. Por exemplo, suponha que um usuário que está em um edifício no faz de Frankfurt uma chamada para um usuário por PSTN: 

- **Sem media bypass**, mídia fluirá via Amsterdã ou Dublin (onde os data centers da Microsoft estão implantados) e voltar para o SBC em Frankfurt. 

  O datacenter na Europa está selecionado porque o SBC está na Europa e a Microsoft usa o datacenter mais próximo ao SBC. Embora essa abordagem não afeta a qualidade da chamada devido à otimização de fluxo de tráfego dentro de redes Microsoft na maioria das regiões, o tráfego tem um loop desnecessário.     

- **Com o media bypass**, a mídia é mantida diretamente entre o usuário de equipes e o SBC, conforme mostrado no diagrama a seguir:

![Mostra a sinalização e o fluxo de mídia com bypass de mídia](media/direct-routing-media-bypass-2.png)

Protocolos aproveita chamados conectividade ICE (estabelecimento interativa) no cliente de equipes e ICE luz do SBC de desvio de mídia. Esses protocolos habilite o roteamento direto usar o caminho de mídia mais direto para a melhor qualidade. ICE e luz ICE são WebRTC padrões. Para obter informações detalhadas sobre esses protocolos, consulte RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Planejamento de firewall e de fluxo de chamadas

Fluxo de chamadas e planejamento de firewall depende se o usuário tem acesso direto para o endereço IP público do SBC e se o usuário está dentro ou fora da rede.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Fluxo de chamadas se o usuário tem acesso direto para o endereço IP público do SBC

Se o usuário tem acesso direto para o endereço IP público do SBC, o fluxo de chamadas é o seguinte:

- Bypass de mídia, o cliente de equipes deve ter acesso ao endereço IP público do SBC até mesmo a partir de uma rede interna. Se a mídia direta não for desejada, a mídia pode fluir via retransmissões de transporte.

- Esta é a solução recomendada quando um usuário estar participando de rede como o SBC e/ou mesmo prédio – remova componentes do Microsoft Cloud o caminho de mídia.

- Sinalização sempre flui por meio de nuvem da Microsoft.

O diagrama a seguir mostra o fluxo de chamadas quando o desvio de mídia está habilitado, o cliente é interno e o cliente pode alcançar o endereço IP público do SBC (direct media): 

- As setas e os valores numéricos dos caminhos estejam de acordo com o documento Microsoft equipes Online fluxos de chamada.

- Sempre a sinalização SIP leva caminhos 4 e 4' (dependendo da direção do tráfego). Mídia permanece local e leva 5b caminho.

![Mostra o fluxo de chamadas com Bypass de mídia habilitado, o cliente interno e pode alcançar o IP público do controlador de borda de sessão (direct mídia)](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Fluxo de chamadas se o usuário não tem acesso para o endereço IP público do SBC

A seguir descreve o fluxo de chamada se o usuário não tem acesso para o endereço IP público do SBC. 

Por exemplo, suponha que o usuário seja externo, e o administrador de locatário decidiu não abrir o endereço IP público do SBC para todos na Internet, mas somente para o Microsoft Cloud. Os componentes internos do tráfego podem fluir através de retransmissões de transporte de equipes. Esta é a configuração recomendada para usuários fora da rede corporativa. Considere o seguinte:

- As equipes retransmissões de transporte são usadas.

- Bypass de mídia, a Microsoft usa uma versão do retransmissões de transporte que requer a abertura de portas 50 000 para 59 999 entre as equipes transporte retransmissões e o SBC (no futuro que pretendemos para mover para a versão que exige portas apenas 3478 e 3479).

- Para fins de otimização de mídia, a Microsoft recomenda abrindo o endereço IP público do SBC apenas ao transporte as equipes retransmissões. Para clientes fora da rede corporativa, a Microsoft recomenda usar retransmissões de transporte em vez de está atingindo o endereço IP público do SBC diretamente.

O diagrama a seguir mostra o fluxo de chamadas quando o desvio de mídia está habilitado, o cliente for externo e o cliente não consegue acessar o endereço IP público do controlador de borda de sessão (mídia é retransmitida por equipes retransmissão de transporte).

- As setas e os valores numéricos dos caminhos estejam de acordo com o documento Microsoft equipes Online fluxos de chamada.

- Mídia é retransmitida via caminhos 3, 3', 4 e 4'

![Mostra o fluxo de chamadas se o usuário não tem acesso ao IP público do SBC)](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Fluxo de chamadas se um usuário está fora da rede e tenha acesso ao IP público do SBC

> [!NOTE]
> Isso não é uma configuração recomendada porque ele não tirar proveito das equipes retransmissões de transporte. Em vez disso, você deve considerar o cenário anterior, onde o usuário não tem acesso para o endereço IP público do SBC. 

O diagrama a seguir mostra o fluxo de chamadas quando o desvio de mídia está habilitado, o cliente for externo e o cliente pode alcançar o endereço IP público do SBC (direct mídia).

- As setas e os valores numéricos dos caminhos estejam de acordo com o documento Microsoft equipes Online fluxos de chamada.

- Sempre a sinalização SIP leva caminhos 3 e 3' (dependendo da direção do tráfego). Fluxos de mídia usando o caminho 2.

![Mostra o fluxo de chamadas se o usuário não tem acesso ao IP público do SBC)](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Uso de processadores de mídia e retransmissões de transporte

Existem dois componentes no Microsoft Cloud que podem ser no caminho do tráfego de mídia: processadores de mídia e retransmissões de transporte. 

- O processador de mídia é um componente de voltada público que trata a mídia em casos não ignorar e trata a mídia para aplicativos de voz.

   Processadores de mídia são sempre no caminho para o usuário final não ignorada chamadas, mas nunca no caminho para chamadas ignorados. Processadores de mídia são sempre no caminho para todos os aplicativos de voz como Call Park, atendedor automático da organizacional e filas de chamada.

- A retransmissão de transporte é usada para se conectar ao serviço de transporte mais próximos, para enviar o tráfego de tempo real.

   Transporte retransmissões podem ou não ser no caminho para chamadas ignorados – provenientes de ou destinados aos usuários finais – dependendo de onde o usuário está e como a rede está configurada.

O diagrama a seguir mostra dois fluxos de chamada – um com bypass de mídia habilitado e o segundo com mídia desvio desabilitado. Observação o diagrama apenas ilustra o tráfego provenientes de – ou destinados a – os usuários finais.  
- O controlador de mídia é um microservice no Azure que atribui processadores de mídia e cria ofertas de protocolo de descrição de sessão (SDP).

- O Proxy SIP é um componente que converte a sinalização de HTTP REST usados em equipes para SIP.    

![Mostra mostra dois fluxos de chamada – um com Bypass de mídia habilitado e o segundo com Bypass de mídia é desabilitado)](media/direct-routing-media-bypass-6.png)


A tabela a seguir resume a diferença entre os processadores de mídia e retransmissões de transporte.

|    | Processadores de mídia | Retransmissões de transporte|
| :--------------|:---------------|:------------|
No caminho de mídia das chamadas não desviada para usuários finais | Sempre | Nunca | 
No caminho de mídia para ignorados chamadas para usuários finais | Nunca | Se o cliente não consegue acessar o SBC no endereço IP público | 
No caminho de mídia para aplicativos de voz | Sempre | Nunca | 
Pode fazer a transcodificação (B2BUA)\* | Sim | Não, retransmite apenas áudio entre os pontos de extremidade | 
Número de instancess mundial e local | total de 8: 2 pol conosco Leste e Oeste; 2 pol Amsterdã e Dublin; 2 de Hong Kong e Cingapura; 2 no Japão (que está sendo adicionado ao Q1CY2019)  | Vários

O intervalo IP é 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254). 

\*Explicação transcodificação: 

- Processador de mídia é B2BUA, o que significa que ele pode alterar um codecs (por exemplo, SILK do cliente de equipes MP e g. 711 entre MP e SBC).

- Transporte retransmissões não são B2BUA, o que significa que o codec nunca é alterado entre o cliente e o SBC – mesmo se o tráfego flui via retransmissões.

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>Uso das equipes retransmissões de transporte em cenários de escalonamento se tronco estiver configurado para o media bypass

As equipes retransmissões de transporte são sempre no caminho de mídia nos seguintes cenários:

- Chamada será escalonada de 1:1 para uma chamada do grupo
- Chamada será um usuário federado de equipes
- Chamada é encaminhada ou transferida para um Skype para o usuário de negócios

Enusre seu SBC possui acesso para o retransmissões de transporte, conforme descrito abaixo.    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a>Sinalização SIP: FQDNs e portas de firewall

De sinalização SIP, os requisitos de firewall e FQDN são iguais às propriedades casos não ignorada. 

Os pontos de conexão para roteamento direto são os FQDNs de três seguintes:

- **sip.pstnhub.microsoft.com** – Global FQDN – deve ser tentado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS da Microsoft Azure retornam um endereço IP apontando para o datacenter do Windows Azure primário atribuído para o SBC. Sobre as métricas de desempenho dos centros de dados e proximidade geográfica com o SBC baseia-se a atribuição. O endereço IP retornado corresponde ao FQDN principal.

- **sip2.pstnhub.microsoft.com** – secundário FQDN – geograficamente mapeia à segunda região prioridade.

- **sip3.pstnhub.microsoft.com** – terciária FQDN – geograficamente mapeia para a região de prioridade de terceiro.

Você deve colocar esses três FQDNs para:

- Fornecer uma experiência ideal (menos carregada e mais próxima para o datacenter SBC atribuído consultando o FQDN do primeiro).

- Fornece failover quando uma conexão de um SBC é estabelecida com um datacenter que está experimentando um problema temporário. Para obter mais informações, consulte abaixo do mecanismo de Failover.


Os FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**e **sip3.pstnhub.microsoft.com** serão resolvidos para um dos seguintes endereços IP:
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Você precisará abrir portas para todos esses endereços IP no seu firewall para permitir o tráfego de entrada e saído de e para os endereços de sinalização. Se seu firewall suporta nomes DNS, o FQDN **sip-all.pstnhub.microsoft.com** resolve para todos os endereços IP acima. Você deve usar as seguintes portas:

| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| Proxy SIP | SBC | 1024 - 65535 | Definidos no SBC |
| SIP/TLS | SBC | Proxy SIP | Definidos no SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Tráfego de mídia: intervalos IP e porta

Tráfego de mídia flui entre o cliente SBC e as equipes se conectividade direta estiver disponível ou através de equipes transporte retransmissões se o cliente não consegue acessar o SBC usando o endereço IP público.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisitos para o tráfego de mídia direto (entre o cliente de equipes e o SBC) 

O cliente deve ter acesso às portas especificadas (veja tabela) no endereço IP público do SBC. 

Observação: Se o cliente estiver em uma rede interna, a mídia flui para o endereço IP público do SBC. Você pode configurar hairpinning no seu dispositivo NAT para que tráfego nunca deixa o equipamento de rede empresarial.

| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Cliente | SBC | 50 000 – 50 019  | Definidos no SBC |
| UDP/SRTP | SBC | Cliente | Definidos no SBC | 50 000 – 50 019  |


Observação: Se você tiver um dispositivo de rede que converte a portas de origem do cliente, verifique se que serão abertas portas convertidas entre o equipamento de rede e o SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisitos de uso retransmissões de transporte

Transporte retransmissões estão no mesmo intervalo como processadores de mídia (para casos não ignorar): 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254).

O intervalo de portas de retransmissões de transporte as equipes é mostrado na tabela a seguir:


| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Retransmissão de transporte | SBC | 50 000-59 999    | Definidos no SBC |
| UDP/SRTP | SBC | Retransmissão de transporte | Definidos no SBC | 50 000 a 59 9999, 3478, 3479     |


Observação: A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC. Como a Microsoft tem duas versões do retransmissões de transporte, é necessário o seguinte:

- V4, que só pode trabalhar com o intervalo de portas 50 000 para 59 999

- v6, que funciona com portas 3478, 3479

Neste momento, o desvio de mídia somente suporta a versão v4 de retransmissões de transporte. Apresentaremos suporte de v6 no futuro. 

Você precisará abrir as portas 3478 e 3479 para a transição. Quando o Microsoft introduz o suporte para v6 retransmissões de transporte com Bypass de mídia, você não precisará reconfigurar o equipamento de rede ou SBCs. 

### <a name="requirements-for-using-media-processors"></a>Requisitos para o uso de processadores de mídia

Processadores de mídia são sempre no caminho de mídia para aplicativos de voz. Os requisitos são iguais às propriedades de configuração não ignorar.


O intervalo IP para o tráfego de mídia é 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254).

O intervalo de portas dos processadores de mídia é mostrado na tabela a seguir:

| Tráfego | De | Até | Porta de origem | Porta de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Processador de mídia | SBC | 49 152 – 53 247    | Definidos no SBC |
| UDP/SRTP | SBC | Processador de mídia | Definidos no SBC | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>Considerações sobre se você tiver Skype para telefones de negócios em sua rede  

Se você tiver quaisquer Skype para pontos finais empresariais em sua rede que está usando o roteamento direto – por exemplo, um usuário pode ter um telefone 3PIP com base no Skype para o cliente de negócios – as equipes o bypass de mídia no tronco que serve a esses usuários deve ser desativado.

Você pode criar um tronco separado para esses usuários e atribuí-la uma política de roteamento de voz Online.

Etapas de configuração de alto nível:

- Dividir os usuários por tipo – dependendo se o usuário possui um telefone 3PIP ou não.

- Criar dois troncos separados com diferentes FQDNs: um habilitado bypass de mídia; outro não. 

  Ambos os troncos apontam para o mesmo SBC. As portas para a sinalização SIP TLS devem ser diferentes. As portas de mídia devem ser o mesmo.

- Atribua o tronco correto, dependendo do tipo do usuário na política de roteamento de voz Online.

O exemplo a seguir ilustra essa lógica.

| Conjunto de usuários | Número de usuários | Tronco FQDN atribuída no OVRP | Bypass de mídia habilitado |
| :------------ |:----------------- |:--------------|:--------------|
Usuários com clientes de equipes e telefones 3PIP | 20 | sbc1.contoso.com:5061 | False | 
Usuários com apenas equipes pontos de extremidade (incluindo novos telefones certificados para equipes) | 980 | sbc2.contoso.com:5060 | True

Ambos os troncos podem apontar para o mesmo SBC com o mesmo endereço IP público. Os TLS sinalização portas no SBC deve ser diferentes, conforme mostrado no diagrama a seguir. Observe que você precisará certificar-se de que seu certificado suporta ambos os troncos. Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.


![Mostra que os dois troncos podem apontar para o mesmo SBC com o mesmo IP público)](media/direct-routing-media-bypass-7.png)

Para obter informações sobre como configurar dois troncos no mesmo SBC, consulte a documentação fornecida pelo seu fornecedor SBC:

- AudioCodes
- Faixa de opções
- TE-Systems (Anynode)   

## <a name="client-endpoints-supported-with-media-bypass"></a>Pontos de extremidade do cliente compatíveis com o media bypass

Bypass de mídia é compatível com todos os pontos de extremidade equipes, exceto clientes Web equipes até notificação futura. 

Se os usuários preferem aplicativos da Web de equipes em Microsoft Edge, Google Chrome ou Mozilla Firefox, o bypass de mídia para tais usuários deve ser desativado. Apresentaremos chamadas usando um tronco habilitado de bypass de mídia no futuro.   
 
## <a name="see-also"></a>Consulte Também

[Configurar o bypass de mídia com o roteamento direto](direct-routing-configure-media-bypass.md)



