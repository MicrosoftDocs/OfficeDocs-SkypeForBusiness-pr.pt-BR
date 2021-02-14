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
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como configurar os Planos de Chamada da Microsoft e o recurso roteamento direto do sistema de telefonia dinâmico de chamadas de emergência.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06153eccd343ef8731af38ff4e3b45cea334fcb2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031007"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planejar e configurar chamadas de emergência dinâmicas 

Chamadas de emergência dinâmicas para Planos de Chamada da Microsoft e Roteamento Direto do Sistema de Telefonia oferece a capacidade de configurar e encaminhar chamadas de emergência e notificar o pessoal de segurança com base na localização atual do cliente teams.  

Com base na topologia de rede definida pelo administrador de locatários, o cliente do Teams fornece informações de conectividade de rede em uma solicitação para o LIS (Serviço de Informações de Localização). Se houver uma combinação, o LIS retornará um local para o cliente. Esses dados de localização são transmitidos de volta para o cliente.  

O cliente do Teams inclui dados de localização como parte de uma chamada de emergência. Esses dados são usados pelo provedor de serviços de emergência para determinar o PSAP (Ponto de Atendimento de Segurança Pública) apropriado e encaminhar a chamada para esse PSAP, que permite que o expedidor PSAP obtenha a localização do chamador.  

Para chamada de emergência dinâmica, o seguinte deve ocorrer:

1. O administrador de rede configura as configurações de rede e o LIS para criar um mapa de localização de rede/emergência.

   Para o Roteamento Direto, é necessária configuração adicional para roteamento de chamadas de emergência e possivelmente para a conectividade do parceiro. O administrador deve configurar a conexão com um provedor de serviços de roteamento de emergência (ERS) (Estados Unidos) **OU** configurar o Controlador de Borda de Sessão (SBC) para um aplicativo ELIN (Número de Identificação de Localização de Emergência).

