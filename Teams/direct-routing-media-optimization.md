---
title: Otimização de mídia local para roteamento direto
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
ms.openlocfilehash: ce9d25e84c67f5ae8b3b4fec51535d53f7b0044f
ms.sourcegitcommit: 8f26bf0ff88f1f6881de32914be00d5f0cc7396a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69740806"
---
# <a name="plan-for-local-media-optimization-for-direct-routing"></a>Planejar otimização de mídia local para roteamento direto

A voz PSTN (Rede Telefônica ComUtada Pública) é considerada um aplicativo comercialmente crítico, com altas expectativas de qualidade de voz. O Roteamento Direto permite controlar fluxos de tráfego de mídia para acomodar uma infinidade de topologias de rede e configurações de telefonia local para várias empresas em todo o mundo.

A Otimização de Mídia Local para Roteamento Direto permite gerenciar a qualidade da voz por:

- Controlando como o tráfego de mídia flui entre os clientes do Teams e os SBCs (Controladores de Borda de Sessão do cliente).
- Manter a mídia local dentro dos limites das sub-redes de rede corporativa.
- Permitir fluxos de mídia entre os clientes do Teams e os SBCs, mesmo que os SBCs estejam por trás de firewalls corporativos com IPs privados e não visíveis diretamente para a Microsoft.

A Otimização de Mídia Local dá suporte a dois cenários:

- Centralização de todos os troncos locais por meio de um SBC centralizado conectado ao tronco DO SIP (Protocolo de Iniciação de Sessão) principal , fornecendo serviços de telefonia para todas as filiais locais da empresa.

- Criando uma topologia de rede virtual de SBCs — em que os SBCs nas filiais locais estão conectados a um SBC proxy centralizado que é visível e se comunicando com o Sistema de Telefone da Microsoft por meio de seu endereço IP externo. Em uma topologia de rede virtual, os SBCs downstream estão se comunicando por meio de IPs internos e não estão diretamente visíveis ao Sistema telefônico.

Este artigo descreve a funcionalidade do recurso e os cenários e soluções do cliente. Para obter detalhes sobre a configuração, consulte [Configurar otimização de mídia local](direct-routing-media-optimization-configure.md).

  > [!NOTE]
  > Se você quiser manter a mídia local dentro dos limites da sua intranet, é recomendável otimização de mídia local. Se você já tiver o Bypass de Mídia e usar apenas os endereços IP públicos de seus SBCs, não será obrigatório migrar para Otimização de Mídia Local. Você pode continuar a usar o Bypass de Mídia. Para obter mais informações, consulte [Planejar Bypass de Mídia](direct-routing-plan-media-bypass.md).

Para obter informações sobre quais fornecedores SBC dão suporte à Otimização de Mídia Local, consulte [Controladores de Borda de Sessão Certificados para Roteamento Direto](direct-routing-border-controllers.md).

## <a name="supported-customer-scenarios"></a>Cenários de cliente com suporte

Para esta discussão, suponha que a Contoso execute vários negócios em todo o mundo da seguinte maneira. (Observe que as regiões europa e APAC são usadas apenas como exemplos. Uma empresa pode ter várias regiões diferentes com requisitos semelhantes.)

- **Na Europa**, a Contoso tem escritórios em aproximadamente 30 países. Cada escritório tem seu próprio PBX (Private Branch Exchange).

  A Contoso recebeu uma opção para centralizar os troncos em um local - Amsterdã - para todos os 30 escritórios europeus. A Contoso implantou o SBC em Amsterdã, forneceu largura de banda suficiente para executar chamadas através do local centralizado, conectou um tronco SIP central ao local centralizado e começou a atender todos os locais europeus de Amsterdã.

- **Na região da APAC, a** Contoso tem vários escritórios em diferentes países.

  Em muitos países, a empresa ainda tem troncos TDM (divisão temporal) em filiais locais. A centralização dos troncos TDM não é uma opção na região do APAC, portanto, alternar para SIP não é possível. Suponha que existam mais de 50 filiais da Contoso em toda a região da APAC com centenas de gateways (SBCs). Nesse cenário, não é possível emparelhar todos os gateways com a interface de Roteamento Direto devido à falta de endereços IP públicos e/ou fugas de internet locais. Além disso, alguns países impõem requisitos regulatórios que não podem ser atendidos sem ter conectividade de rede PSTN local.

