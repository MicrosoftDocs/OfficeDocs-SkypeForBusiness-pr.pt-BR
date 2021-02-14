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
description: Otimização de mídia local para roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886dd4d14d8393764f3c939991a8959ed4726aa3
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686457"
---
# <a name="local-media-optimization-for-direct-routing"></a>Otimização de mídia local para roteamento direto

A voz PSTN (Rede Telefônica Pública Comutado) é considerada um aplicativo comercial crítico, com grandes expectativas de qualidade de voz. O Roteamento Direto permite controlar os fluxos de tráfego de mídia para acomodar uma infinidade de topologias de rede e configurações de telefonia local para várias empresas em todo o mundo. 

A Otimização de Mídia Local para Roteamento Direto permite gerenciar a qualidade da voz por:

-   Controlar como o tráfego de mídia flui entre os clientes do Teams e os SBCs (Controladores de Borda de Sessão) do cliente.
-   Manter a mídia local dentro dos limites das sub-redes de rede corporativa.
-   Permitindo fluxos de mídia entre os clientes do Teams e os SBCs, mesmo que os SBCs sejam firewalls corporativos com IPs particulares e não visíveis diretamente para a Microsoft.

A Otimização de Mídia Local dá suporte a dois cenários:

- Centralização de todos os troncos locais por meio de um SBC centralizado conectado ao tronco principal do PROTOCOLO ( Protocolo de Início de Sessão), fornecendo serviços de telefonia para todas as filiais locais da empresa.

-   Criando uma topologia de rede virtual de SBCs, onde os SBCs nas filiais locais estão conectados a um SBC proxy centralizado que está visível e se comunicando com o Microsoft Phone System por meio de seu endereço IP externo. Em uma topologia de rede virtual, os SBCs downstream estão se comunicando por meio de IPs internos e não estão diretamente visíveis para o Sistema telefônico.

Este artigo descreve a funcionalidade de recursos, cenários e soluções do cliente. Para obter detalhes sobre configuração, consulte [Configurar Otimização de Mídia Local.](direct-routing-media-optimization-configure.md) 

  > [!NOTE]
  > Se você quiser manter a mídia local dentro dos limites da intranet, recomenda-se a Otimização de Mídia Local. Se você já tem o Bypass de Mídia e usa apenas os endereços IP públicos de seus SBCs, não é obrigatório mover para Otimização de Mídia Local. Você pode continuar a usar o Bypass de Mídia. Para obter mais informações, consulte [Plan Media Bypass.](direct-routing-plan-media-bypass.md)


## <a name="supported-customer-scenarios"></a>Cenários de clientes com suporte

Para essa discussão, suponha que a Contoso administra várias empresas em todo o mundo da seguinte forma. (Observe que as regiões da Europa e APAC são usadas apenas como exemplos. Uma empresa pode ter várias regiões diferentes com requisitos semelhantes.)
 
- **Na Europa,** a Contoso tem escritórios em aproximadamente 30 países. Cada escritório tem seu próprio PBX (Private Branch Exchange). 

  A Contoso foi oferecida uma opção para centralizar os troncos em um único local — Amsterdã — para todos os 30 escritórios europeus. A Contoso implantou o SBC em Amsterdã, forneceu largura de banda suficiente para executar chamadas pelo local centralizado, conectou um tronco SIP central ao local centralizado e começou a atender a todos os locais europeus de Amsterdã. 

- **Na região da APAC,** a Contoso tem vários escritórios em diferentes países. 

  Em muitos países, a empresa ainda tem troncos de multiplexação de divisão de tempo (TDM) em filiais locais. A centralização dos troncos TDM não é uma opção na região APAC, portanto, não é possível alternar para SIP. Suponha que haja mais de 50 filiais da Contoso em toda a região do APAC com centenas de gateways (SBCs). Nesse cenário, não é possível emparelhar todos os gateways para a interface de Roteamento Direto devido à falta de endereços IP públicos e/ou de quebras de internet locais. Além disso, alguns países impõem requisitos regulatórios que não podem ser atendidos sem ter conectividade de rede PSTN local.

Com base em seus requisitos de negócios, a Contoso implementou duas soluções com Otimização de Mídia Local para Roteamento Direto:

