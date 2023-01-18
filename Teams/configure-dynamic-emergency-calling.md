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
- highpri
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como configurar o recurso de chamada dinâmica de roteamento dinâmico de planos e de roteamento direto do sistema de telefone.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1061adf81b8e9ae84ad028a5047636b6fee7a959
ms.sourcegitcommit: 052e4b3982b0b8ee7d4edc47da4d63b35518a757
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2023
ms.locfileid: "69814353"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planejar e configurar chamadas de emergência dinâmicas 

A chamada de emergência dinâmica para Planos de Chamada da Microsoft, Conexão de Operador, Teams Phone Mobile e Roteamento Direto fornece a capacidade de configurar e rotear chamadas de emergência e notificar a equipe de segurança com base na localização atual do cliente do Teams.  

Com base na topologia de rede (elementos de rede associados a endereços de emergência) que o administrador do locatário define, o cliente do Teams fornece informações de conectividade de rede em uma solicitação ao LIS (Serviço de Informações de Localização). Se houver uma correspondência, o LIS retornará um local para o cliente.

O cliente do Teams inclui dados de localização como parte de uma chamada de emergência. Esses dados são então usados pelo provedor de serviços de emergência para determinar o PSAP (Ponto de Resposta de Segurança Pública) apropriado e para rotear a chamada para esse PSAP, o que permite que o despachante PSAP obtenha a localização do chamador.  

Para chamadas dinâmicas de emergência, o seguinte deve ocorrer:

1. O administrador de rede configura as configurações de rede e o LIS para criar um mapa de localização de rede/emergência.

