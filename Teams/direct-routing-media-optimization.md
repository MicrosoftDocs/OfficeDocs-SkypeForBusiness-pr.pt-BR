---
title: Otimização direta de roteamento de mídia local
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
ms.openlocfilehash: ebf6ca7b8b3c1bd18ffb5c00f124d90f973c4b46
ms.sourcegitcommit: aec9fcc178c227d9cfe3e2bf57d0f3bf4c318d49
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48950785"
---
# <a name="local-media-optimization-for-direct-routing"></a>Otimização de mídia local para roteamento direto

A voz de rede telefônica pública comutada (PSTN) é considerada um aplicativo essencial para os negócios, com alta expectativa de qualidade de voz. O roteamento direto permite que você controle o fluxo de tráfego de mídia para acomodar diversas topologias de rede e configurações de telefonia locais para várias empresas ao redor do mundo. 

A otimização de mídia local para roteamento direto permite que você gerencie a qualidade da voz por:

-   Controlar o fluxo de tráfego de mídia entre os clientes do Teams e os controladores de borda da sessão (SBCs) do cliente.
-   Manter a mídia local dentro dos limites de sub-redes de rede corporativa.
-   Permitir fluxos de mídia entre os clientes do Teams e o SBCs mesmo se o SBCs estiver atrás de firewalls corporativos com IPs privados e não visíveis diretamente para a Microsoft.

A otimização de mídia local dá suporte a dois cenários:

- Centralização de todos os troncos locais por meio de um SBC centralizado conectado ao tronco SIP (protocolo de iniciação de sessão principal)-fornecendo serviços de telefonia a todas as filiais locais da empresa.

-   Criar uma topologia de rede virtual de SBCs--onde o SBCs nas filiais locais está conectado a um SBC de proxy centralizado que é visível para e se comunicando com o sistema telefônico da Microsoft por meio de seu endereço IP externo. Em uma topologia de rede virtual, a SBCs (downstream) se comunica através de IPs internos e não fica visível diretamente para o sistema telefônico.

Este artigo descreve a funcionalidade dos recursos e as soluções e os cenários dos clientes. Para obter detalhes sobre a configuração, consulte [Configurar a otimização de mídia local](direct-routing-media-optimization-configure.md). 

  > [!NOTE]
  > Se você quiser manter a mídia local dentro dos limites da sua intranet, recomenda-se a otimização de mídia local. Se você já tiver o recurso de ignorar mídias e usar somente os endereços IP públicos do seu SBCs, não será obrigatório se mover para a otimização de mídia local. Você pode continuar a usar o bypass de mídia. Para obter mais informações, consulte [planejar o bypass de mídia](direct-routing-plan-media-bypass.md).


## <a name="supported-customer-scenarios"></a>Cenários de cliente com suporte

Para esta discussão, suponha que a contoso executa várias empresas em todo o mundo da seguinte maneira. (Observe que as regiões Europa e Ásia-oeste são usadas apenas como exemplos. Uma empresa pode ter várias regiões diferentes com requisitos semelhantes.)
 
- **Na Europa** , a contoso tem escritórios em cerca de 30 países. Cada escritório tem sua própria agência de intercâmbio privada (PBX). 

  A contoso ofereceu uma opção para centralizar os troncos em um local--Amsterdã--para todos os 30 escritórios europeus. A contoso implantou o SBC em Amsterdã, desde largura de banda suficiente para executar chamadas por meio do local centralizado, conectar um tronco SIP central ao local centralizado e começar a servir todos os locais europeus do Amsterdã. 

- **Na região da Ásia, a** contoso tem vários escritórios em diferentes países. 

  Em muitos países, a empresa ainda tem troncos TDM (multiplexação de divisão de tempo) em filiais locais. A centralização dos troncos TDM não é uma opção na região da Ásia e, portanto, não é possível mudar para SIP. Suponha que há mais de 50 filiais da Contoso na região da Ásia-Pacífico com centenas de gateways (SBCs). Nesse cenário, não é possível emparelhar todos os gateways para a interface de roteamento direto devido a falta de endereços IP públicos e/ou debates locais na Internet. Além disso, alguns países impõem requisitos regulatórios que não podem ser atendidos sem conectividade de rede PSTN local.

Com base em suas necessidades comerciais, a contoso implementou duas soluções com otimização de mídia local para roteamento direto:

- **Na Europa** , todos os troncos são centralizados e os fluxos de mídia entre o SBC central e os usuários, com base no local do usuário. 

  - Se um usuário estiver conectado à sub-rede local de uma rede corporativa (ou seja, o usuário for interno), o fluxo de mídia entre o IP interno do SBC central e o cliente das equipes do usuário. 
  
  - Se um usuário estiver fora dos limites da rede corporativa, por exemplo, se o usuário estiver usando uma conexão de Internet pública sem fio--então o usuário será considerado externo. Nesse caso, a mídia flui entre o IP externo do SBC central e o cliente da equipe.

- **Na região da Ásia** , um SBC de proxy centralizado está emparelhado ao direcionamento direto da Microsoft, que direciona a mídia entre a interface de roteamento direto e a SBCS de downstream em filiais locais. 

  O SBCs downstream nas filiais locais não está diretamente visível para o roteamento direto na Ásia, mas eles são emparelhados usando o cmdlet Set-CSOnlinePSTNGateway para criar uma topologia de rede virtual no sistema telefônico da Microsoft. A mídia sempre fica local quando possível. Os usuários externos têm fluxo de mídia entre o cliente da equipe e o IP público do SBC do proxy.


## <a name="central-sbc-with-centralized-trunks"></a>SBC central com troncos centralizados

Para criar uma solução em que os serviços PSTN sejam fornecidos a todas as filiais locais por meio de um único SBC central com um tronco SIP centralizado conectado, o administrador do locatário da Contoso emparelha um SBC (centralsbc.contoso.com) para o serviço; o SBC tem um tronco SIP centralizado conectado a ele. 

- Quando um usuário está na rede interna da empresa, o SBC fornece o IP interno do SBC para mídia.

- Quando um usuário está fora da rede corporativa, o SBC fornece o IP externo (público) do SBC.

Observação: todos os valores dentro de exemplos, tabelas ou diagramas são apresentados somente para fins ilustrativos.

Tabela 1. Exemplo de parâmetros de rede para SBCs 

| Local | O FQDN DO SBC | Sub-rede interna | NAT externo (IP confiável) | Endereço IP externo do SBC | Endereço IP interno do SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdã | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Alemanha | Não implantado | 192.168.6.0/24 | 172.16.76.74 | Não implantado |  Não implantado |
| França | Não implantado | 192.168.7.0/24 | 172.16.76.75 | Não implantado |  Não implantado ||||


### <a name="internal-user"></a>Usuário interno

O diagrama a seguir mostra o fluxo de tráfego quando um usuário está conectado à rede corporativa no escritório ou no site da filial de casa do usuário. 

Enquanto você estiver em um local, o usuário será atribuído à filial local na Alemanha. O usuário faz uma chamada telefônica direta por meio do teams.

- O cliente das equipes do usuário se comunica com o sistema telefônico diretamente por meio da API REST, mas a mídia gerada durante a chamada flui para o endereço IP interno do SBC central. 

- O SBC redireciona o fluxo para o sistema telefônico e a rede PSTN conectada. 

- O SBC central é visível para o sistema telefônico apenas por meio do endereço IP externo. 

Diagrama 1. Fluxo de tráfego quando o usuário está no site ' Home ' com um SBC centralizado e com um tronco SIP centralizado conectado

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-1.png "Fluxo de tráfego quando o usuário está no site ' página inicial ' com SBC centralizado com tronco SIP centralizado conectado")


### <a name="external-user"></a>Usuário externo

O diagrama a seguir mostra o fluxo de tráfego quando um usuário não está em local e não está conectado à rede corporativa (ou seja, o dispositivo do usuário está conectado à Internet por meio de um dispositivo móvel ou Wi-Fi público). O usuário faz uma chamada telefônica direta por meio do teams:

- O cliente do teams do usuário se comunica com o sistema telefônico diretamente por meio da API REST, mas, nesse caso, a mídia gerada durante a chamada flui para o endereço IP externo do SBC central. 

- O SBC redireciona o fluxo para o sistema telefônico e a rede PSTN conectada. 

- O SBC central é visível para o sistema telefônico apenas por meio do endereço IP externo. 

Nesse caso, o comportamento é semelhante se o usuário é local para a filial na Alemanha ou para qualquer outro escritório da filial. O usuário é considerado externo porque o usuário está fora dos limites da rede corporativa.

Diagrama 2. Fluxo de tráfego quando o usuário é externo com um SBC centralizado e com um tronco SIP centralizado conectado

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-2.png "Fluxo de tráfego quando o usuário é externo em caso de SBC centralizado com tronco SIP centralizado conectado")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC proxy com SBCs downstream conectada