- **Na Europa,** todos os troncos são centralizados e os fluxos de mídia entre o SBC central e os usuários, com base na localização do usuário. 

  - Se um usuário estiver conectado à sub-rede local de uma rede corporativa (ou seja, o usuário é interno), a mídia fluirá entre o IP interno do SBC central e o cliente do Teams do usuário. 
  
  - Se um usuário estiver fora dos limites da rede corporativa, por exemplo, se o usuário estiver usando uma conexão de Internet sem fio pública, o usuário será considerado externo. Nesse caso, a mídia flui entre o IP externo do SBC central e o cliente do Teams.

- Na região **APAC,** um SBC proxy centralizado é emparelhado ao Roteamento Direto da Microsoft, que direciona a mídia entre a interface de Roteamento Direto e os SBCs downstream em filiais locais. 

  Os SBCs downstream nas filiais locais não ficam diretamente visíveis ao Roteamento Direto no APAC, mas são emparelhados usando o cmdlet Set-CSOnlinePSTNGateway para criar uma topologia de rede virtual no Microsoft Phone System. A mídia sempre fica local quando possível. Os usuários externos têm mídia fluindo entre o cliente teams e o IP público do SBC proxy.


## <a name="central-sbc-with-centralized-trunks"></a>SBC Central com troncos centralizados

Para criar uma solução na qual os serviços PSTN são fornecidos a todas as filiais locais por meio de um SBC central único com um tronco SIP centralizado conectado, o administrador de locatários da Contoso emparelha um SBC (centralsbc.contoso.com) ao serviço; O SBC tem um tronco SIP centralizado conectado a ele. 

- Quando um usuário está na rede interna da empresa, o SBC fornece o IP interno do SBC para mídia. 

- Quando um usuário está fora da rede corporativa, o SBC fornece o IP externo (público) do SBC.

Observação: todos os valores em exemplos, tabelas ou diagramas são apresentados apenas para fins de ilustração.

Tabela 1. Exemplo de parâmetros de rede para SBCs 

| Local | SBC FQDN | Sub-rede interna | NAT externo (IP confiável) | Endereço IP externo SBC | Endereço IP interno do SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdã | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Alemanha | Não implantado | 192.168.6.0/24 | 172.16.76.74 | Não implantado |  Não implantado |
| França | Não implantado | 192.168.7.0/24 | 172.16.76.75 | Não implantado |  Não implantado ||||


### <a name="internal-user"></a>Usuário interno

O diagrama a seguir mostra o fluxo de tráfego quando um usuário está conectado à rede corporativa na filial ou no site do usuário. 

No local, o usuário é atribuído à filial local na Alemanha. O usuário faz uma chamada telefônica de Roteamento Direto por meio do Teams.

- O cliente do Teams do usuário se comunica ao Sistema Telefônico diretamente por meio da API REST, mas a mídia gerada durante a chamada flui para o endereço IP interno do SBC central. 

- O SBC redireciona o fluxo para o Sistema telefônico e a rede PSTN conectada. 

- O SBC central é visível para o Sistema telefônico apenas por meio do endereço IP externo. 

Diagrama 1. Fluxo de tráfego quando o usuário está no site "home" com um SBC centralizado e com um Tronco SIP centralizado conectado

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-1.png "Fluxo de tráfego quando o usuário está no site 'home' com SBC centralizado com Tronco SIP centralizado conectado")


### <a name="external-user"></a>Usuário externo

O diagrama a seguir mostra o fluxo de tráfego quando um usuário não está no local e não está conectado à rede corporativa (ou seja, o dispositivo do usuário está conectado à Internet por meio de um dispositivo móvel ou wi-fi público). O usuário faz uma chamada telefônica de Roteamento Direto pelo Teams:

- O cliente do Teams do usuário se comunica ao Sistema Telefônico diretamente por meio da API REST, mas, nesse caso, a mídia gerada durante a chamada flui para o endereço IP externo do SBC central. 

- O SBC redireciona o fluxo para o Sistema telefônico e a rede PSTN conectada. 

- O SBC central é visível para o Sistema telefônico apenas por meio do endereço IP externo. 

Nesse caso, o comportamento é semelhante se o usuário é local da filial na Alemanha ou de qualquer outra filial. O usuário é considerado externo porque o usuário está fora dos limites da rede corporativa.