Com base em seus requisitos comerciais, a Contoso implementou duas soluções com Otimização de Mídia Local para Roteamento Direto:

- **Na Europa**, todos os troncos são centralizados e os fluxos de mídia entre o SBC central e os usuários, com base na localização do usuário.

  - Se um usuário estiver conectado à sub-rede local de uma rede corporativa (ou seja, o usuário é interno), a mídia flui entre o IP interno do SBC central e o cliente do Teams do usuário.

  - Se um usuário estiver fora dos limites da rede corporativa , por exemplo, se o usuário estiver usando uma conexão de Internet sem fio pública, o usuário será considerado externo. Nesse caso, a mídia flui entre o IP externo do SBC central e o cliente do Teams.

- **Na região do APAC**, um SBC de proxy centralizado é emparelhado com o Roteamento Direto da Microsoft, que direciona a mídia entre a interface de Roteamento Direto e os SBCs downstream nas filiais locais.

  Os SBCs downstream nas filiais locais não estão diretamente visíveis para o Roteamento Direto na APAC, mas são emparelhados usando o cmdlet Set-CSOnlinePSTNGateway para criar uma topologia de rede virtual no Sistema de Telefone da Microsoft. A mídia sempre permanece local quando possível. Usuários externos têm a mídia fluindo entre o cliente do Teams e o IP público do SBC proxy.

## <a name="central-sbc-with-centralized-trunks"></a>SBC central com troncos centralizados

Para criar uma solução em que os serviços PSTN são fornecidos a todas as filiais locais por meio de um único SBC centralizado com um tronco SIP centralizado conectado, o administrador de locatários da Contoso emparelha um SBC (centralsbc.contoso.com) ao serviço; O SBC tem um tronco SIP centralizado conectado a ele.

- Quando um usuário está na rede interna da empresa, o SBC fornece o IP interno do SBC para mídia.

- Quando um usuário está fora da rede corporativa, o SBC fornece o IP externo (público) do SBC.

> [!NOTE]
> Todos os valores dentro de exemplos, tabelas ou diagramas são apresentados apenas para fins de ilustração.

Tabela 1. Exemplo de parâmetros de rede para SBCs

| Localização | SBC FQDN | Sub-rede interna | NAT externo (IP confiável) | Endereço IP externo do SBC | Endereço IP interno do SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdã | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Alemanha | Não implantado | 192.168.6.0/24 | 172.16.76.74 | Não implantado |  Não implantado |
| França | Não implantado | 192.168.7.0/24 | 172.16.76.75 | Não implantado |  Não implantado |

### <a name="internal-user"></a>Usuário interno

O diagrama a seguir mostra o fluxo de tráfego quando um usuário está conectado à rede corporativa na filial ou site do usuário.

Enquanto estiver no local, o usuário é atribuído à filial local na Alemanha. O usuário faz uma chamada telefônica de Roteamento Direto por meio do Teams.

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST, mas a mídia gerada durante a chamada flui para o endereço IP interno do SBC central.

- O SBC redireciona o fluxo para o Sistema telefônico e a rede PSTN conectada.

- O SBC central é visível para o Sistema de Telefone apenas por meio do endereço IP externo.

Diagrama 1. Fluxo de tráfego quando o usuário está no site 'home' com um SBC centralizado e com um tronco SIP centralizado conectado

![Diagrama mostrando o fluxo de tráfego Otimização de Mídia Local.](media/direct-routing-media-op-1.png "Fluxo de tráfego quando o usuário está no site 'home' com SBC centralizado com tronco SIP centralizado conectado")


### <a name="external-user"></a>Usuário externo

