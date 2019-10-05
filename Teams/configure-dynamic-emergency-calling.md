---
title: Configurar chamadas de emergência dinâmicas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurar chamadas de emergência dinâmicas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 006f131183fe75b8246f0d2fa2d0ae28575e9e1d
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396452"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>Planejar e configurar chamadas de emergência dinâmicas para planos de chamada
Chamadas de emergência dinâmicas para planos de chamada da Microsoft fornecem a funcionalidade de configurar e rotear chamadas de emergência com base na localização atual do cliente da equipe.  A capacidade de direcionar o roteamento automático para o ponto de resposta de segurança pública adequado (PSAP) ou notificar a equipe de suporte técnico varia de acordo com o país de uso do usuário do teams.  

> [!Note] 
> Atualmente, o recurso de chamadas de emergência dinâmicos está disponível somente nos Estados Unidos. No entanto, a notificação de segurança técnica tem suporte entre os limites do país.

**Nos Estados Unidos**, você pode configurar o roteamento de chamada de emergência dinâmico da seguinte maneira:
  
- Se um cliente do teams estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão roteadas automaticamente para o PSAP que está servindo essa localização geográfica.  

- Se um cliente do Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão filtradas por um centro de chamadas nacionais para determinar a localização do chamador antes de transferir a chamada para o PSAP que está servindo dessa localização geográfica.

Você pode configurar a notificação do Security Desk da seguinte maneira:

- Se um cliente do teams estiver localizado em um site de rede definido pelo locatário, os membros do grupo de segurança configurados para esse site serão notificados.

- Se um cliente do Teams não estiver localizado em um site de rede definido pelo locatário, os membros do grupo de segurança configurados para o usuário serão notificados.

**Fora dos Estados Unidos**, as chamadas de emergência são roteadas para o PSAP que está mapeado para o número de telefone atribuído ao usuário.  Em alguns países, como a Grã-Bretanha e o Canadá, as chamadas são as chamadas nacionais antes de transferir o chamador para o PSAP apropriado, enquanto outras roteiam diretamente para o PSAP, independentemente de onde o usuário está localizado no momento. 

Observe que você pode configurar a notificação do Dynamic Security Desk para todos os usuários do plano de chamadas.


## <a name="supported-clients"></a>Clientes com suporte

Os clientes a seguir têm suporte no momento.  Verifique com frequência para ver as atualizações desta lista.

- Cliente de área de trabalho do teams para Windows
- Cliente de área de trabalho do teams para Mac

## <a name="configure-dynamic-emergency-calling"></a>Configurar chamadas de emergência dinâmicas

Para configurar a chamada de emergência dinâmica, você precisa executar as seguintes tarefas:

- [Configurar endereços de emergência](#configure-emergency-addresses)
- [Definir configurações de rede](#configure-network-settings)
- [Configurar o serviço de informações de localização](#configure-location-information-service)
- [Configurar políticas de emergência](#configure-emergency-policies)
- [Habilitar usuários e sites](#enable-users-and-sites)
- [Testar chamadas de emergência](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>Configurar endereços de emergência

Para dar suporte ao roteamento automatizado nos Estados Unidos, você deve configurar completamente o endereço cívico que faz parte dos locais de emergência atribuídos a identificadores de rede--e incluir os códigos geográficos associados. (Endereços de emergência sem códigos geográficos não podem ser atribuídos aos identificadores de rede necessários para locais dinâmicos.)

- Se você inserir um endereço de emergência por meio do centro de administração do Microsoft Teams, os códigos geográficos serão automaticamente incluídos se uma correspondência for encontrada.

- Se uma coincidência não for encontrada automaticamente, você terá a oportunidade de criar um endereço de emergência manualmente.  

Isso significa que, se um endereço de emergência existente for configurado para fazer chamadas de emergência, o mesmo endereço precisa ser recriado para incluir os códigos geográficos.  Para distinguir entre os dois endereços, você deve incluir uma descrição diferente. O novo endereço de emergência pode ser atribuído aos usuários que têm o endereço antigo. Quando migrado completamente, o endereço antigo pode ser excluído. 

Para obter mais informações sobre como configurar endereços de emergência, consulte [o que são locais de emergência, locais e encaminhamento de chamadas?](what-are-emergency-locations-addresses-and-call-routing.md).

### <a name="configure-network-settings"></a>Definir configurações de rede

Você precisa definir as configurações de rede para obter dinamicamente um local de emergência usado para roteamento de chamadas de emergência e, opcionalmente, fornecer a configuração dinâmica de notificações de segurança de mesa. A experiência de chamadas de emergência desejada determinará quais configurações de rede precisam ser configuradas. 

Tenha em mente as seguintes definições:

- Os IPs confiáveis contêm uma coleção dos IPs externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Locais dinâmicos só serão habilitados se o IP externo do usuário corresponder a um IP na coleção de IPs confiáveis.  Uma coincidência pode ser feita em endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede.

- Uma região de rede contém uma coleção de locais de rede. 

- Um site de rede representa um local onde a sua organização tem um valor físico, como um escritório, um conjunto de edifícios ou um campus. Esses sites são definidos como uma coleção de sub-redes IP.

- Uma sub-rede de rede deve estar associada a um site de rede específico. A localização de um cliente é determinada com base na sub-rede da rede e no site de rede associado.  


Para usuários do plano de chamada:

- Se a configuração dinâmica da notificação de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.

- Se forem necessários apenas locais dinâmicos, você deverá configurar apenas endereços IP confiáveis. 

- Se nenhuma delas for necessária, a configuração das configurações de rede não será necessária. 

Para obter mais informações, consulte [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md), que descreve como definir as configurações de rede. (As informações neste artigo se aplicam aos planos de chamada e ao encaminhamento direto.)


### <a name="configure-location-information-service"></a>Configurar o serviço de informações de localização

Um cliente do teams Obtém endereços de emergência dos locais de emergência associados a diferentes identificadores de rede.  As sub-redes e pontos de acesso sem fio têm suporte. (O suporte para switch/porta Ethernet está pendente.)

Para configurar o LIS (serviço de informações de localização) com identificadores de rede e locais de emergência, use os seguintes cmdlets:

- Obter, definir, remover-CsOnlineLisPort
- Obter, definir, remover-CsOnlineLisSwitch
- Obter, definir, remover-CsOnlineLisSubnet
- Obter, definir, remover-CsOnlineLisWirelessAccessPoint 

> [!Important] 
> Se as sub-redes estiverem sendo usadas como parte dos sites de rede, elas deverão ser redefinidas no serviço de informações de localização para renderizar locais dinâmicos.


### <a name="configure-emergency-policies"></a>Configurar políticas de emergência

As políticas de emergência determinam o que acontece quando um usuário em sua organização faz uma chamada de emergência.  Você pode definir quem deseja notificar e como eles são notificados quando um usuário chama serviços de emergência. Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.

Para gerenciar as políticas de emergência, use os cmdlets de política New-, Set-CsTeamsEmergencyCalling.  Para obter mais informações, consulte [gerenciar políticas de chamadas de emergência no Microsoft Teams](manage-emergency-calling-policies.md).


### <a name="enable-users-and-sites"></a>Habilitar usuários e sites

Enquanto os usuários do plano de chamada são habilitados automaticamente para chamadas de emergência, você deve habilitar os usuários para a notificação de segurança, configurando a política de chamadas de emergência, conforme mostrado no exemplo a seguir:


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Você também pode atribuir a política de chamadas de emergência a um site de rede, conforme mostrado no exemplo a seguir, que atribui uma política chamada "política de chamadas de emergência da Contoso 1" ao site 1:

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Se você atribuiu uma política de chamadas de emergência a um site de rede e a um usuário, e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.


### <a name="test-emergency-calling"></a>Testar chamadas de emergência

Para testar as chamadas de emergência nos Estados Unidos, use o número de emergência de teste predefinido 933.  Esse número é roteado para um bot, que então ecoa novamente o número de telefone do chamador (ID da linha de chamada), o endereço de emergência ou o local e se a chamada é automaticamente roteada para o PSAP ou com a tela em primeiro lugar.  