Para criar uma solução em que os serviços PSTN sejam fornecidos em todas as filiais locais na região da Ásia, em que a centralização dos troncos de TDM não é uma opção, o administrador da Contoso emparelha um SBC (proxysbc.contoso.com), também chamado de SBC proxy, para o serviço de roteamento direto. 

Posteriormente, o administrador da Contoso adiciona um SBCs downstream indicando que pode ser alcançado por meio do proxysbc.contoso.com do SBC do proxy. No entanto, o SBCs downstream não tem IPs públicos pode ser atribuído a rotas de voz. A tabela a seguir mostra exemplos de configuração e parâmetros de rede.

Quando um usuário está no escritório de filial local onde o SBC downstream está localizado, o tráfego de mídia flui entre o usuário e o SBC downstream local diretamente. Se um usuário estiver fora do escritório (em uma Internet pública), a mídia flui do usuário para o IP público do SBC do proxy, que os proxies para os SBC (s) downstream (es) relevantes.

Tabela 2. Exemplo de informações de rede SBC

| Local | O FQDN DO SBC | Sub-rede interna | NAT externo (IP confiável) | Endereço IP externo do SBC  | Endereço IP interno do SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnã | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Nenhum |  192.168.1.5 |
| Indonésia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Nenhum |  192.168.2.5 |
| Singapura | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Usuário interno 

O diagrama a seguir mostra o fluxo de tráfego de alto nível para o cenário quando um usuário está dentro do escritório na região da Ásia. O usuário, que é atribuído a uma filial local no Vietnã, e local, faz uma chamada telefônica direta por meio do teams. 

- O cliente das equipes do usuário se comunica com o sistema telefônico diretamente por meio da API REST, mas a mídia gerada durante a chamada flui para o endereço IP interno do SBC local.

- O SBC local redireciona o fluxo para o SBC do proxy em Cingapura e para a rede PSTN local conectada.

-  O SBC do proxy é visível para o sistema telefônico apenas por meio do endereço IP externo e roteia o fluxo do SBC (neste caso, o SBC local no Vietnã) para o sistema telefônico. 

- O SBC downstream na ramificação local não fica visível para o sistema telefônico diretamente, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso durante a configuração da otimização de mídia local.

Observação: o comportamento pode ser diferente para usuários locais e usuários não locais, dependendo do modo de otimização de mídia local configurado. 

Para obter mais informações sobre possíveis modos e comportamentos relevantes, consulte Configurar a otimização de mídia local.

Diagrama 3. Fluxo de tráfego quando o usuário está na rede "Home" com um SBC proxy e com SBCs downstream conectada 

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-3.png "Fluxo de tráfego no caso do SBC de proxy com SBCs downstream conectada quando o usuário está na rede "página inicial"")

### <a name="external-user"></a>Usuário externo

O diagrama a seguir mostra o fluxo de tráfego quando um usuário está fora dos limites da rede corporativa. O usuário não está local (não está dentro dos limites da rede corporativa). O usuário faz uma chamada telefônica direta por meio do teams para um número de telefone no Vietnã. 

- O cliente das equipes do usuário se comunica com o sistema telefônico diretamente por meio da API REST, mas a mídia gerada durante os fluxos de chamadas primeiro para o endereço IP externo do SBC do proxy em Cingapura. 

- Com base em políticas de configuração e voz (consulte [Configurar a otimização de mídia local](direct-routing-media-optimization-configure.md) para obter detalhes), o SBC do proxy redireciona o fluxo para o SBC downstream no Vietnã. 

- O SBC downstream no Vietnã redireciona o fluxo para a rede PSTN local conectada. 

- O SBC do proxy é visível para o sistema telefônico apenas por meio do endereço IP externo.

-  O SBC downstream na ramificação local do Office não é visível diretamente para o sistema telefônico, mas é mapeado na topologia de rede virtual definida pelo administrador da Contoso durante a configuração da otimização de mídia local. No exemplo, o usuário é considerado externo porque o usuário está fora dos limites da rede corporativa. 

Diagrama 4. Fluxo de tráfego quando o usuário é externo com um SBC de proxy e com SBCs downstream conectada

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-4.png "Fluxo de tráfego no caso do SBC de proxy com SBCs downstream conectada quando o usuário é externo")