O diagrama a seguir mostra o fluxo de tráfego quando um usuário não está no local e não está conectado à rede corporativa (ou seja, o dispositivo do usuário está conectado à Internet por meio de um dispositivo móvel ou Wi-Fi público). O usuário faz uma chamada telefônica de Roteamento Direto por meio do Teams:

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST, mas, nesse caso, a mídia gerada durante a chamada flui para o endereço IP externo do SBC central.

- O SBC redireciona o fluxo para o Sistema telefônico e a rede PSTN conectada.

- O SBC central é visível para o Sistema de Telefone apenas por meio do endereço IP externo.

Nesse caso, o comportamento é semelhante se o usuário é local para a filial na Alemanha ou para qualquer outra filial. O usuário é considerado externo porque o usuário está fora dos limites da rede corporativa.

Diagrama 2. Fluxo de tráfego quando o usuário está externo com um SBC centralizado e com um tronco SIP centralizado conectado

![Diagrama mostra o fluxo de tráfego Otimização de mídia local.](media/direct-routing-media-op-2.png "Fluxo de tráfego quando o usuário está externo no caso de SBC centralizado com tronco SIP centralizado conectado")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>Proxy SBC com SBCs downstream conectados

Para criar uma solução em que os serviços PSTN são fornecidos em todas as filiais locais na região do APAC, onde a centralização dos troncos TDM não é uma opção, o administrador da Contoso emparelha um SBC (proxysbc.contoso.com), também chamado de SBC proxy, para o serviço de Roteamento Direto.

Posteriormente, o administrador da Contoso adiciona alguns SBCs downstream indicando que eles podem ser acessados por meio do proxy SBC proxysbc.contoso.com. Os SBCs downstream não têm IPs públicos, no entanto, eles podem ser atribuídos a rotas de voz. A tabela abaixo mostra parâmetros de rede e configuração de exemplo.

Quando um usuário está na filial local onde o SBC downstream está localizado, o tráfego de mídia flui diretamente entre o usuário e o SBC downstream local. Se um usuário estiver fora do escritório (em uma internet pública), a mídia flui do usuário para o IP público do SBC proxy, que o proxie para os SBC(s) downstream relevantes.

Tabela 2. Exemplo de informações de rede SBC

| Localização | SBC FQDN | Sub-rede interna | NAT externo (IP confiável) | Endereço IP externo do SBC  | Endereço IP interno do SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnã | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Nenhum |  192.168.1.5 |
| Indonésia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Nenhum |  192.168.2.5 |
| Singapura | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Usuário interno

O diagrama a seguir mostra o fluxo de tráfego de alto nível para o cenário quando um usuário está dentro do escritório na região da APAC.
O usuário, que é atribuído a uma filial local no Vietnã e está no local, faz uma chamada telefônica de Roteamento Direto por meio do Teams.

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST, mas a mídia gerada durante a chamada flui para o endereço IP interno do SBC local.

- O SBC local redireciona o fluxo para o proxy SBC em Cingapura e para a rede PSTN local conectada.

-  O SBC de proxy é visível para o Sistema de Telefone apenas por meio do endereço IP externo e roteia o fluxo do SBC downstream (nesse caso, o SBC local no Vietnã) para o Sistema de Telefonia.

- O SBC downstream na filial local não é visível diretamente para o Sistema de Telefone, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso ao configurar a Otimização de Mídia Local.

> [!NOTE]
> O comportamento pode ser diferente para usuários locais e usuários não locais, dependendo do modo de otimização de mídia local configurado.

Para obter mais informações sobre possíveis modos e comportamento relevante, consulte Configurar Otimização de Mídia Local.

Diagrama 3. Fluxo de tráfego quando o usuário está na rede "home" com um SBC proxy e com SBCs downstream conectados

![Diagrama mostrando novamente o fluxo de tráfego Otimização de mídia local.](media/direct-routing-media-op-3.png "Traffic flow in case of proxy SBC with connected downstream SBCs when user is in the \"home\" network")

### <a name="external-user"></a>Usuário externo

O diagrama a seguir mostra o fluxo de tráfego quando um usuário está fora dos limites de rede corporativa. O usuário não está no local (não está dentro dos limites da rede corporativa). O usuário faz uma chamada telefônica de Roteamento Direto por meio do Teams para um número de telefone no Vietnã.

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST, mas a mídia gerada durante a chamada flui primeiro para o endereço IP externo do proxy SBC em Cingapura.

