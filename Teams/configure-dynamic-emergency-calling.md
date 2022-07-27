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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como configurar os Planos de Chamadas da Microsoft e o recurso de chamada de emergência dinâmica de Roteamento Direto do Sistema de Telefonia.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc7fb0ae87cda84dfbf7b164d38b709b7ef2eef9
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023692"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planejar e configurar chamadas de emergência dinâmicas 

Chamadas de emergência dinâmicas para Planos de Chamadas da Microsoft, Conexão de Operador e Roteamento Direto fornecem a capacidade de configurar e rotear chamadas de emergência e notificar a equipe de segurança com base na localização atual do cliente do Teams.  

Com base na topologia de rede (elementos de rede associados a endereços de emergência) que o administrador de locatários define, o cliente do Teams fornece informações de conectividade de rede em uma solicitação para o LIS (Serviço de Informações de Localização). Se houver uma correspondência, o LIS retornará um local para o cliente.

O cliente do Teams inclui dados de localização como parte de uma chamada de emergência. Esses dados são usados pelo provedor de serviços de emergência para determinar o PSAP (Ponto de Atendimento de Segurança Pública) apropriado e rotear a chamada para esse PSAP, o que permite que o dispatcher PSAP obtenha a localização do chamador.  

Para chamadas de emergência dinâmicas, o seguinte deve ocorrer:

1. O administrador de rede define as configurações de rede e o LIS para criar um mapa de local de rede/emergência.