Diagrama 2. Fluxo de tráfego quando o usuário está externo com um SBC centralizado e com um Tronco SIP centralizado conectado

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-2.png "Fluxo de tráfego quando o usuário é externo em caso de SBC centralizado com tronco SIP centralizado conectado")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC proxy com SBCs conectados nostream

Para criar uma solução na qual os serviços PSTN são fornecidos em todas as filiais locais na região APAC, onde a centralização dos troncos TDM não é uma opção, o administrador da Contoso emparelha um SBC (proxysbc.contoso.com), também chamado de SBC proxy, para o serviço roteamento direto. 

Posteriormente, o administrador da Contoso adiciona alguns SBCs downstream indicando que eles podem ser alcançados por meio do SBC proxy proxysbc.contoso.com. Os SBCs downstream não têm IPs públicos, no entanto, eles podem ser atribuídos a rotas de voz. A tabela a seguir mostra exemplos de parâmetros de rede e configurações.

Quando um usuário está na filial local onde o SBC downstream está localizado, o tráfego de mídia flui diretamente entre o usuário e o SBC downstream local. Se um usuário estiver fora do escritório (em uma Internet pública), a mídia fluirá do usuário para o IP público do SBC Proxy, que o proxifica para os SBC(s) downstream(s) relevantes.

Tabela 2. Exemplo de informações de rede SBC

| Local | SBC FQDN | Sub-rede interna | NAT externo (IP confiável) | Endereço IP externo SBC  | Endereço IP interno do SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnã | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Nenhum |  192.168.1.5 |
| Indonésia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Nenhum |  192.168.2.5 |
| Singapura | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Usuário interno 

O diagrama a seguir mostra o fluxo de tráfego de alto nível para o cenário quando um usuário está dentro do escritório na região APAC. O usuário, que está atribuído a uma filial local no Vietnã, e está no local, faz uma chamada telefônica de Roteamento Direto por meio do Teams. 

- O cliente do Teams do usuário se comunica com o Sistema telefônico diretamente por meio da API REST, mas a mídia gerada durante a chamada flui para o endereço IP interno do SBC local.

- O SBC local redireciona o fluxo para o SBC proxy em Cingapura e para a rede PSTN local conectada.

-  O SBC proxy é visível para o Sistema telefônico apenas por meio do endereço IP externo e encaminha o fluxo do SBC downstream (nesse caso, o SBC local no Vietnã) para o Sistema Telefônico. 

- O SBC downstream na filial local não é visível diretamente ao Sistema telefônico, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso ao configurar a Otimização de Mídia Local.

Observação: o comportamento pode ser diferente para usuários locais e usuários não locais, dependendo do modo de Otimização de Mídia Local configurado. 

Para obter mais informações sobre possíveis modos e comportamento relevante, consulte Configurar Otimização de Mídia Local.

Diagrama 3. Fluxo de tráfego quando o usuário está na rede "home" com um SBC proxy e com SBCs conectados abaixo do fluxo 

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-3.png "Fluxo de tráfego em caso de SBC proxy com SBCs conectados ao fluxo de trabalho quando o usuário está na rede "home"")

### <a name="external-user"></a>Usuário externo

O diagrama a seguir mostra o fluxo de tráfego quando um usuário está fora dos limites da rede corporativa. O usuário não está no local (não está dentro dos limites da rede corporativa). O usuário faz uma chamada telefônica de Roteamento Direto pelo Teams para um número de telefone no Vietnã. 

- O cliente do Teams do usuário se comunica com o Sistema telefônico diretamente por meio da API REST, mas a mídia gerada durante a chamada flui primeiro para o endereço IP externo do SBC proxy em Cingapura. 

- Com base na configuração e nas políticas de voz (consulte Configurar Otimização de Mídia [Local](direct-routing-media-optimization-configure.md) para obter detalhes), o SBC proxy redireciona o fluxo para o SBC downstream no Vietnã. 

- O SBC downstream no Vietnã redireciona o fluxo para a rede PSTN local conectada. 

- O SBC proxy é visível para o Sistema telefônico apenas por meio do endereço IP externo.

-  O SBC downstream na filial local não é visível diretamente ao Sistema telefônico, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso ao configurar a Otimização de Mídia Local. No exemplo, o usuário é considerado externo porque o usuário está fora dos limites da rede corporativa. 