## <a name="local-media-optimization-modes"></a>Modos de otimização de mídia local

A otimização de mídia local dá suporte a dois modos:

- **Modo 1: sempre ignorar**. Nesse caso, se o usuário for interno, a mídia irá fluir pelo endereço IP interno do SBC downstream local, independentemente da localização real do usuário interno; por exemplo, dentro da mesma filial do trabalho em que o SBC downstream está localizado ou em algum outro escritório da filial.

- **Modo 2: somente para usuários locais**. Nesse modo, a mídia fluirá diretamente para o endereço IP interno do SBC do SBC local somente quando gerado pelo usuário interno localizado na mesma filial do trabalho como o SBC downstream. 

Para distinguir entre os modos de otimização de mídia local, o administrador de locatários precisa definir o parâmetro-Bypassmode como "Always" ou "OnlyForLocalUsers" para cada SBC usando o cmdlet Set-CSonlinePSTNGateway. Para obter mais informações, consulte [Configurar otimização de mídia local](direct-routing-media-optimization-configure.md).  

### <a name="mode-1-always-bypass"></a>Modo 1: ignorar sempre

Se você tiver uma boa conexão entre filiais, o modo recomendado será sempre ignorado.

Por exemplo, suponha que uma empresa tem um tronco SIP centralizado em Amsterdã, que tem 30 países e tem uma boa conectividade entre todos os 30 sites e usuários locais. Também há uma ramificação na Alemanha na qual um SBC local é implantado.

O SBC na Alemanha pode ser configurado no modo "sempre ignorar". Os usuários, independentemente de sua localização, serão conectados ao SBC diretamente por meio do endereço IP interno do SBC (por exemplo, da França para a Alemanha; consulte o diagrama abaixo para obter referência).

O seguinte descreve dois cenários:

- Cenário 1. O usuário está no mesmo local que o SBC definido na política de roteamento de voz online.

- Cenário 2. O usuário e os gateways estão em sites diferentes.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Cenário 1. O usuário está no mesmo local que o SBC definido na política de roteamento de voz online

O SBC em Amsterdã está configurado para ser um SBC de proxy para um SBC downstream local na Alemanha. O usuário está na Alemanha na mesma sub-rede da rede corporativa do SBC local. O SBCs (proxy e downstream) está configurado para o modo sempre ignorar. As políticas de roteamento de voz online especificam que, em caso de chamadas na Alemanha (com código de área + 49) elas devem ser roteadas para o SBC local na Alemanha. Todas as outras chamadas--e, em caso de falha do SBC na Alemanha, as chamadas em Alemanha--devem ser roteadas para o SBC do proxy em Amsterdã. A tabela a seguir resume o exemplo de configuração. 

Tabela 3. Configuração de exemplo para o cenário 1

| Localização física do usuário | O usuário faz uma chamada para um número | Política de roteamento de voz online | Modo configurado para SBC | Fluxo de mídia | 
|:------------|:-------|:-------|:-------|:-------|
| Alemanha | + 49 1 437 2800 | Prioridade 1: ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com<br>Prioridade 2:. *-proxysbc.contoso.com| DEsbc.contoso.com – sempre ignorar <br>proxysbc.contoso.com – sempre ignorar | < de usuários do teams – > DEsbc.contoso.com |

O diagrama a seguir mostra o fluxo de tráfego de alto nível para o usuário interno na Alemanha, que faz uma chamada telefônica direta de roteamento por meio do teams para o número na Alemanha. 

- O cliente das equipes do usuário se comunica com o sistema telefônico diretamente por meio da API REST. 

- A mídia gerada durante a chamada flui para o endereço IP interno do SBC local. 

- O SBC local redireciona o fluxo para o SBC do proxy em Amsterdã e para a rede PSTN local conectada. 

- O SBC do proxy é visível para o sistema telefônico apenas por meio do endereço IP externo e roteia o fluxo do SBC (neste caso, o SBC local na Alemanha) para o sistema telefônico. 

- O SBC downstream na ramificação local não fica visível para o sistema telefônico diretamente, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso durante a configuração da otimização de mídia local.


Diagrama 5.  Fluxo de tráfego com o modo "sempre ignorado" e o usuário está no site "Home"

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-5.png "Fluxo de tráfego com o modo "sempre ignorado" e o usuário está no site "Home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Cenário 2: o usuário e os gateways estão em sites diferentes