2. Durante a inicialização e periodicamente posteriormente ou quando uma conexão de rede é alterada, o cliente do Teams envia uma solicitação de localização que contém suas informações de conectividade de rede para as configurações de rede e o LIS.

   - Se houver uma combinação de site de configurações de rede, as políticas de chamada de emergência serão retornadas para o cliente do Teams desse site. (Para obter mais informações sobre políticas, consulte [Configurar políticas de emergência).](#configure-emergency-policies)

   - Se houver uma combinação de LIS, um local de emergência do elemento de rede ao que o cliente do Teams está conectado será devolvido ao cliente do Teams. A combinação é executada na seguinte ordem, com o primeiro resultado matched sendo retornado:
       - Wap
       - Opção/porta Ethernet
       - Opção Ethernet
       - Sub-rede

3. Quando o cliente do Teams faz uma chamada de emergência, o local de emergência é transmitido para a rede PSTN.

   Para Roteamento Direto, o administrador deve configurar o SBC para enviar chamadas de emergência para o provedor de ERS ou configurar o aplicativo ELIN SBC.

Este artigo contém as seções a seguir.

- [Configurar endereços de emergência](#assign-emergency-addresses)
- [Definir configurações de rede](#configure-network-settings)
- [Configurar o Serviço de Informações de Localização](#configure-location-information-service)
- [Configurar políticas de emergência](#configure-emergency-policies)
- [Habilitar usuários e sites](#enable-users-and-sites)
- [Testar chamada de emergência](#test-emergency-calling)

A capacidade de fazer o roteamento automático para o PSAP (Ponto de Resposta de Segurança Pública) apropriado varia dependendo do país de uso do usuário do Teams.

Para obter mais informações sobre chamadas de emergência, incluindo informações sobre endereços de emergência e roteamento de chamadas de emergência, informações específicas para países e informações sobre configurações de rede e topologia de rede, consulte o seguinte:

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)

## <a name="supported-clients"></a>Clientes com suporte

Os clientes a seguir têm suporte no momento.  Verifique com frequência para ver as atualizações desta lista.

- Cliente de área de trabalho do Teams para Microsoft Windows
- Cliente de área de trabalho do Teams para Apple macOS
- Cliente móvel do Teams para o cliente Apple iOS versão 1.0.92.2019121004 e App Store versão 1.0.92 e superior
- Cliente móvel do Teams para cliente Android e Google Play Store versão 1416/1.0.0.2019121201 e superior
- Versão 1449/1.0.94.2019110802 e superior do Teams
- Salas do Teams versão 4.4.25.0 e superior

> [!NOTE]
> Não há suporte para chamada de emergência dinâmica, incluindo notificação de segurança no cliente Web do Teams. Para impedir que os usuários usem o cliente Web do Teams para ligar para números PSTN, você pode definir uma política de chamada do Teams e desativar a configuração Permitir chamada **PSTN** Web. Para saber mais, confira [as políticas de Chamadas no Teams](teams-calling-policy.md) e [set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

## <a name="assign-emergency-addresses"></a>Atribuir endereços de emergência

Você pode atribuir endereços de emergência a usuários do Plano de Chamada e aos identificadores de rede necessários para obter dinamicamente um local. (Há suporte para sub-rede e WIFi AP. A opção/porta Ethernet tem suporte no Windows 8.1 e posterior no momento).

Para dar suporte ao roteamento automatizado de chamadas de emergência nos Estados Unidos, você deve garantir que os locais de emergência atribuídos aos identificadores de rede incluam os códigos geodados associados. (Endereços de emergência sem códigos geo não podem ser atribuídos aos identificadores de rede necessários para locais dinâmicos.)

O Azure Maps é usado para serviços baseados em localização.  Quando você insere um endereço de emergência usando o Centro de administração do Microsoft Teams, o Teams verifica o endereço do Mapas do Azure:

- Se uma combinação for encontrada, os códigos geográficas serão incluídos automaticamente.

- Se uma combinação não for encontrada, você terá a oportunidade de criar manualmente um endereço de emergência. Você pode usar o recurso de soltar PIN para fazer isso. 

Isso significa que, se um local de emergência existente criado para a atribuição de usuários do Plano de Chamada for destinado a um local dinâmico, o mesmo endereço precisará ser re-criado para incluir os códigos geo. Para distinguir entre os dois locais, você deve incluir uma descrição diferente. O novo local de emergência pode ser atribuído aos usuários que têm o local antigo. Quando totalmente migrado, o local antigo pode ser excluído.

Adicione e atribua endereços de emergência no Centro de administração do Microsoft Teams ou usando o PowerShell. Para obter mais informações, [consulte Adicionar um local de emergência para](add-change-remove-emergency-location-organization.md) sua organização e atribuir um local de emergência para um [usuário.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Definir configurações de rede

As configurações de rede são usadas para determinar a localização de um cliente do Teams e para obter dinamicamente políticas de chamada de emergência e um local de emergência. Você pode definir as configurações de rede de acordo com como sua organização deseja que as chamada de emergência funcionem.

As configurações de rede incluem sites que incluem um conjunto de sub-redes e que são usados exclusivamente para atribuição de política dinâmica aos usuários. Por exemplo, uma política de chamada de emergência e uma política de roteamento de chamadas de emergência podem ser atribuídas ao "site Redmond" para que qualquer usuário que vá de casa ou outro local da Microsoft seja configurado com números de emergência, roteamento e suporte de segurança específicos para Redmond.  

>[!Note]
>As sub-redes também podem ser definidas no LIS e podem ser associadas a um local de emergência.  

Lembre-se das definições a seguir. Para obter mais informações, consulte [Configurações de rede para recursos de voz na nuvem.](cloud-voice-network-settings.md)

- Os endereços IP confiáveis contêm um conjunto de endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Uma tentativa de obter uma política ou local dinâmico só será feita se o endereço IP externo do usuário coincide com um endereço IP no endereço IP confiável. Uma combinação pode ser feita em relação a endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede.  (Se um endereço IP público tiver IPv4 e IPv6, você precisará adicionar ambos como endereços IP confiáveis.)

- Uma região de rede contém uma coleção de locais de rede. 

- Um site de rede representa um local onde sua organização tem um valor físico, como um escritório, um conjunto de edifícios ou um campus. Esses sites são definidos como um conjunto de sub-redes IP.

- Uma sub-rede de rede deve estar associada a um site de rede específico. A localização de um cliente é determinada com base na sub-rede de rede e no site de rede associado.  

Configure as configurações de rede no Centro de administração do Microsoft Teams ou usando o PowerShell. Para saber mais, confira [Gerenciar sua topologia de rede para recursos de voz na nuvem.](manage-your-network-topology.md)

Observe que pode levar algum tempo (até algumas horas) para que algumas alterações nas configurações de rede (como um novo endereço, identificador de rede e assim por diante) se propaguem e estarão disponíveis para clientes do Teams.  

**Para usuários do Plano de Chamada:**

- Se a configuração dinâmica da notificação de segurança for necessária, configure os endereços IP confiáveis e os sites de rede.

- Se apenas locais dinâmicos são necessários, você deve configurar apenas endereços IP confiáveis.

- Se nenhuma delas for necessária, a configuração de configurações de rede não será necessária. 

**Para usuários de Roteamento Direto:**

- Se a habilitação dinâmica de chamada de emergência ou configuração dinâmica de notificação de segurança for necessária, você deverá configurar os endereços IP confiáveis e os sites de rede.

- Se apenas locais dinâmicos são necessários, você deve configurar apenas endereços IP confiáveis.

- Se nenhuma delas for necessária, a configuração de configurações de rede não será necessária.


## <a name="configure-location-information-service"></a>Configurar o Serviço de Informações de Localização

Um cliente do Teams obtém endereços de emergência dos locais associados a diferentes identificadores de rede. Há suporte para as sub-redes e os WAPs (pontos de acesso sem fio). A opção/porta Ethernet tem suporte no Windows 8.1 e posterior neste momento.

Para que um cliente obtenha um local, você deve preencher o LIS com identificadores de rede (sub-redes, WAPs, opções, portas) e locais de emergência. Você pode fazer isso no Centro de administração do Microsoft Teams ou usando o PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, vá para **Locais**  >  **redes & locais.**
2. Clique na guia que representa o identificador de rede que você deseja adicionar. Por exemplo, clique em **Sub-redes,** pontos **de acesso Wi-Fi,** **Opções** ou **Portas.** Em seguida, **clique em Adicionar.**
3. Preencha os campos, adicione um local de emergência e clique em **Aplicar.**

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use os cmdlets a seguir para adicionar portas, opções, sub-redes e WAPs ao LIS.

- [Obter,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps) [Definir,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps) [Remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnline FazerSubnet
- [Obter,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps) [Definir,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps) [Remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineMobilPort
- [Obter,](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps) [Definir,](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps) [Remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineWirelessAccessPoint
- [Obter,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps) [Definir,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps) [Remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLhoSwear

>[!Important]
>Se as sub-redes estão sendo usadas como parte de sites de rede, elas devem ser redefinidas no Serviço de Informações de Localização para renderizar locais dinâmicos.

## <a name="configure-emergency-policies"></a>Configurar políticas de emergência

Use as seguintes políticas para configurar as chamada de emergência. Você pode gerenciar essas políticas no Centro de administração do Microsoft Teams ou usando o PowerShell.

- **Política de roteamento de chamadas** de emergência – aplica-se somente ao Roteamento Direto. Esta política configura os números de emergência, as máscaras por número, se desejar, e a rota PSTN por número.  Você pode atribuir essa política aos usuários, a sites de rede ou a ambos. (Os clientes do Teams de planos de chamada são habilitados automaticamente para chamada de emergência com os números de emergência do país com base no local de uso do Microsoft 365 ou do Office 365.)  Para saber mais, consulte [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto.](manage-emergency-call-routing-policies.md)

- **Política de chamada de emergência** – aplica-se aos Planos de Chamada e Ao Roteamento Direto. Essa política configura a experiência de notificação do security desk quando uma chamada de emergência é feita. Você pode definir quem notificar e como eles serão notificados. Por exemplo, para notificar automaticamente o sistema de segurança da sua organização e fazer com que eles ouçam chamadas de emergência.  Essa política pode ser atribuída a usuários ou sites de rede ou a ambos. Para saber mais, consulte [Gerenciar políticas de chamada de emergência no Teams.](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>Habilitar usuários e sites

Você pode atribuir políticas de roteamento de chamadas de emergência e políticas de chamadas de emergência aos usuários e aos sites. Lembre-se de que as políticas de roteamento de chamadas de emergência se aplicam somente ao Roteamento Direto. (Embora seja possível atribuir essa política a um usuário do Plano de Chamada, a política não terá efeito.)

Você atribui políticas no Centro de administração do Microsoft Teams ou usando o PowerShell. Para saber mais, veja:

- [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto](manage-emergency-call-routing-policies.md)
- [Gerenciar políticas de chamada de emergência no Teams](manage-emergency-calling-policies.md)

Aqui estão alguns exemplos do PowerShell.

Para habilitar um usuário específico para notificação de segurança, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para atribuir uma política chamada "Política de Chamada de Emergência 1" da Contoso ao Site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar um usuário específico de Roteamento Direto para chamadas de emergência, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para atribuir uma política chamada "Roteamento de Chamadas de Emergência da Contoso New York" ao Site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se você atribuiu uma política de chamada de emergência a um site de rede e a um usuário e, se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="test-emergency-calling"></a>Testar chamada de emergência

Alguns ERSPs (Provedores de Serviços de Roteamento de Emergência) nos Estados Unidos oferecem um bot de teste de chamada de emergência.

- **Os usuários do Plano** de Chamada nos Estados Unidos podem usar o número de emergência de teste predefinido 933 para validar a configuração de chamada de emergência. Esse número é roteado para um bot, que, em seguida, ecoa o número de telefone do chamador (ID da linha de chamada), o endereço ou o local de emergência e se a chamada seria automaticamente roteada para o PSAP ou exibido primeiro.

- **Os clientes de Roteamento Direto nos Estados Unidos** devem coordenar com seu ERSP para um serviço de teste.

 ## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência ](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para o usuário](assign-change-emergency-location-user.md)
- [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)