- Com base em políticas de configuração e voz (consulte [Configurar otimização de mídia local](direct-routing-media-optimization-configure.md) para obter detalhes), o proxy SBC redireciona o fluxo para o SBC downstream no Vietnã.

- O SBC downstream no Vietnã redireciona o fluxo para a rede PSTN local conectada.

- O SBC de proxy fica visível para o Sistema de Telefone somente por meio do endereço IP externo.

-  O SBC downstream na filial local não é visível diretamente para o Sistema de Telefone, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso ao configurar a Otimização de Mídia Local. No exemplo, o usuário é considerado externo porque o usuário está fora dos limites da rede corporativa.

Diagrama 4. Fluxo de tráfego quando o usuário está externo com um SBC proxy e com SBCs downstream conectados

![Diagrama mostra novamente o fluxo de tráfego Otimização de mídia local.](media/direct-routing-media-op-4.png "Fluxo de tráfego no caso de SBC proxy com SBCs downstream conectados quando o usuário está externo")

## <a name="local-media-optimization-modes"></a>Modos de otimização de mídia local

A Otimização de Mídia Local dá suporte a dois modos:

- **Modo 1: sempre ignorar**. Nesse caso, se o usuário for interno, a mídia fluirá pelo endereço IP interno do SBC downstream local, independentemente da localização real do usuário interno; por exemplo, na mesma filial em que o SBC downstream está localizado ou em alguma outra filial.

- **Modo 2: somente para usuários locais**. Nesse modo, a mídia fluirá diretamente para o endereço IP interno do SBC downstream local somente quando gerado pelo usuário interno localizado na mesma filial que o SBC downstream.

Para distinguir entre os modos de Otimização de Mídia Local, o administrador do locatário precisa definir o parâmetro -BypassMode como 'Always' ou 'OnlyForLocalUsers' para cada SBC usando o cmdlet Set-CSonlinePSTNGateway. Para obter mais informações, consulte [Configurar otimização de mídia local](direct-routing-media-optimization-configure.md).

> [!NOTE]
> Quando os usuários são internos, a conectividade de mídia entre o usuário e o SBC sobre o endereço IP interno é **necessária**. Não há retorno para retransmissões de transporte público para mídia nesse caso, pois o SBC fornecerá um IP interno para conectividade de mídia.

### <a name="mode-1-always-bypass"></a>Modo 1: Sempre ignorar

Se você tiver uma boa conexão entre as filiais, o modo recomendado será Sempre ignorar.

Por exemplo, suponha que uma empresa tenha um tronco SIP centralizado em Amsterdã, que atende 30 países e tem boa conectividade entre todos os 30 sites e usuários locais. Há também uma filial na Alemanha onde um SBC local é implantado.

O SBC na Alemanha pode ser configurado no modo "Sempre ignorar". Os usuários, independentemente de sua localização, se conectarão ao SBC diretamente por meio do endereço IP interno do SBC (por exemplo, da França à Alemanha; confira o diagrama abaixo para referência).

O seguinte descreve dois cenários:

- Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online.

- Cenário 2. O usuário e os gateways estão em sites diferentes.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online

O SBC em Amsterdã está configurado para ser um SBC proxy para um SBC downstream local na Alemanha. O usuário está na Alemanha dentro da mesma sub-rede que a rede corporativa do SBC local. Os SBCs (proxy e downstream) são configurados para o modo Always Bypass. As políticas de roteamento de voz online especificam que, em caso de chamadas na Alemanha (com código de área +49), elas devem ser roteadas para o SBC local na Alemanha. Todas as outras chamadas - e caso o SBC na Alemanha falhe, chamadas na Alemanha - devem ser roteadas para o proxy SBC em Amsterdã. A tabela a seguir resume a configuração de exemplo.