O SBC em Amsterdã está configurado para ser um SBC de proxy para um SBC downstream local na Alemanha. O SBCs (proxy e downstream) está configurado para o modo sempre ignorar. O usuário interno na França, localizado na filial local, é fazer uma chamada de roteamento direto para a Alemanha. As políticas de roteamento de voz online especificam que chamadas para a Alemanha (com código de área + 49) devem ser roteadas para o SBC local na Alemanha. Todas as outras chamadas--e, em caso de falha do SBC na Alemanha, todas as chamadas na Alemanha--devem ser roteadas para o SBC do proxy em Amsterdã. A tabela a seguir resume o exemplo de configuração. 

Tabela 4. Configuração de exemplo para o cenário 2

| Localização física do usuário | O usuário faz uma chamada para um número | Política de roteamento de voz online | Modo configurado para SBC | Fluxo de mídia | 
|:------------|:-------|:-------|:-------|:-------|
| França | + 49 1 437 2800 | Prioridade 1: ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com <br>Prioridade 2:. *-proxysbc.contoso.com |  DEsbc.contoso.com – sempre ignorar proxysbc.contoso.com – sempre ignorar | < de usuários do teams – > DEsbc.contoso.com  |

O diagrama a seguir mostra o fluxo de tráfego de alto nível quando o usuário interno do alemão localizado na França faz uma chamada telefônica direta por meio do teams para o número na Alemanha. 

- O cliente das equipes do usuário se comunica com o sistema telefônico diretamente por meio da API REST.

- A mídia gerada durante a chamada flui diretamente para o SBC no endereço IP interno da Alemanha. 

- O SBC na Alemanha redireciona o fluxo para o SBC do proxy em Amsterdã e para a rede PSTN local conectada. 

Diagrama 6.  Fluxo de tráfego com o modo "sempre ignorado" e o usuário não está no site "Home", mas na rede interna

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-6.png "Fluxo de tráfego com o modo "sempre ignorado" e o usuário não está no site "Home", mas na rede interna")

### <a name="mode-2-only-for-local-users"></a>Modo 2: somente para usuários locais

Se houver conexões ruins entre escritórios filiais locais, mas boas conexões entre cada filial local e escritório regional, o modo recomendado será "somente para usuários locais".

Por exemplo, na região da Ásia, suponha que a contoso tenha vários escritórios em países diferentes. Em muitos países, não é possível mudar para o SIP porque a empresa ainda tem troncos de TDM em muitas filiais locais. A centralização dos troncos TDM não é uma opção na região da Ásia. Além disso, há mais de 50 filiais da Contoso na região da Ásia com centenas de gateways (SBCs). 

Para criar uma solução em que os serviços PSTN sejam fornecidos em todas as filiais locais na região da Ásia, em que a centralização dos troncos de TDM não é uma opção, o administrador da Contoso emparelha um SBC regional em Cingapura como o SBC de proxy para o serviço de roteamento direto. A conexão direta entre as filiais locais não é boa, mas há uma boa conexão entre cada filial local e o SBC regional em Cingapura. Para o SBC regional, o administrador escolhe o modo ' sempre ignorar ' e, para o SBCs downstream local, o administrador escolhe ' somente para o modo de usuários locais '.

O seguinte descreve dois cenários:

- Cenário 1. O usuário está no mesmo local que o SBC definido na política de roteamento de voz online

- Cenário 2. O usuário e os gateways estão em sites diferentes

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Cenário 1. O usuário está no mesmo local que o SBC definido na política de roteamento de voz online

Suponha que o SBC em Cingapura esteja configurado como um SBC do proxy para o SBCs downstream local no Vietnã e na Indonésia. O usuário está em Vietnã no mesmo local do SBC local. As políticas de roteamento de voz online especificam que as chamadas no Vietnã (com código de área + 84) devem ser roteadas para o SBC local no Vietnã. Todas as outras chamadas--e, se o SBC no Vietnã falhar, as chamadas no Vietnã--deverão ser roteadas para o SBC do proxy em Cingapura. A tabela a seguir resume o exemplo de configuração. 

Tabela 5. Configuração de exemplo para modo ' somente para usuários locais ' 1

| Localização física do usuário | O usuário faz uma chamada para um número | Política de roteamento de voz online | Modo configurado para SBC | Fluxo de mídia | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnã | + 84 4 3926 3000 | Prioridade 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br>Prioridade 2:. *-proxysbc.contoso.com | VNsbc.contoso.com – somente para usuários locais <br> proxysbc.contoso.com – sempre ignorar | < de usuários do teams – > VNsbc.contoso.com |

