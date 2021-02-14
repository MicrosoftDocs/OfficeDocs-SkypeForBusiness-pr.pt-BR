---
title: Otimização de Mídia Local de Roteamento Direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurar Otimização de Mídia Local para Roteamento Direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576983"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurar Otimização de Mídia Local para Roteamento Direto

A configuração de Otimização de Mídia Local baseia-se nas configurações de rede que são comuns a outros recursos de voz na nuvem, como o roteamento Location-Based e chamadas de emergência dinâmicas. Para saber mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte Configurações de rede para recursos [de voz na nuvem.](cloud-voice-network-settings.md)

Antes de configurar a Otimização de Mídia Local, consulte [Otimização de mídia local para Roteamento Direto.](direct-routing-media-optimization.md)  

Para configurar a Otimização de Mídia Local, as etapas a seguir são necessárias. Você pode usar o Centro de Administração do Teams ou o PowerShell. Para obter detalhes, consulte [Gerenciar sua topologia de rede.](manage-your-network-topology.md)

1. Configure o usuário e os sites SBC (conforme descrito neste artigo).
2. Configure os SBCs para Otimização de Mídia Local (de acordo com a especificação do fornecedor SBC).

O diagrama a seguir mostra a configuração de rede usada nos exemplos deste artigo.

![Diagrama mostrando a configuração de rede para exemplos](media/direct-routing-media-op-9.png "Configuração de rede para exemplos")


## <a name="configure-the-user-and-the-sbc-sites"></a>Configurar o usuário e os sites SBC

Para configurar o usuário e os sites SBC, você precisará:

1. [Gerenciar endereços IP confiáveis externos.](#manage-external-trusted-ip-addresses)  

2. [Defina a topologia de rede](#define-the-network-topology) configurando as regiões de rede, os sites de rede e as sub-redes de rede.

3. [Defina a topologia de](#define-the-virtual-network-topology) rede virtual atribuindo SBC(s) a sites(s) com modos relevantes e valores SBC de proxy.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurar SBC(s) para Otimização de Mídia Local de acordo com a especificação do fornecedor SBC

Este artigo descreve a configuração dos componentes da Microsoft. Para obter informações sobre configuração SBC, consulte a documentação do fornecedor SBC.

A Otimização de Mídia Local tem suporte dos seguintes fornecedores SBC:

| Fornecedor | Produto |    Versão do software |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.256 | 
|            |  Mediant 2600 SBC |  7.20A.256 | 
|            |  Mediant 4000 SBC |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [Núcleo SBC da Faixa de Opções](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Borda SBC da Faixa de Opções](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Gerenciar endereços IP confiáveis externos

IPs confiáveis externos são os IPs externos da Internet da rede corporativa. Esses IP são os endereços IP usados pelos clientes do Microsoft Teams quando eles se conectam ao Microsoft 365. Você precisa adicionar esses IPs externos para cada site onde você tem usuários usando Otimização de Mídia Local.

Para adicionar os endereços IP públicos de cada site, use New-CsTenantTrustedIPAddress cmdlet. Você pode definir um número ilimitado de endereços IP confiáveis para um locatário. Se os IPs externos vistos pelo Microsoft 365 são endereços IPv4 e IPv6, você precisa adicionar os dois tipos de endereços IP. Para IPv4, use a máscara 32. Para IPv6, use a máscara 128. Você pode adicionar endereços IP externos individuais e sub-redes IP externas especificando diferentes MaskBits no cmdlet.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Exemplo de adição de endereços IP confiáveis.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Definir a topologia de rede

Esta seção descreve como definir as regiões de rede, os sites de rede e as sub-redes de rede para sua topologia de rede.

Todos os parâmetros são sensíveis a minúsculas, portanto, você precisa garantir que use o mesmo caso usado durante a configuração.  (Por exemplo, os valores GatewaySiteID "Vietnã" e "vietnã" serão tratados como sites diferentes.)

### <a name="define-network-regions"></a>Definir regiões de rede

Para definir regiões de rede, use New-CsTenantNetworkRegion cmdlet. O parâmetro ID Região é um nome lógico que representa a geografia da região e não tem dependências ou restrições. O parâmetro CentralSite <site ID> é opcional.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

O exemplo a seguir cria uma região de rede chamada APAC:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Definir sites de rede

Para definir sites de rede, use o cmdlet New-CsTenantNetworkSite de rede. Cada site de rede deve estar associado a uma região de rede.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

O exemplo a seguir cria três novos sites de rede, Vietnã, Indonésia e Cingapura na região APAC:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definir sub-redes de rede

Para definir sub-redes de rede e associá-las a sites de rede, use o cmdlet New-CsTenantNetworkSubnet rede. Cada sub-rede de rede só pode ser associada a um site. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

O exemplo a seguir define três sub-redes de rede e as associa aos três sites de rede: Vietnã, Indonésia e Cingapura:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Definir a topologia de rede virtual 

Primeiro, o administrador do locatário cria uma nova configuração SBC para cada SBC relevante usando o cmdlet New-CsOnlinePSTNGateway usuário.
O administrador do locatário define a topologia de rede virtual especificando os sites de rede para os objetos de gateway PSTN usando o cmdlet Set-CsOnlinePSTNGateway:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Observe o seguinte: 
   - Se o cliente tiver um único SBC, o parâmetro -ProxySBC deve ser obrigatório $null ou FQDN SBC (SBC Central com cenário centralizado de troncos).
   - O parâmetro -MediaBypass deve ser definido como $true para dar suporte à Otimização de Mídia Local.
   - Se o SBC não tiver o parâmetro -BypassMode definido, os headers X-MS não serão enviados. 
   - Todos os parâmetros são sensíveis a minúsculas, portanto, você precisa garantir que use o mesmo caso usado durante a configuração.  (Por exemplo, os valores GatewaySiteID "Vietnã" e "vietnã" serão tratados como sites diferentes.)

O exemplo a seguir adiciona três SBCs aos sites de rede Vietnã, Indonésia e Cingapura na região APAC com o modo Sempre ignorar:

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Observação: para garantir operações ininterruptas quando a Otimização de Mídia Local e o roteamento de Location-Based (LBR) estão configurados ao mesmo tempo, os SBCs downstream devem ser habilitados para a LBR, definindo o parâmetro GatewaySiteLbrEnabled para $true para cada SBC downstream. (Essa configuração não é obrigatória para o SBC proxy.)

Com base nas informações acima, o Roteamento Direto incluirá três Headers SIP proprietários para Convites SIP e Re-convidar, conforme mostrado na tabela a seguir.

Os Headers X-MS introduzidos no Roteamento Direto em Convites e Re-Invites se BypassMode estiver definido:

| Nome do header | Valores | Comentários | 
|:------------|:-------|:-------|
| X-MS-UserLocation | interno/externo | Indica se o usuário é interno ou externo |
| Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | O FQDN que é direcionado para a chamada mesmo que o SBC não esteja conectado diretamente ao Roteamento Direto |
| X-MS-MediaPath | Exemplo: proxysbc.contoso.com, VNsbc.contoso.com | Ordem de SBCs que devem ser usados para o caminho de mídia entre o usuário e o SBC de destino. O SBC final é sempre o último |
| X-MS-UserSite | iDdosu usuários | Cadeia de caracteres definida pelo administrador do locatário |

## <a name="call-flows"></a>Fluxos de chamada 

O seguinte mostra os fluxos de chamada para dois modos:

- [Sempre ignorar](#always-bypass-mode)
- [Somente para usuários locais](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modo Sempre Ignorar

O modo Sempre Ignorar é a opção mais simples de configurar. O administrador do locatário pode configurar um único site para todos os usuários e SBCs se todos os SBCs puderem ser acessíveis de qualquer site.

Os exemplos mostram o modo Sempre ignorado para os seguintes cenários:

- [Chamadas de saída e o usuário está no mesmo local que o SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Chamadas de entrada e o usuário está no mesmo local que o SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Chamadas de saída e o usuário é externo](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Chamadas de entrada e o usuário é externo](#inbound-calls-and-the-user-is-external-with-always-bypass)

A tabela a seguir mostra os endereços IP e FQDN usados nos exemplos:

| FQDN | Endereço IP externo SBC | Endereço IP interno SBC | Sub-rede interna | Local | NAT externo (IP confiável) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Nenhum | 192.168.1.5 | 192.168.1.0/24 | Vietnã | 172.16.240.110 |
| IDsbc.contoso.com | Nenhum | 192.168.2.5 | 192.168.2.0/24 | Indonésia | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Singapura | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Chamadas de saída e o usuário está no mesmo local que o SBC com Sempre Ignorar

| Modo |    Usuário |  Local |  Direção da chamada |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Interno |  O mesmo site que o SBC |  Saída |

A tabela a seguir mostra a configuração e a ação do usuário final:

| Localização física do usuário| O usuário faz ou recebe uma chamada para/de número | Número de telefone do usuário  | Política de Roteamento de Voz Online | Modo configurado para SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnã | +84 4 3926 3000 | +84 4 5555 5555   | Prioridade 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridade 2: .* - proxysbc.contoso.com   | VNsbc.contoso.com – Sempre Ignorar <br> proxysbc.contoso.com – Sempre Ignorar


O diagrama a seguir mostra a classificação SIP para uma chamada de saída com o modo Sempre ignorar e o usuário no mesmo local que o SBC.

![Diagrama mostrando chamadas de saída](media/direct-routing-media-op-10.png "Chamadas de saída")

A tabela a seguir mostra os headers X-MS enviados pelo Roteamento Direto:

| Parâmetro | Explicação |
|:------------|:-------|
| Convidar +8443926300@VNsbc.contoso.com | O FQDN de destino do SBC conforme definido na Política de Roteamento de Voz Online é enviado no URI de Solicitação | 
| X-MS-UserLocation: interno | O campo indica que o usuário está localizado dentro da rede corporativa |
| X-MS-MediaPath: VNsbc.contoso.com |   Especifica qual SBC o cliente deve percorrer até o SBC de destino. Nesse caso, como sempre ignoramos, e o cliente é interno o nome de destino enviado como o único nome no header. | 
|X-MS-UserSite: Vietnã |   O campo indicado no site em que o usuário está localizado. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Chamadas de entrada e o usuário está no mesmo local que o SBC com Sempre Ignorar

| Modo |    Usuário |  Local |  Direção da chamada |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Interno | O mesmo site que o SBC | Entrada |


Em uma chamada de entrada, a localização do usuário é desconhecida e o SBC deve adivinhar onde o usuário está. Se a suposição não estiver correta, será necessário um novo convite. Esse caso pressu que o usuário é interno, que a mídia pode fluir diretamente e nenhuma ação é necessária (convidar de novo).
O SBC conectado ao serviço roteamento direto informa o local SBC de origem, fornecendo campos Record-Route e Contato. Com base nesses campos, o caminho da mídia é calculado pelo Roteamento Direto.

Observação: como um usuário pode ter vários pontos de extremidade, não é possível ter suporte para 183. O Roteamento Direto sempre usará o Toque 180 nesse caso. 

O diagrama a seguir mostra a classificação SIP para chamada de entrada com o modo AlwaysBypass e o usuário está no mesmo local que o SBC.

![Diagrama mostrando sip](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Chamadas de saída e o usuário é externo com Sempre Ignorar

| Modo |    Usuário |  Site |  Direção da chamada
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externo |  Não disponível | Saída |


O diagrama a seguir mostra a classificação SIP para uma chamada de saída com o modo AlwaysBypass e o usuário é externo:

![Diagrama mostrando sip](media/direct-routing-media-op-12.png)

A tabela a seguir mostra os headers X-MS enviados pelo serviço roteamento direto:

| Parâmetro |   Explicação |
|:------------|:-------|
|Convidar +8443926300@VNsbc.contoso.com | O FQDN de destino do SBC conforme definido na Política de Roteamento de Voz Online é enviado no URI de Solicitação.|
| X-MS-UserLocation: externo | O campo indicou que o usuário está localizado fora da rede corporativa. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Especifica qual SBC o cliente deve percorrer até o SBC de destino. Nesse caso, como sempre ignoramos, e o cliente é externo. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Chamadas de entrada e o usuário é externo com Sempre Ignorar

| Modo | Usuário | Site |  Direção da chamada |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externo |  Não disponível |   Entrada |

Para uma chamada de entrada, o SBC conectado ao Roteamento Direto precisa enviar um novo convite (por padrão, os candidatos à mídia local sempre são oferecidos) se o local do usuário for externo.  O X-MediaPath é calculado com base Record-Route e o usuário SBC especificado.

O diagrama a seguir mostra a classificação SIP para uma chamada de entrada com o modo AlwaysBypass e o usuário é externo.

![Diagrama mostrando sip](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Somente para o modo de usuários locais

Os candidatos à mídia local do SBC de destino serão oferecidos somente se um usuário estiver no mesmo local que o SBC. Em todos os outros casos, a mídia fluirá por um IP interno ou externo do SBC proxy.

Os seguintes cenários são descritos:

- [Chamadas de saída e o usuário está no mesmo local que o SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Chamadas de entrada e o usuário está no mesmo local que o SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [O usuário não está no mesmo local que o SBC, mas está na rede corporativa](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Chamadas de entrada e o usuário é interno, mas não está no mesmo local que o SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

A tabela a seguir mostra a configuração e a ação do usuário final:

| Localização física do usuário |  O usuário faz ou recebe uma chamada para/de número |  Número de telefone do usuário | Política de Roteamento de Voz Online |   Modo configurado para SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnã | +84 4 3926 3000 |  +84 4 5555 5555 | Prioridade 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridade 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Sempre Ignorar |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chamadas de saída e o usuário está no mesmo local que o SBC com Somente para usuários locais

| Modo | Usuário | Site | Direção da chamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno |Mesmo que SBC   | Saída |

O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e o usuário está no mesmo local que o SBC. Esse é o mesmo fluxo mostrado em chamadas de saída quando o usuário está [no mesmo local que o SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagrama mostrando sip](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chamadas de entrada e o usuário está no mesmo local que o SBC com Somente para usuários locais

| Modo | Usuário | Site | Direção da chamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno | Mesmo que SBC | Entrada |

O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e o usuário está no mesmo local que o SBC. Esse é o mesmo fluxo mostrado em chamadas de entrada quando o usuário está [no mesmo local que o SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagrama mostrando sip](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>O usuário não está no mesmo local que o SBC, mas está na rede corporativa apenas para usuários locais

| Modo | Usuário | Site |Direção da chamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Interno |   Diferente do SBC | Saída |

O roteamento direto calcula o X-MediaPath com base no local relatado do usuário e no modo configurado no SBC.


O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local que o SBC.

![Diagrama mostrando sip](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chamada de entrada e o usuário é interno, mas não está no mesmo local que o SBC somente para usuários locais

| Modo |    Usuário |  Site |  Direção da chamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Interno |    Diferente do SBC |    Entrada |

O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local que o SBC.

![Diagrama mostrando sip](media/direct-routing-media-op-17.png)