Tabela 3. Configuração de exemplo para Cenário 1

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia |
|:------------|:-------|:-------|:-------|:-------|
| Alemanha | +49 1 437 2800 | Prioridade 1: ^\+49(\d{8})$ -DEsbc.contoso.com<br>Prioridade 2: .* – proxysbc.contoso.com| DEsbc.contoso.com – Always Bypass <br>proxysbc.contoso.com – Always Bypass | <-> DEsbc.contoso.com de Usuário do Teams |

O diagrama abaixo mostra o fluxo de tráfego de alto nível para o usuário interno na Alemanha fazendo uma chamada telefônica de Roteamento Direto por meio do Teams para o número na Alemanha.

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST.

- A mídia gerada durante a chamada flui para o endereço IP interno do SBC local.

- O SBC local redireciona o fluxo para o proxy SBC em Amsterdã e para a rede PSTN local conectada.

- O SBC de proxy fica visível para o Sistema de Telefonia apenas por meio do endereço IP externo e roteia o fluxo do SBC downstream (nesse caso, o SBC local na Alemanha) para o Sistema de Telefonia.

- O SBC downstream na filial local não é visível diretamente para o Sistema de Telefone, mas é mapeado dentro da topologia de rede virtual definida pelo administrador da Contoso ao configurar a Otimização de Mídia Local.


Diagrama 5.  Fluxo de tráfego com o modo "Always Bypass" e o usuário está no site "home"

![Um diagrama mostrando o fluxo de tráfego Otimização de Mídia Local.](media/direct-routing-media-op-5.png "Fluxo de tráfego com o modo 'Always Bypass' e o usuário está no site 'home'")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Cenário 2: o usuário e os gateways estão em sites diferentes

O SBC em Amsterdã está configurado para ser um SBC proxy para um SBC downstream local na Alemanha. Os SBCs (proxy e downstream) são configurados para o modo Always Bypass. O usuário interno na França, localizado na filial local, está fazendo uma chamada de Roteamento Direto para a Alemanha. As políticas de roteamento de voz online especificam que as chamadas para a Alemanha (com código de área +49) devem ser roteadas para o SBC local na Alemanha. Todas as outras chamadas - e, caso o SBC na Alemanha falhe, todas as chamadas na Alemanha - devem ser roteadas para o proxy SBC em Amsterdã. A tabela a seguir resume a configuração de exemplo.

Tabela 4. Configuração de exemplo para o Cenário 2

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia |
|:------------|:-------|:-------|:-------|:-------|
| França | +49 1 437 2800 | Prioridade 1: ^\+49(\d{8})$ -DEsbc.contoso.com <br>Prioridade 2: .* – proxysbc.contoso.com |  DEsbc.contoso.com – Always Bypass proxysbc.contoso.com – Always Bypass | < de Usuário do Teams: > DEsbc.contoso.com  |

O diagrama a seguir mostra o fluxo de tráfego de alto nível quando o usuário alemão interno localizado na França faz uma chamada telefônica de Roteamento Direto por meio do Teams para o número na Alemanha.

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST.

- A mídia gerada durante a chamada flui diretamente para o SBC no endereço IP interno da Alemanha.

- O SBC na Alemanha redireciona o fluxo para o proxy SBC em Amsterdã e para a rede PSTN local conectada.

Diagrama 6.  Fluxo de tráfego com o modo "Always Bypass" e o usuário não está no site "home", mas na rede interna

![Um diagrama mostra o fluxo de tráfego Otimização de Mídia Local.](media/direct-routing-media-op-6.png "Fluxo de tráfego com o modo 'Always Bypass' e o usuário não está no site 'home', mas na rede interna")

### <a name="mode-2-only-for-local-users"></a>Modo 2: somente para usuários locais

Se houver conexões incorretas entre filiais locais, mas boas conexões entre cada filial local e escritório regional, o modo recomendado será "Somente para usuários locais".

Por exemplo, na região da APAC, suponha que a Contoso tenha vários escritórios em diferentes países. Para muitos países, a mudança para SIP não é possível porque a empresa ainda tem troncos TDM em muitas filiais locais. A centralização dos troncos TDM não é uma opção na região do APAC. Além disso, há mais de 50 filiais da Contoso em toda a região da APAC com centenas de gateways (SBCs).