No diagrama a seguir, um usuário atribuído à filial local no Vietnã, enquanto em local, faz uma chamada telefônica direta por meio do teams. 

- O cliente das equipes do usuário se comunica com o sistema telefônico diretamente por meio da API REST. 

- Mídia gerada durante o fluxo de chamadas para o endereço IP interno do SBC local. 

- O SBC local redireciona o fluxo para o SBC do proxy em Cingapura e para a rede PSTN local conectada. 

- O SBC do proxy é visível para o sistema telefônico apenas por meio do endereço IP externo e roteia o fluxo do SBC (neste caso, o SBC local no Vietnã) para o sistema telefônico. 

- O SBC downstream na ramificação local não fica visível para o sistema telefônico diretamente, mas é mapeado dentro da topologia de rede virtual.

Diagrama 7. Fluxo de tráfego com o modo "somente para usuários locais" e o usuário está no site "Home"

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-7.png "Fluxo de tráfego com o modo "somente para usuários locais" e o usuário está no site "Home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Cenário 2. O usuário e os gateways estão em sites diferentes

Suponha que o SBC em Cingapura esteja configurado como um SBC do proxy para o SBCs downstream local no Vietnã e na Indonésia. O usuário interno na Indonésia, localizado na filial local, é fazer uma chamada de roteamento direto para o Vietnã. As políticas de roteamento de voz online especificam que chamadas para o Vietnã (com código de área + 84) devem ser roteadas para o SBC local no Vietnã. Todas as outras chamadas--e, em caso de falha do SBC no Vietnã, as chamadas para o Vietnã--devem ser roteadas para o SBC do proxy em Cingapura. O SBC do proxy em Cingapura está definido como o modo ' sempre ignorar ' e o SBC local no Vietnã está definido como ' somente para usuários locais '. A tabela a seguir resume o exemplo de configuração. 

Tabela 6. Configuração do usuário

| Localização física do usuário | O usuário faz uma chamada para um número | Política de roteamento de voz online | Modo configurado para SBC | Fluxo de mídia | 
|:------------|:-------|:-------|:-------|:-------|
| Indonésia | + 84 4 3926 3000 | Prioridade 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Prioridade 2:. *-proxysbc.contoso.com |VNsbc.contoso.com – somente para usuários locais <br> proxysbc.contoso.com – sempre ignorar | < de usuário do teams – > proxysbc.contoso.com < – > VNsbc.contoso.com |


No diagrama a seguir, o usuário interno, enquanto em local no escritório da filial em indonésio, faz uma chamada telefônica direta por meio do teams para um número no Vietnã. 

- O cliente das equipes do usuário se comunica com o sistema telefônico diretamente por meio da API REST.

- Mídia gerada durante o fluxo de chamadas para o endereço IP interno de SBC do proxy primeiro. 

- O SBC do proxy em Cingapura redireciona o fluxo para o endereço IP interno do SBC (downstream) do SBC e para o sistema telefônico. 

- O SBC downstream do Vietnã roteia o fluxo para a rede PSTN local conectada. 

- O SBC do proxy é visível para o sistema telefônico apenas por meio do endereço IP externo.

- O SBCs (downstream) em filiais locais não é visível diretamente para o sistema telefônico, mas são mapeados na topologia de rede virtual.

Diagrama 8.  Fluxo de tráfego com o modo "somente para usuários locais" e o usuário não está no site "Home", mas na rede interna

![Diagrama mostrando a otimização de mídia local do fluxo de tráfego](media/direct-routing-media-op-8.png "Fluxo de tráfego com o modo "somente para usuários locais", o usuário não está no site "Home", mas na rede interna")

## <a name="known-issues"></a>Problemas conhecidos

Veja a seguir uma lista de problemas conhecidos que estão presentes atualmente na otimização de mídia local. A Microsoft está trabalhando para resolver esses problemas.

| Problema | Possíveis |
| :--- | :--- |
| O cliente de equipes não é identificado como **interno** quando o IP público do cliente do teams corresponde à lista de IPs confiáveis do cliente. | A otimização de mídia local requer que a sub-rede do cliente do teams corresponda uma [sub-rede de rede](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) configurada por locatário|
| Os escalonamentos de chamadas resultam em chamadas ignoradas quando o cliente do teams é identificado como interno.| Desabilite a otimização de mídia local no SBC Routing direto.|