Diagrama 4. Fluxo de tráfego quando o usuário está externo com um SBC proxy e com SBCs conectados astream

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-4.png "Fluxo de tráfego em caso de SBC proxy com SBCs conectados abaixo do fluxo quando o usuário é externo")

## <a name="local-media-optimization-modes"></a>Modos de Otimização de Mídia Local

A Otimização de Mídia Local dá suporte a dois modos:

- **Modo 1: Ignorar sempre.** Nesse caso, se o usuário for interno, a mídia fluirá pelo endereço IP interno do SBC downstream local, independentemente da localização real do usuário interno; por exemplo, dentro da mesma filial onde o SBC downstream está localizado ou em alguma outra filial.  

- **Modo 2: somente para usuários locais.** Nesse modo, a mídia fluirá diretamente para o endereço IP interno do SBC no downstream local somente quando gerado pelo usuário interno localizado na mesma filial que o SBC downstream. 

Para distinguir entre os modos de Otimização de Mídia Local, o administrador do locatário precisa definir o parâmetro -BypassMode como "Sempre" ou "OnlyForLocalUsers" para cada SBC usando o cmdlet Set-CSonlinePSTNGateway. Para obter mais informações, consulte [Configurar Otimização de Mídia Local.](direct-routing-media-optimization-configure.md)  

 > [!NOTE]
  > Quando os usuários são internos, a conectividade de mídia entre o usuário e o SBC sobre o endereço IP **interno é necessária.** Não há nenhuma retransmissão de transporte público para mídia nesse caso, pois o SBC fornecerá um IP interno para conectividade de mídia. 

### <a name="mode-1-always-bypass"></a>Modo 1: Ignorar sempre

Se você tiver uma boa conexão entre filiais, o modo recomendado é Sempre ignorar.
 
Por exemplo, suponha que uma empresa tenha um tronco SIP centralizado em Amsterdã, que atende a 30 países e tem boa conectividade entre todos os 30 sites e usuários locais. Também há uma ramificação na Alemanha onde um SBC local é implantado.

O SBC na Alemanha pode ser configurado no modo "Sempre ignorar". Os usuários, independentemente de sua localização, se conectarão ao SBC diretamente por meio do endereço IP interno do SBC (por exemplo, da França à Alemanha; consulte o diagrama abaixo para referência).

O seguinte descreve dois cenários:

- Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online.

- Cenário 2. O usuário e os gateways estão em sites diferentes.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online

O SBC em Amsterdã está configurado para ser um SBC proxy para um SBC downstream local na Alemanha. O usuário está na Alemanha na mesma sub-rede que a rede corporativa do SBC local. Ambos os SBCs (proxy e downstream) estão configurados para o modo Sempre Ignorar. As políticas de roteamento de voz online especificam que, em caso de chamadas na Alemanha (com código de área +49), elas devem ser roteada para o SBC local na Alemanha. Todas as outras chamadas , e caso o SBC na Alemanha falhe, chamadas na Alemanha, devem ser roteados para o SBC proxy em Amsterdã. A tabela a seguir resume a configuração de exemplo. 

Tabela 3. Configuração de exemplo para o Cenário 1

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia | 
|:------------|:-------|:-------|:-------|:-------|
| Alemanha | +49 1 437 2800 | Prioridade 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com<br>Prioridade 2: .* - proxysbc.contoso.com| DEsbc.contoso.com – Sempre Ignorar <br>proxysbc.contoso.com – Sempre Ignorar | Usuários do Teams <–> DEsbc.contoso.com |

O diagrama a seguir mostra o fluxo de tráfego de alto nível para o usuário interno na Alemanha fazer uma chamada telefônica de Roteamento Direto pelo Teams para o número na Alemanha. 

- O cliente do Teams do usuário se comunica com o Sistema telefônico diretamente por meio da API REST. 

- A mídia gerada durante a chamada flui para o endereço IP interno do SBC local. 

- O SBC local redireciona o fluxo para o SBC proxy em Amsterdã e para a rede PSTN local conectada. 

- O SBC proxy é visível para o Sistema telefônico apenas por meio do endereço IP externo e encaminha o fluxo do SBC downstream (nesse caso, o SBC local na Alemanha) para o Sistema telefônico. 

- O SBC downstream na filial local não é visível diretamente ao Sistema telefônico, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso ao configurar a Otimização de Mídia Local.


