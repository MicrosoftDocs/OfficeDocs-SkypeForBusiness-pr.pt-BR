---
title: Configurar chamadas de emergência dinâmicas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como configurar os planos de chamada e o recurso de chamadas de emergência dinâmicos de roteamento direto do sistema telefônico.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b76f8605aa1151911c26e0724db161b3a497fcf6
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164550"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planejar e configurar chamadas de emergência dinâmicas 

Chamadas de emergência dinâmicas para planos de chamadas e roteamento direto do sistema telefônico fornecem a funcionalidade de configurar e direcionar chamadas de emergência e notificar o pessoal de segurança com base na localização atual do cliente da equipe.  

Com base na topologia de rede que o administrador do locatário define, o cliente do teams fornece informações de conectividade de rede em uma solicitação para o serviço de informações de localização (LIS).  Se houver uma correspondência, o LIS retornará um local para o cliente. Esses dados de localização são transmitidos de volta para o cliente.  

O cliente do teams inclui dados de localização como parte de uma chamada de emergência. Esses dados são usados pelo provedor de serviços de emergência para determinar o ponto de resposta de segurança pública apropriado (PSAP) e para direcionar a chamada para esse PSAP, que permite que o PSAP Dispatcher obtenha a localização do chamador.  

Para fazer chamadas de emergência dinâmicas, o seguinte deve ocorrer:

1. O administrador de rede define as configurações de rede e o LIS para criar um mapa de local de emergência/rede.

   Para roteamento direto, a configuração adicional é necessária para roteamento de chamadas de emergência e possivelmente para conectividade de parceiro. O administrador deve configurar a conexão para um provedor de serviços de roteamento de emergência (ERS) **ou** configurar o controlador de borda de sessão (SBC) para um aplicativo de número de identificação de localização (Elin) de emergência.