Para criar uma solução em que os serviços PSTN são fornecidos em todas as filiais locais na região do APAC, onde a centralização dos troncos TDM não é uma opção, o administrador da Contoso emparelha um SBC regional em Cingapura como o proxy SBC para o serviço de Roteamento Direto. A conexão direta entre as filiais locais não é boa, mas há uma boa conexão entre cada filial local e o SBC regional em Cingapura. Para o SBC regional, o administrador escolhe o modo "Always Bypass" e, para os SBCs downstream locais, o administrador escolhe o modo "Somente para usuários locais".

O seguinte descreve dois cenários:

- Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online

- Cenário 2. O usuário e os gateways estão em sites diferentes

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Cenário 1. O usuário está no mesmo local que o SBC definido na Política de Roteamento de Voz Online

Suponha que o SBC em Cingapura esteja configurado como um SBC proxy para os SBCs downstream locais no Vietnã e na Indonésia. O usuário está no Vietnã no mesmo local que o SBC local. As políticas de roteamento de voz online especificam que as chamadas no Vietnã (com código de área +84) devem ser roteadas para o SBC local no Vietnã. Todas as outras chamadas - e, se o SBC no Vietnã falhar, chamadas no Vietnã - devem ser roteadas para o proxy SBC em Cingapura. A tabela a seguir resume a configuração de exemplo.

Tabela 5. Configuração de exemplo para o modo "Somente para usuários locais" Cenário 1

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia |
|:------------|:-------|:-------|:-------|:-------|
| Vietnã | +84 4 3926 3000 | Prioridade 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br>Prioridade 2: .* – proxysbc.contoso.com | VNsbc.contoso.com – somente para usuários locais <br> proxysbc.contoso.com – Always Bypass | <-> VNsbc.contoso.com de Usuário do Teams |

No diagrama a seguir, um usuário atribuído à filial local no Vietnã, enquanto estiver no local, faz uma chamada telefônica de Roteamento Direto por meio do Teams.

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST.

- A mídia gerada durante a chamada flui para o endereço IP interno do SBC local.

- O SBC local redireciona o fluxo para o proxy SBC em Cingapura e para a rede PSTN local conectada.

- O SBC de proxy é visível para o Sistema de Telefone apenas por meio do endereço IP externo e roteia o fluxo do SBC downstream (nesse caso, o SBC local no Vietnã) para o Sistema de Telefone.

- O SBC downstream na filial local não está visível diretamente para o Sistema de Telefone, mas é mapeado dentro da topologia de rede virtual.

Diagrama 7. Fluxo de tráfego com o modo "Somente para usuários locais" e o usuário está no site "home"

![Outro diagrama mostrando o fluxo de tráfego Otimização de Mídia Local.](media/direct-routing-media-op-7.png "Fluxo de tráfego com o modo &quot;Somente para usuários locais&quot; e o usuário está no site 'home'")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Cenário 2. O usuário e os gateways estão em sites diferentes

Suponha que o SBC em Cingapura esteja configurado como um SBC proxy para os SBCs downstream locais no Vietnã e na Indonésia. O usuário interno na Indonésia, localizado na filial local, está fazendo uma chamada de Roteamento Direto para o Vietnã. As políticas de roteamento de voz online especificam que as chamadas para o Vietnã (com código de área +84) devem ser roteadas para o SBC local no Vietnã. Todas as outras chamadas - e, caso o SBC no Vietnã falhe, chamadas para o Vietnã - devem ser roteadas para o proxy SBC em Cingapura. O SBC de proxy em Cingapura está definido como modo 'Always Bypass', e o SBC local no Vietnã está definido como modo "Somente para usuários locais". A tabela a seguir resume a configuração de exemplo.

Tabela 6. Configuração do usuário

| Localização física do usuário | O usuário faz uma chamada para um número | Política de Roteamento de Voz Online | Modo configurado para SBC | Fluxo de Mídia |
|:------------|:-------|:-------|:-------|:-------|
| Indonésia | +84 4 3926 3000 | Prioridade 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Prioridade 2: .* – proxysbc.contoso.com |VNsbc.contoso.com – somente para usuários locais <br> proxysbc.contoso.com – Always Bypass | < de Usuário do Teams–> proxysbc.contoso.com <-> VNsbc.contoso.com |