Diagrama 5.  Fluxo de tráfego com o modo "Sempre Ignorar" e o usuário está no site "home"

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-5.png "Fluxo de tráfego com o modo "Sempre Ignorar" e o usuário está no site "home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Cenário 2: o usuário e os gateways estão em sites diferentes

O SBC em Amsterdã está configurado para ser um SBC proxy para um SBC downstream local na Alemanha. Ambos os SBCs (proxy e downstream) estão configurados para o modo Sempre Ignorar. O usuário interno na França, localizado na filial local, está fazendo uma chamada de Roteamento Direto para a Alemanha. As políticas de roteamento de voz online especificam que as chamadas para a Alemanha (com código de área +49) devem ser roteada para o SBC local na Alemanha. Todas as outras chamadas e, caso o SBC na Alemanha falhe, todas as chamadas na Alemanha devem ser roteados para o SBC proxy em Amsterdã. A tabela a seguir resume a configuração de exemplo. 

Tabela 4. Configuração de exemplo para o Cenário 2

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia | 
|:------------|:-------|:-------|:-------|:-------|
| França | +49 1 437 2800 | Prioridade 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com <br>Prioridade 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com – Sempre Ignorar proxysbc.contoso.com – Sempre Ignorar | Usuários do Teams <– > DEsbc.contoso.com  |

O diagrama a seguir mostra o fluxo de tráfego de alto nível quando o usuário alemão interno localizado na França faz uma chamada telefônica de Roteamento Direto pelo Teams para o número na Alemanha. 

- O cliente do Teams do usuário se comunica com o Sistema telefônico diretamente por meio da API REST.

- A mídia gerada durante a chamada flui diretamente para o SBC no endereço IP interno da Alemanha. 

- O SBC na Alemanha redireciona o fluxo para o SBC proxy em Amsterdã e para a rede PSTN local conectada. 

Diagrama 6.  O fluxo de tráfego com o modo "Sempre Ignorar" e o usuário não está no site "home", mas na rede interna

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-6.png "O fluxo de tráfego com o modo "Sempre Ignorar" e o usuário não está no site "home", mas na rede interna")

### <a name="mode-2-only-for-local-users"></a>Modo 2: somente para usuários locais

Se houver conexões ruins entre filiais locais, mas boas conexões entre cada filial local e escritório regional, o modo recomendado será "Somente para usuários locais".

Por exemplo, na região da APAC, suponha que a Contoso tenha vários escritórios em diferentes países. Para muitos países, a mudança para SIP não é possível porque a empresa ainda tem troncos TDM em muitas filiais locais. A centralização dos troncos TDM não é uma opção na região APAC. Além disso, há mais de 50 filiais da Contoso na região do APAC com centenas de gateways (SBCs). 

Para criar uma solução na qual os serviços PSTN são fornecidos em todas as filiais locais na região APAC, onde a centralização dos troncos TDM não é uma opção, o administrador da Contoso emparelha um SBC regional em Cingapura como SBC proxy para o serviço de Roteamento Direto. A conexão direta entre as filiais locais não é boa, mas há uma boa conexão entre cada filial local e o SBC regional em Cingapura. Para o SBC regional, o administrador escolhe o modo "Sempre Ignorar" e, para os SBCs locais downstream, o administrador escolhe o modo "Somente para Usuários Locais".

O seguinte descreve dois cenários:

- Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online

- Cenário 2. O usuário e os gateways estão em sites diferentes

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online

Suponha que o SBC em Cingapura está configurado para ser um SBC proxy para os SBCs locais downstream no Vietnã e na Indonésia. O usuário está no Vietnã no mesmo local que o SBC local. As políticas de roteamento de voz online especificam que as chamadas no Vietnã (com código de área +84) devem ser roteada para o SBC local no Vietnã. Todas as outras chamadas e, se o SBC no Vietnã falhar, as chamadas no Vietnã devem ser roteados para o SBC proxy em Cingapura. A tabela a seguir resume a configuração de exemplo. 

Tabela 5. Configuração de exemplo para o modo "Somente para usuários locais" Cenário 1

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnã | +84 4 3926 3000 | Prioridade 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br>Prioridade 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – somente para usuários locais <br> proxysbc.contoso.com – Sempre Ignorar | Usuários do Teams <–> VNsbc.contoso.com |