2. Durante a inicialização e, periodicamente, ou quando uma conexão de rede é alterada, o cliente do Teams envia uma solicitação de localização que contém suas informações de conectividade de rede para as configurações de rede e o LIS.

   - Se houver uma correspondência de site de configurações de rede – as políticas de chamada de emergência serão retornadas ao cliente do Teams desse site. (Para obter mais informações sobre políticas, consulte [Configurar políticas de emergência](#configure-emergency-policies)).

   - Se houver uma correspondência LIS – um local de emergência do elemento de rede ao qual o cliente do Teams está conectado será retornado ao cliente do Teams. A correspondência é executada na seguinte ordem com o primeiro resultado correspondente sendo retornado:
       - WAP
       - Comutador/porta Ethernet
       - Comutador Ethernet
       - Sub-rede

3. Quando o cliente do Teams faz uma chamada de emergência, o local de emergência é transmitido para a rede PSTN.

A capacidade de fazer o roteamento automático para o PSAP (Ponto de Resposta à Segurança Pública) apropriado varia dependendo do país de uso do usuário do Teams.

Os planos de chamada da Microsoft, os parceiros do Operator Connect e os parceiros do Teams Phone Mobile incluem serviços dinâmicos de roteamento de emergência para usuários no Estados Unidos e canadá.

No entanto, para o Roteamento Direto, é necessária configuração adicional para roteamento de chamadas de emergência e possivelmente para conectividade de parceiro. O administrador deve garantir que o gateway PSTN que roteia a chamada de emergência tenha sido configurado para adicionar informações de local ao INVITE de saída (definindo o parâmetro PidfloSupported como True no objeto de gateway PSTN online. Além disso, o administrador deve configurar a conexão com um provedor ERS (Serviço de Roteamento de Emergência) (Estados Unidos e Canadá) **OU** configurar o SBC (Session Border Controller) para um aplicativo ELIN (Número de Identificação de Local de Emergência). Para obter informações sobre provedores ERS, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).

Este artigo contém as seções a seguir.

- [Atribuir endereços de emergência](#assign-emergency-addresses)
- [Configurar configurações de rede](#configure-network-settings)
- [Configurar o Serviço de Informações de Localização](#configure-location-information-service)
- [Configurar políticas de emergência](#configure-emergency-policies)
- [Habilitar usuários e sites](#enable-users-and-sites)
- [Testar chamada de emergência](#test-emergency-calling)

Para obter mais informações sobre chamadas de emergência, incluindo informações sobre endereços de emergência e roteamento de chamadas de emergência, informações específicas para países e informações sobre configurações de rede e topologia de rede, confira o seguinte:

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)

Para obter mais informações sobre quais recursos estão disponíveis nas nuvens do governo, consulte [Suporte governamental](#government-support) no final deste artigo.


## <a name="supported-clients"></a>Clientes com suporte

Atualmente, há suporte para os seguintes clientes.  Volte com frequência para ver as atualizações desta lista.

- Cliente da área de trabalho do Teams para Microsoft Windows
- Cliente da área de trabalho do Teams para Apple macOS
- Cliente móvel do Teams para cliente apple iOS versão 1.0.92.2019121004 e App Store versão 1.0.92 e maior
- Cliente móvel do Teams para cliente Android e google play store versão 1416/1.0.0.2019121201 e maior
- Telefone do Teams versão 1449/1.0.94.2019110802 e maior
- Salas do Teams versão 4.4.25.0 e maior

> [!NOTE]
> Locais baseados em Sub-rede e WiFi têm suporte em todos os clientes do Teams com suporte. <br><br>
> O LLDP (Ethernet/Switch) tem suporte em:
> - Versões do Windows 10.0 e posteriores neste momento.<br>
> - Mac OS, que requer [software de habilitação LLDP](https://www.microsoft.com/download/details.aspx?id=103383).<br>
> - O Teams telefone com o aplicativo Teams versão 1449/1.0.94.2021110101 e posterior.

> [!NOTE]
> A chamada de emergência dinâmica, incluindo a notificação do security desk, não tem suporte no cliente Web do Teams. Para impedir que os usuários usem o cliente Web do Teams para chamar números PSTN, você pode definir uma política de chamada do Teams e desativar a configuração **de chamada Permitir PSTN Web** . Para saber mais, confira [Chamando políticas no Teams](teams-calling-policy.md) e [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). 

> [!NOTE]
> Os telefones 3PIP não dão suporte a chamadas dinâmicas de emergência. 



## <a name="assign-emergency-addresses"></a>Atribuir endereços de emergência

Você pode atribuir endereços de emergência da seguinte maneira:

- Para chamar usuários do Plano.

- Para usuários&mdash;do Operator Connect e do Teams Phone Mobile, dependendo dos recursos atribuídos ao número quando a operadora os carrega no inventário de um cliente.

- Para os identificadores de rede necessários para obter dinamicamente um local. 

Para dar suporte ao roteamento automatizado de chamadas de emergência no Estados Unidos, você deve garantir que os locais de emergência atribuídos aos identificadores de rede incluam os códigos geográficos associados. (Endereços de emergência sem códigos geográficos não podem ser atribuídos aos identificadores de rede necessários para locais dinâmicos.)

Azure Mapas é usado para serviços baseados em localização. Ao inserir um endereço de emergência usando o centro de administração do Microsoft Teams, o Teams verifica Azure Mapas para o endereço:

- Se uma correspondência for encontrada, os códigos geográficos serão incluídos automaticamente.

- Se uma correspondência não for encontrada, você terá a oportunidade de criar manualmente um endereço de emergência. Você pode usar o recurso de queda de PIN para fazer isso. 

> [!NOTE]
> Endereços de emergência com mais de dois anos de idade não podem ser atribuídos a identificadores de rede. Você precisará recriar endereços mais antigos.

Você adiciona e atribui endereços de emergência no centro de administração do Microsoft Teams ou usando o PowerShell. Para obter mais informações, consulte [Adicionar um local de emergência para sua organização](add-change-remove-emergency-location-organization.md) e [Atribuir um local de emergência para um usuário](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Configurar configurações de rede

As configurações de rede são usadas para determinar a localização de um cliente do Teams e para obter dinamicamente políticas de chamada de emergência e um local de emergência. Você pode configurar as configurações de rede de acordo com como sua organização deseja que a chamada de emergência funcione.

As configurações de rede incluem sites que incluem uma coleção de sub-redes e elas são usadas exclusivamente para atribuição de política dinâmica aos usuários. Por exemplo, uma política de chamada de emergência e uma política de roteamento de chamadas de emergência podem ser atribuídas ao "site de Redmond" para que qualquer usuário que ande de casa ou de outro local da Microsoft seja configurado com números de emergência, roteamento e mesa de segurança específicos para Redmond.  

Os endereços IP confiáveis contêm uma coleção dos endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Uma tentativa de obter uma política dinâmica ou local só será feita se o endereço IP externo do usuário corresponder a um endereço IP no endereço IP confiável.

Para obter mais informações sobre endereços IP, regiões de rede, sites e endereços de sub-rede, confira [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).

Você configura as configurações de rede no centro de administração do Microsoft Teams ou usando o PowerShell. Para saber mais, confira [Gerenciar sua topologia de rede para recursos de voz na nuvem](manage-your-network-topology.md).

Observe que pode levar algum tempo (até algumas horas) para algumas alterações nas configurações de rede (como um novo endereço, identificador de rede e assim por diante) para propagar e estar disponível para clientes do Teams.  

> [!Note]
> As sub-redes também podem ser definidas no LIS e podem ser associadas a um local de emergência.  As sub-redes LIS devem ser definidas pela ID de Rede que corresponde ao intervalo de IP da sub-rede atribuído aos clientes. Por exemplo, a ID de rede de um IP/máscara do cliente de 10.10.10.150/25 é 10.10.10.128. Para obter mais informações, confira [Noções básicas de endereçamento e sub-rede TCP/IP](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

> [!Important]
> Não há suporte para pesquisas de configuração de configuração de rede com implantações de serviço proxy de nuvem que modificam os endereços IP de origem de clientes do Teams.



**Para usuários do Plano de Chamada, Do Operador Connect e do Teams Phone Mobile:**

- Se a configuração dinâmica da notificação do security desk for necessária, você deverá configurar endereços IP confiáveis e sites de rede.

- Se apenas locais dinâmicos forem necessários, você deverá configurar apenas endereços IP confiáveis; A configuração de configurações de rede não é necessária.

- Se nenhum dos dois for necessário, a configuração de configurações de rede não será necessária. 

**Para usuários de Roteamento Direto:**

- Se for necessária a habilitação dinâmica da chamada de emergência ou da configuração dinâmica da notificação do security desk, você deverá configurar endereços IP confiáveis e sites de rede.

- Se apenas locais dinâmicos forem necessários, você deverá configurar apenas endereços IP confiáveis; A configuração de configurações de rede não é necessária.

- Se nenhum dos dois for necessário, a configuração de configurações de rede não será necessária.


## <a name="configure-location-information-service"></a>Configurar o Serviço de Informações de Localização

Um cliente do Teams obtém endereços de emergência dos locais associados a diferentes identificadores de rede. 

Para que um cliente obtenha um local, você deve preencher o LIS com identificadores de rede (sub-redes, WAPs, comutadores, portas) e locais de emergência. Você pode fazer isso no centro de administração do Microsoft Teams ou usando o PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, vá para **Locais** > **Redes & locais**.
2. Clique na guia que representa o identificador de rede que você deseja adicionar. Por exemplo, clique em **Sub-redes**, **pontos de acesso Wi-Fi**, **Comutadores** ou **Portas**. Em seguida, clique em **Adicionar**.
3. Conclua os campos, adicione um local de emergência e clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use os cmdlets a seguir para adicionar portas, comutadores, sub-redes e WAPs ao LIS.

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Se as sub-redes estiverem sendo usadas como parte de sites de rede, elas deverão ser redefinidas no Serviço de Informações de Localização para renderizar locais dinâmicos.

## <a name="configure-emergency-policies"></a>Configurar políticas de emergência

Use as políticas a seguir para configurar a chamada de emergência. Você pode gerenciar essas políticas no centro de administração do Microsoft Teams ou usando o PowerShell.

- **Política de roteamento de chamada de emergência – aplica-se apenas ao Roteamento Direto**. Essa política configura os números de emergência, máscaras por número, se desejado, e a rota PSTN por número. Você pode atribuir essa política aos usuários, a sites de rede ou a ambos. Para saber mais, confira [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto](manage-emergency-call-routing-policies.md).  

   (Os usuários do Plano de Chamada, do Operator Connect e do Teams Phone Mobile estão automaticamente habilitados para chamadas de emergência com os números de emergência do país com base no local de uso do Microsoft 365 ou Office 365.)

- **Política de chamada de emergência – aplica-se a Planos de Chamada, Conexão de Operador, Telefone do Teams Móvel e Roteamento Direto.** Essa política configura a experiência de notificação do security desk quando uma chamada de emergência é feita. Você pode definir quem notificar e como eles são notificados. Por exemplo, para notificar automaticamente o balcão de segurança da sua organização e fazer com que eles ouçam em chamadas de emergência.  Essa política pode ser atribuída a usuários ou sites de rede ou ambos. Para saber mais, confira [Gerenciar políticas de chamada de emergência no Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Habilitar usuários e sites

Você pode atribuir políticas de roteamento de chamadas de emergência e políticas de chamada de emergência aos usuários e aos sites. Tenha em mente que as políticas de roteamento de chamadas de emergência se aplicam apenas ao Roteamento Direto. (Embora seja possível atribuir essa política a um usuário do Plano de Chamada, do Operador Connect ou do Teams Phone Mobile, a política não terá efeito.)

Você atribui políticas no centro de administração do Microsoft Teams ou usando o PowerShell. Para saber mais, veja:

- [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto](manage-emergency-call-routing-policies.md)
- [Gerenciar políticas de chamada de emergência no Teams](manage-emergency-calling-policies.md)

Veja a seguir exemplos do PowerShell:

Para habilitar um usuário específico para notificação do security desk, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para atribuir uma política chamada "Contoso Emergency Calling Policy 1" ao Site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar um usuário de Roteamento Direto específico para chamadas de emergência, use o seguinte comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para atribuir uma política chamada "Roteamento de Chamadas de Emergência da Contoso New York" ao Site 1, use o seguinte comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se você atribuiu uma política de chamada de emergência a um site de rede e a um usuário e, se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.

## <a name="test-emergency-calling"></a>Testar chamada de emergência

Alguns ERSPs (Provedores de Serviço de Roteamento de Emergência) no Estados Unidos oferecem um bot de teste de chamada de emergência.

- **Os usuários do Plano de Chamada, do Operator Connect e do Teams Phone Mobile no Estados Unidos ou no Canadá** podem usar o número de emergência de teste predefinido 933 para validar sua configuração de chamada de emergência. Esse número é roteado para um bot, que, em seguida, ecoa o número de telefone do chamador (ID da linha de chamada), endereço de emergência ou local e se a chamada seria roteada automaticamente para o PSAP ou exibida primeiro.

- **Os clientes de Roteamento Direto no Estados Unidos** devem coordenar com seu ERSP para um serviço de teste.

## <a name="government-support"></a>Apoio do governo

A tabela a seguir mostra o suporte à chamada de emergência dinâmica nas nuvens do governo:

| Nuvem | Disponibilidade |
| :------------|:-------|
| Várias locatários em todo o mundo | Disponível em todos os clientes do Teams |
| GCC | Disponível em todos os clientes do Teams |
| GCCH | -Disponível na área de trabalho do Teams <br> -Disponível em clientes móveis do Teams <br> -Disponível em telefones do Teams, versão do aplicativo: 1449/1.0.94.2022061702 |
| Dod | -Disponível na área de trabalho do Teams <br>-Disponível em clientes móveis do Teams <br>-Pendente em telefones do Teams |

 ## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência ](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para seu usuário](assign-change-emergency-location-user.md)
- [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para os recursos de voz na nuvem](manage-your-network-topology.md)