2. Durante a inicialização e depois, periodicamente, ou quando uma conexão de rede é alterada, o cliente das equipes envia uma solicitação de localização que contém suas informações de conectividade de rede para as configurações de rede e o LIS.

   - Se houver uma correspondência de site de configurações de rede – as políticas de chamadas de emergência serão retornadas ao cliente do teams desse site. (Para obter mais informações sobre políticas, consulte [Configurar políticas de emergência](#configure-emergency-policies)).

   - Se houver uma combinação de LIS – um local de emergência do elemento de rede ao qual o cliente do teams está conectado será retornado ao cliente do teams.

3. Quando o cliente do teams faz uma chamada de emergência, o local de emergência é transmitido para a rede PSTN.

   Para roteamento direto, o administrador deve configurar o SBC para enviar chamadas de emergência para o provedor de ERS ou configurar o aplicativo SBC ELIN.

Este artigo contém as seções a seguir.

- [Configurar endereços de emergência](#assign-emergency-addresses)
- [Definir configurações de rede](#configure-network-settings)
- [Configurar o serviço de informações de localização](#configure-location-information-service)
- [Configurar políticas de emergência](#configure-emergency-policies)
- [Habilitar usuários e sites](#enable-users-and-sites)
- [Testar chamadas de emergência](#test-emergency-calling)


A capacidade de fazer o roteamento automático para o ponto de resposta de segurança pública apropriado (PSAP) varia de acordo com o país de uso do usuário do teams. 

Para obter mais informações sobre chamadas de emergência, incluindo informações sobre endereços de emergência e roteamento de chamadas de emergência, informações específicas para países e informações sobre configurações de rede e topologia de rede, consulte o seguinte:

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)


## <a name="supported-clients"></a>Clientes com suporte

Os clientes a seguir têm suporte no momento.  Verifique com frequência para ver as atualizações desta lista.

- Cliente de área de trabalho do teams para Microsoft Windows
- Cliente de área de trabalho do teams para Apple macOS
- Cliente móvel do teams para Apple iOS Client versão 1.0.92.2019121004 e App Store versão 1.0.92 e posterior
- Cliente do teams Mobile para cliente Android e Google Play Store versão 1416/1.0.0.2019121201 e posterior
- Teams Phone versão 1449/1.0.94.2019110802 e maior

## <a name="assign-emergency-addresses"></a>Atribuir endereços de emergência

Você pode atribuir endereços de emergência a usuários do plano de chamada e aos identificadores de rede necessários para obter um local dinamicamente. (A sub-rede e o AP WiFi têm suporte; o suporte para switch/porta Ethernet está pendente).

Para dar suporte ao roteamento automatizado de chamadas de emergência nos Estados Unidos, você deve garantir que os locais de emergência atribuídos a identificadores de rede incluam os códigos geográficos associados. (Os endereços de emergência sem códigos geográficos não podem ser atribuídos aos identificadores de rede necessários para locais dinâmicos.)

O Azure Maps é usado para serviços baseados em localização.  Quando você insere um endereço de emergência usando o centro de administração do Microsoft Teams, o Teams verifica o Azure Maps para o endereço:

- Se for encontrada uma correspondência, os códigos geográficos serão incluídos automaticamente.

- Se não for encontrada uma correspondência, você terá a oportunidade de criar manualmente um endereço de emergência. Você pode usar o recurso soltar de PIN para fazer isso.   

Isso significa que, se um local de emergência existente criado para a atribuição a usuários do plano de chamada for destinado a um local dinâmico, o mesmo endereço precisa ser recriado para incluir os códigos geográficos. Para distinguir entre os dois locais, você deve incluir uma descrição diferente. O novo local de emergência pode ser atribuído aos usuários que têm o local antigo. Quando migrado completamente, o local antigo pode ser excluído.

Para obter mais informações sobre como configurar endereços de emergência, consulte [Adicionar um local de emergência para sua organização](add-change-remove-emergency-location-organization.md) e [atribuir um local de emergência para o usuário](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Definir configurações de rede

As configurações de rede são usadas para determinar a localização de um cliente do Teams e para obter dinamicamente as políticas de chamadas de emergência e um local de emergência. Você pode definir as configurações de rede de acordo com a forma como a sua organização quer que a chamada de emergência funcione.

As configurações de rede incluem sites que incluem uma coleção de sub-redes--elas são usadas exclusivamente para atribuição de política dinâmica a usuários.  Por exemplo, uma política TeamsEmergencyCalling e uma política TeamsEmergencyCallRouting podem ser atribuídas ao "site Redmond" para que todos os usuários que estiverem em roaming ou em outro local da Microsoft sejam configurados com números de emergência, roteamento e pessoal de segurança específicos para Redmond.  

>[!Note]
>As sub-redes também podem ser definidas no LIS e podem ser associadas a um local de emergência.  

Tenha em mente as seguintes definições:

- Os IPs confiáveis contêm uma coleção dos IPs externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Uma tentativa de obter uma política dinâmica ou local será feita apenas se o IP externo do usuário corresponder a um IP no endereço IP confiável. Uma coincidência pode ser feita em endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede.  (Se um endereço IP público tiver IPv4 e IPv6, você precisará adicionar ambos como endereços IP confiáveis.)

- Uma região de rede contém uma coleção de locais de rede. 

- Um site de rede representa um local onde a sua organização tem um valor físico, como um escritório, um conjunto de edifícios ou um campus. Esses sites são definidos como uma coleção de sub-redes IP.

- Uma sub-rede de rede deve estar associada a um site de rede específico. A localização de um cliente é determinada com base na sub-rede da rede e no site de rede associado.  

Para obter mais informações, consulte [configurações de rede para recursos de voz em nuvem](cloud-voice-network-settings.md) e [gerenciar a topologia de rede para recursos de voz na nuvem](manage-your-network-topology.md).

Observe que pode demorar algum tempo (até algumas horas) para algumas alterações nas configurações de rede (como um novo endereço, identificador de rede e assim por diante) para propagar e estar disponível para clientes do teams.  

**Para usuários do plano de chamada:**

- Se a configuração dinâmica da notificação de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.

- Se forem necessários apenas locais dinâmicos, você deverá configurar apenas endereços IP confiáveis. 

- Se nenhuma delas for necessária, a configuração das configurações de rede não será necessária. 

**Para usuários de roteamento direto:**

- Se a habilitação dinâmica de configuração de emergência ou a configuração dinâmica da notificação de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.

- Se forem necessários apenas locais dinâmicos, você deverá configurar apenas endereços IP confiáveis.

- Se nenhuma delas for necessária, a configuração das configurações de rede não será necessária.


## <a name="configure-location-information-service"></a>Configurar o serviço de informações de localização

Um cliente do teams Obtém endereços de emergência dos locais associados a diferentes identificadores de rede. As duas sub-redes e pontos de acesso sem fio (WAPs) são compatíveis. Se vários locais forem encontrados, o WAP terá precedência sobre a sub-rede. (O suporte para switch/porta Ethernet está pendente.)

Para que um cliente obtenha um local, você deve preencher o LIS (serviço de informações de localização) com identificadores de rede e locais de emergência usando os seguintes cmdlets:  


- [Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch
- [Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint 


>[!Important] 
>Se as sub-redes estiverem sendo usadas como parte dos sites de rede, elas deverão ser redefinidas no serviço de informações de localização para renderizar locais dinâmicos.


## <a name="configure-emergency-policies"></a>Configurar políticas de emergência

Use as políticas a seguir para configurar as chamadas de emergência:

- **TeamsEmergencyCallRoutingPolicy** – aplica-se somente ao roteamento direto. Essa política configura os números de emergência, máscaras por número, se desejado, e a rota PSTN por número.  Você pode atribuir essa política a usuários, a sites de rede ou a ambos. (Planos de chamada os clientes da equipe são habilitados automaticamente para fazer chamadas de emergência com os números de emergência do país com base no local de uso do Office 365.)  Você gerencia essa política usando os cmdlets New-, set-e Grant-CsTeamsEmergencyCallRouting. 

- **TeamsEmergencyCallingPolicy** -aplica-se ao plano de chamada e ao encaminhamento direto. Essa política configura a experiência de notificação de segurança técnica quando uma chamada de emergência é feita. Você pode definir quem deseja notificar e como eles são notificados. Por exemplo, para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.  Essa política pode ser atribuída a usuários ou sites de rede ou ambos. Você gerencia essa política usando os cmdlets New-, set-e Grant-CsTeamsEmergencyCallingPolicy. 

Para obter mais informações, consulte [gerenciar políticas de chamadas de emergência no Teams](manage-emergency-calling-policies.md) e [gerenciar políticas de roteamento de chamadas de emergência para roteamento direto](manage-emergency-call-routing-policies.md).


## <a name="enable-users-and-sites"></a>Habilitar usuários e sites

Você pode atribuir políticas **TeamsEmergencyCalling** e **TeamsEmergencyCallROuting** para usuários e para sites.  

A política TeamsEmergencyCallRouting se aplica apenas ao roteamento direto. (Embora seja possível atribuir essa política a um usuário de plano de chamada, a política não terá efeito.)

Por exemplo, para habilitar um usuário específico para a notificação do Security Desk, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para atribuir uma política chamada "política de chamadas de emergência da Contoso 1" ao site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar um usuário de roteamento direto específico para fazer chamadas de emergência, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para atribuir uma política chamada "roteamento de chamada de emergência do contoso New York" ao site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se você atribuiu uma política de chamadas de emergência a um site de rede e a um usuário, e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.


## <a name="test-emergency-calling"></a>Testar chamadas de emergência

Alguns provedores de serviços de roteamento de emergência (ERSPs) nos Estados Unidos oferecem um bot de teste de chamada de emergência.

- **Plano de chamada os usuários nos Estados Unidos** podem usar o número de emergência de teste predefinido 933 para validar a configuração de chamadas de emergência. Esse número é roteado para um bot, que então ecoa novamente o número de telefone do chamador (ID da linha de chamada), o endereço de emergência ou o local e se a chamada seria automaticamente roteada para o PSAP ou em uma tela em primeiro lugar.

- **Os clientes de roteamento direto nos Estados Unidos** devem coordenar com o ERSP para um serviço de teste.

 ## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para o usuário](assign-change-emergency-location-user.md)
- [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)