No diagrama a seguir, o usuário interno, enquanto estiver no local na filial indonésia, faz uma chamada telefônica de Roteamento Direto por meio do Teams para um número no Vietnã.

- O cliente do Teams do usuário se comunica diretamente com o Sistema telefônico por meio da API REST.

- A mídia gerada durante a chamada flui primeiro para o endereço IP interno do SBC de proxy.

- O proxy SBC em Cingapura redireciona o fluxo para o endereço IP interno do SBC downstream no Vietnã e para o Sistema telefônico.

- O SBC downstream no Vietnã roteia o fluxo para a rede PSTN local conectada.

- O SBC de proxy fica visível para o Sistema de Telefone somente por meio do endereço IP externo.

- Os SBCs downstream nas filiais locais não são visíveis diretamente para o Sistema de Telefone, mas são mapeados na topologia de rede virtual.

Diagrama 8.  Fluxo de tráfego com o modo "Somente para usuários locais" e o usuário não está no site "home", mas na rede interna

![Outro diagrama mostra o fluxo de tráfego Otimização de Mídia Local.](media/direct-routing-media-op-8.png "Fluxo de tráfego com o modo &quot;Somente para usuários locais&quot;, o usuário não está no site 'home', mas na rede interna")

## <a name="known-issues"></a>Problemas conhecidos

A seguir está uma lista de problemas conhecidos que estão atualmente presentes na Otimização de Mídia Local. A Microsoft está trabalhando para resolver esses problemas.

| Problema | Solução alternativa |
| :--- | :--- |
| O cliente do Teams não é identificado como **interno** quando o IP público do cliente do Teams corresponde à lista de IP confiável do cliente. | A otimização de mídia local exige que a sub-rede cliente do Teams corresponda a uma [sub-rede de rede](/powershell/module/skype/new-cstenantnetworksubnet) configurada pelo locatário|
| Escalonamentos de chamadas resultam em chamadas descartadas quando o cliente do Teams é identificado como interno.| Desabilite a Otimização de Mídia Local no SBC de Roteamento Direto.|
| Escalonamentos de chamadas de 1 para 1 chamada entre clientes internos para chamada multiparty com cliente/recurso externo resultam em chamadas descartadas | Trabalhe em andamento em uma correção. Como alternativa, desabilite a Otimização de Mídia Local no SBC de Roteamento Direto.|
| O usuário do Teams coloca a chamada Em Espera. A música é reproduzida no final do PSTN e a Otimização de Mídia Local está funcionando. O usuário do Teams retoma a chamada. A chamada para PSTN é retomada, mas a Otimização de Mídia Local não está funcionando e a chamada continua por meio do SBC central (Proxy) | Quando um usuário estaciona uma chamada para iniciar música em espera (MoH), ela está sendo escalonada de 1:1 para uma chamada multiparty pelo Controlador de Chamada para invocar o Controlador de Mídia e o Processador de Mídia (servindo como misturador AVMCU) por meio do qual o MoH atinge um usuário que foi colocado em espera. A desescalada para uma chamada 1:1 após a retomada da chamada nunca acontece conforme o design. Desabilite a Otimização de Mídia Local no SBC de Roteamento Direto.|
|Enquanto uma chamada está sendo estabelecida por alguns segundos, o usuário pode ouvir silêncio.| Devido à complexidade da arquitetura de otimização de mídia local, isso pode ocorrer em alguns casos.|
|Aplicativos de voz (por exemplo, Atendimento Automático, Fila de Chamadas) não funcionam.| A Otimização de Mídia Local não dá suporte a Aplicativos de Voz porque eles residem na nuvem e exigem conectividade externa. Para Location-Based cenários de roteamento, consulte [Aplicativos de voz (Assistente Automático ou Fila de Chamadas)](location-based-routing-plan.md#inbound-calls-through-voice-apps-auto-attendant-or-call-queue).|