No diagrama a seguir, um usuário atribuído à filial local no Vietnã, enquanto estiver no local, faz uma chamada telefônica de Roteamento Direto por meio do Teams. 

- O cliente do Teams do usuário se comunica com o Sistema telefônico diretamente por meio da API REST. 

- A mídia gerada durante a chamada flui para o endereço IP interno do SBC local. 

- O SBC local redireciona o fluxo para o SBC proxy em Cingapura e para a rede PSTN local conectada. 

- O SBC proxy é visível para o Sistema Telefônico apenas por meio do endereço IP externo e encaminha o fluxo do SBC downstream (nesse caso, o SBC local no Vietnã) para o Sistema telefônico. 

- O SBC downstream na filial local não é visível diretamente ao Sistema Telefônico, mas é mapeado dentro da topologia de rede virtual.

Diagrama 7. Fluxo de tráfego com o modo "Somente para Usuários Locais" e o usuário está no site "home"

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-7.png "O fluxo de tráfego com o modo "Somente para Usuários Locais" e o usuário está no site "home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Cenário 2. O usuário e os gateways estão em sites diferentes

Suponha que o SBC em Cingapura está configurado para ser um SBC proxy para os SBCs locais downstream no Vietnã e na Indonésia. O usuário interno na Indonésia, localizado na filial local, está fazendo uma chamada de Roteamento Direto para o Vietnã. As políticas de roteamento de voz online especificam que as chamadas para o Vietnã (com código de área +84) devem ser roteada para o SBC local no Vietnã. Todas as outras chamadas e, caso o SBC no Vietnã falhe, as chamadas para o Vietnã devem ser roteados para o SBC proxy em Cingapura. O SBC proxy em Cingapura está definido como modo "Sempre Ignorar" e o SBC local no Vietnã é definido como o modo "Somente para Usuários Locais". A tabela a seguir resume a configuração de exemplo. 

Tabela 6. Configuração do usuário

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia | 
|:------------|:-------|:-------|:-------|:-------|
| Indonésia | +84 4 3926 3000 | Prioridade 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridade 2: .* - proxysbc.contoso.com |VNsbc.contoso.com – somente para usuários locais <br> proxysbc.contoso.com – Sempre Ignorar | Usuário do Teams <–> proxysbc.contoso.com <–> VNsbc.contoso.com |


No diagrama a seguir, o usuário interno, enquanto estiver no local da filial indonésia, faz uma chamada telefônica de Roteamento Direto pelo Teams para um número no Vietnã. 

- O cliente do Teams do usuário se comunica com o Sistema telefônico diretamente por meio da API REST.

- A mídia gerada durante a chamada flui primeiro para o endereço IP interno do proxy SBC. 

- O SBC proxy em Cingapura redireciona o fluxo para o endereço IP interno do SBC downstream no Vietnã e para o Sistema Telefônico. 

- O SBC downstream no Vietnã encaminha o fluxo para a rede PSTN local conectada. 

- O SBC proxy é visível para o Sistema telefônico apenas por meio do endereço IP externo.

- Os SBCs downstream em filiais locais não são visíveis diretamente para o Sistema telefônico, mas são mapeados dentro da topologia de rede virtual.

Diagrama 8.  O fluxo de tráfego com o modo "Somente para Usuários Locais" e o usuário não está no site "home", mas na rede interna

![Diagrama mostrando otimização de mídia local de fluxo de tráfego](media/direct-routing-media-op-8.png "Fluxo de tráfego com o modo "Somente para Usuários Locais", o usuário não está no site "página", mas na rede interna")

## <a name="known-issues"></a>Problemas conhecidos

Veja a seguir uma lista de problemas conhecidos que estão presentes no momento na Otimização de Mídia Local. A Microsoft está trabalhando para resolver esses problemas.

| Problema | Solução alternativa |
| :--- | :--- |
| O cliente do Teams não é identificado **como interno quando** o IP público do cliente do Teams corresponde à lista ip confiável do cliente. | A Otimização de Mídia Local requer que a sub-rede do cliente teams corresponde a uma [sub-rede de rede configurada pelo locatário](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)|
| As escalações de chamadas resultam em chamadas desaloadas quando o cliente do Teams é identificado como interno.| Desabilitar a Otimização de Mídia Local no SBC de Roteamento Direto.|