2. Durante a inicialização e periodicamente posteriormente ou quando uma conexão de rede é alterada, o cliente do Teams envia uma solicitação de localização que contém suas informações de conectividade de rede para as configurações de rede e o LIS.

   - Se houver uma correspondência de site de configurações de rede– as políticas de chamada de emergência serão retornadas para o cliente do Teams desse site. (Para obter mais informações sobre políticas, consulte [Configurar políticas de emergência](#configure-emergency-policies)).

   - Se houver uma correspondência de LIS – um local de emergência do elemento de rede ao qual o cliente do Teams está conectado será retornado ao cliente do Teams. A correspondência é executada na seguinte ordem com o primeiro resultado correspondente sendo retornado:
       - WAP
       - Comutador/porta Ethernet
       - Comutador Ethernet
       - Sub-rede

3. Quando o cliente do Teams faz uma chamada de emergência, o local de emergência é transmitido para a rede PSTN.

A capacidade de fazer o roteamento automático para o PSAP (Ponto de Resposta de Segurança Pública) apropriado varia dependendo do país de uso do usuário do Teams.

Os Planos de Chamadas da Microsoft e os parceiros do Operator Connect incluem serviços de roteamento de emergência dinâmicos para usuários no Estados Unidos e no Canadá.

No entanto, para Roteamento Direto, a configuração adicional é necessária para rotear chamadas de emergência e, possivelmente, para a conectividade do parceiro. O administrador deve garantir que o gateway PSTN que roteia a chamada de emergência tenha sido configurado para adicionar informações de localização ao INVITE de saída (definindo o parâmetro PidfloSupported como True no objeto de gateway PSTN online. Além disso, o administrador deve configurar a conexão com um provedor de ERS (Serviço de Roteamento de Emergência) (Estados Unidos e Canadá) **OU** configurar o SBC (Controlador de Borda de Sessão) para um aplicativo ELIN (Número de Identificação de Local de Emergência). Para obter informações sobre provedores ERS, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).

Este artigo contém as seções a seguir.

- [Atribuir endereços de emergência](#assign-emergency-addresses)
- [Definir configurações de rede](#configure-network-settings)
- [Configurar o Serviço de Informações de Localização](#configure-location-information-service)
- [Configurar políticas de emergência](#configure-emergency-policies)
- [Habilitar usuários e sites](#enable-users-and-sites)
- [Testar chamada de emergência](#test-emergency-calling)

Para obter mais informações sobre chamadas de emergência, incluindo informações sobre endereços de emergência e roteamento de chamadas de emergência, informações específicas para países e informações sobre configurações de rede e topologia de rede, consulte o seguinte:

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)

Para obter mais informações sobre quais recursos estão disponíveis nas nuvens governamentais, consulte [Suporte](#government-support) governamental no final deste artigo.


## <a name="supported-clients"></a>Clientes com suporte

No momento, há suporte para os clientes a seguir.  Verifique novamente com frequência para ver as atualizações dessa lista.

- Cliente de área de trabalho do Teams para Microsoft Windows
- Cliente da área de trabalho do Teams para MacOS da Apple
- Cliente móvel do Teams para apple iOS versão 1.0.92.2019121004 e App Store versão 1.0.92 e superior
- Cliente móvel do Teams para cliente Android e Google Play Store versão 1416/1.0.0.2019121201 e superior
- Versão de telefone do Teams 1449/1.0.94.2019110802 e superior
- Salas do Teams versão 4.4.25.0 e superior

> [!NOTE]
> Os locais baseados em Sub-rede e Wi-Fi têm suporte em todos os clientes do Teams com suporte. <br><br>
> Há suporte para Ethernet/Switch (LLDP) em:
> - Windows versões 10.0 e posteriores neste momento.<br>
> - Mac OS, que requer software [de habilitação de LLDP](https://www.microsoft.com/download/details.aspx?id=103383).<br>
> - Telefone do Teams com o aplicativo Teams versão 1449/1.0.94.2021110101 e posterior.

> [!NOTE]
> Não há suporte para chamadas de emergência dinâmicas, incluindo notificação de suporte de segurança no cliente Web do Teams. Para impedir que os usuários usem o cliente Web do Teams para chamar números PSTN, você pode definir uma política de chamada do Teams e desativar a configuração Permitir chamada **PSTN** Web. Para saber mais, confira [Políticas de chamada no Teams](teams-calling-policy.md) e [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). 

> [!NOTE]
> Telefones 3PIP não dão suporte a chamadas de emergência dinâmicas. 



## <a name="assign-emergency-addresses"></a>Atribuir endereços de emergência

Você pode atribuir endereços de emergência da seguinte maneira:

- Para usuários do Plano de Chamadas.

- Para usuários do Operator Connect&mdash;, dependendo dos recursos atribuídos ao número quando a operadora os carrega no inventário de um cliente.

- Para os identificadores de rede necessários para obter dinamicamente um local. 

Para dar suporte ao roteamento automatizado de chamadas de emergência no Estados Unidos, você deve garantir que os locais de emergência atribuídos aos identificadores de rede incluam os códigos geográficos associados. (Endereços de emergência sem códigos geográficos não podem ser atribuídos aos identificadores de rede necessários para locais dinâmicos.)

Azure Mapas é usado para serviços baseados em localização. Quando você insere um endereço de emergência usando o centro de administração do Microsoft Teams, o Teams verifica Azure Mapas o endereço:

- Se uma correspondência for encontrada, os códigos geogeográficos serão incluídos automaticamente.

- Se uma correspondência não for encontrada, você terá a oportunidade de criar manualmente um endereço de emergência. Você pode usar o recurso de soltar PIN para fazer isso. 

> [!NOTE]
> Endereços de emergência com mais de dois anos não podem ser atribuídos a identificadores de rede. Você precisará criar novamente endereços mais antigos.

Você adiciona e atribui endereços de emergência no centro de administração do Microsoft Teams ou usando o PowerShell. Para obter mais informações, [consulte Adicionar um local de emergência para sua organização](add-change-remove-emergency-location-organization.md) e [atribuir um local de emergência para um usuário](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Definir configurações de rede

As configurações de rede são usadas para determinar a localização de um cliente do Teams e para obter dinamicamente políticas de chamada de emergência e um local de emergência. Você pode definir as configurações de rede de acordo com o modo como sua organização deseja que as chamadas de emergência funcionem.

As configurações de rede incluem sites que incluem uma coleção de sub-redes e são usadas exclusivamente para atribuição de política dinâmica aos usuários. Por exemplo, uma política de chamada de emergência e uma política de roteamento de chamadas de emergência podem ser atribuídas ao "site de Redmond" para que qualquer usuário que faz roaming de casa ou outro local da Microsoft seja configurado com números de emergência, roteamento e suporte de segurança específicos para Redmond.  

Os endereços IP confiáveis contêm uma coleção de endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Uma tentativa de obter uma política ou local dinâmico só será feita se o endereço IP externo do usuário corresponder a um endereço IP no endereço IP confiável.

Para obter mais informações sobre endereços IP, regiões de rede, sites e endereços de sub-rede, consulte [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).

Defina as configurações de rede no centro de administração do Microsoft Teams ou usando o PowerShell. Para saber mais, confira [Gerenciar sua topologia de rede para recursos de voz na nuvem](manage-your-network-topology.md).

Observe que pode levar algum tempo (até algumas horas) para algumas alterações nas configurações de rede (como um novo endereço, identificador de rede e assim por diante) para propagar e estar disponível para clientes do Teams.  

> [!Note]
> As sub-redes também podem ser definidas no LIS e podem ser associadas a um local de emergência.  As sub-redes LIS devem ser definidas pela ID de rede correspondente ao intervalo de IP da sub-rede atribuído aos clientes. Por exemplo, a ID de rede de um IP/máscara de cliente de 10.10.10.150/25 é 10.10.10.128. Para obter mais informações, consulte [Noções básicas de endereçamento TCP/IP e sub-rede](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

> [!Important]
> Não há suporte para pesquisas de configuração de rede com implantações de serviço de proxy de nuvem que modificam os endereços IP de origem de clientes do Teams.



**Para usuários do Plano de Chamada e do Operator Connect:**

- Se a configuração dinâmica da notificação do suporte de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.

- Se apenas locais dinâmicos forem necessários, você deverá configurar apenas endereços IP confiáveis; Não é necessário definir as configurações de rede.

- Se nenhum deles for necessário, a definição das configurações de rede não será necessária. 

**Para usuários de Roteamento Direto:**

- Se a habilitação dinâmica de chamadas de emergência ou configuração dinâmica da notificação de suporte de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.

- Se apenas locais dinâmicos forem necessários, você deverá configurar apenas endereços IP confiáveis; Não é necessário definir as configurações de rede.

- Se nenhum deles for necessário, a definição das configurações de rede não será necessária.


## <a name="configure-location-information-service"></a>Configurar o Serviço de Informações de Localização

Um cliente do Teams obtém endereços de emergência dos locais associados a diferentes identificadores de rede. 

Para que um cliente obtenha um local, você deve preencher o LIS com identificadores de rede (sub-redes, WAPs, comutadores, portas) e locais de emergência. Você pode fazer isso no centro de administração do Microsoft Teams ou usando o PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **Redes de** > **Locais & locais**.
2. Clique na guia que representa o identificador de rede que você deseja adicionar. Por exemplo, clique **em Sub-redes**, pontos **de acesso Wi-Fi**, **Comutadores** ou **Portas**. Em seguida, clique **em Adicionar**.
3. Preencha os campos, adicione um local de emergência e clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use os cmdlets a seguir para adicionar portas, comutadores, sub-redes e WAPs ao LIS.

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Se as sub-redes estiverem sendo usadas como parte dos sites de rede, elas deverão ser redefinidas no Serviço de Informações de Localização para renderizar locais dinâmicos.

## <a name="configure-emergency-policies"></a>Configurar políticas de emergência

Use as políticas a seguir para configurar chamadas de emergência. Você pode gerenciar essas políticas no centro de administração do Microsoft Teams ou usando o PowerShell.

- **Política de roteamento de chamadas de emergência – aplica-se somente ao Roteamento Direto**. Essa política configura os números de emergência, máscaras por número, se desejado, e a rota PSTN por número. Você pode atribuir essa política a usuários, a sites de rede ou a ambos. Para saber mais, confira [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto](manage-emergency-call-routing-policies.md).  

   (Os usuários do Plano de Chamada e do Operator Connect são habilitados automaticamente para chamadas de emergência com os números de emergência do país com base em seu microsoft 365 ou Office 365 local de uso.)

- **Política de chamada de emergência – aplica-se a Planos de Chamada, Conexão de Operador e Roteamento Direto.** Essa política configura a experiência de notificação do suporte de segurança quando uma chamada de emergência é feita. Você pode definir quem notificar e como eles são notificados. Por exemplo, para notificar automaticamente o suporte de segurança da sua organização e fazer com que eles ouçam em chamadas de emergência.  Essa política pode ser atribuída a usuários, sites de rede ou ambos. Para saber mais, confira [Gerenciar políticas de chamadas de emergência no Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Habilitar usuários e sites

Você pode atribuir políticas de roteamento de chamadas de emergência e políticas de chamada de emergência a usuários e sites. Tenha em mente que as políticas de roteamento de chamadas de emergência se aplicam somente ao Roteamento Direto. (Embora seja possível atribuir essa política a um plano de chamada ou usuário do Operator Connect, a política não terá efeito.)

Você atribui políticas no centro de administração do Microsoft Teams ou usando o PowerShell. Para saber mais, veja:

- [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto](manage-emergency-call-routing-policies.md)
- [Gerenciar políticas de chamadas de emergência no Teams](manage-emergency-calling-policies.md)

A seguir estão exemplos do PowerShell:

Para habilitar um usuário específico para notificação de suporte de segurança, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para atribuir uma política chamada "Política de Chamada de Emergência 1 da Contoso" ao Site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar um usuário de Roteamento Direto específico para chamadas de emergência, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para atribuir uma política chamada "Roteamento de Chamadas de Emergência da Contoso em Nova York" ao Site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se você atribuiu uma política de chamada de emergência a um site de rede e a um usuário e, se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="test-emergency-calling"></a>Testar chamada de emergência

Alguns provedores de serviços de roteamento de emergência (ERSPs) no Estados Unidos oferecem um bot de teste de chamada de emergência.

- **Os usuários do Plano de Chamada e do Operator Connect no Estados Unidos ou** no Canadá podem usar o número de emergência de teste predefinido 933 para validar sua configuração de chamada de emergência. Esse número é roteado para um bot, que retorna o número de telefone do chamador (ID da linha de chamada), o endereço de emergência ou o local e se a chamada seria roteada automaticamente para o PSAP ou exibida primeiro.

- **Os clientes de Roteamento Direto no Estados Unidos** devem coordenar com seu ERSP para um serviço de teste.

## <a name="government-support"></a>Suporte do governo

A tabela a seguir mostra suporte para chamadas de emergência dinâmicas nas nuvens governamentais:

| Nuvem | Disponibilidade |
| :------------|:-------|
| Multilocatário da World Wide | Disponível em todos os clientes do Teams |
| GCC | Disponível em todos os clientes do Teams |
| GCCH | -Disponível na área de trabalho do Teams <br> -Disponível em clientes móveis do Teams <br> -Disponível em telefones do Teams, versão do aplicativo: 1449/1.0.94.2022061702 |
| Dod | Pendente |

 ## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência ](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para o usuário](assign-change-emergency-location-user.md)
- [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)
