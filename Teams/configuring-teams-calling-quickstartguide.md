---
title: Guia de Início Rápido - Como configurar Planos de Chamadas no Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Guia de Início Rápido para configurar Planos de Chamadas no Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882094"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams
==============================================================

Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.

Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos que, em paralelo com este Guia de Início Rápido, você use as [orientações prática](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) e o [FastTrack](https://aka.ms/cloudvoice) para planejar e realizar uma distribuição bem-sucedida.

Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams
Para habilitar a guia **Chamadas** no Microsoft Teams e permitir que os usuários façam e recebam chamadas PSTN, será necessário provisionar os usuários para o Sistema de Telefonia e os Planos de Chamadas. Para saber como configurar, leia [Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).

## <a name="teams-interop-policy-configuration"></a>Configuração da política de interoperabilidade do Teams
Para permitir que o Teams comece a receber chamadas, você precisa atualizar a política de atualização do Teams e a política de interoperabilidade do Teams usando o [Centro de Administração do Microsoft Teams e do Skype for Business](https://aka.ms/teamsadmincenter) ou uma sessão remota do Windows PowerShell com os cmdlets do Skype for Business [`*-CsTeamsUpgradePolicy` e do `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) para redirecionar chamadas ao Teams.

Para obter mais informações sobre a política de atualização do Teams e a política de interoperabilidade do Teams, consulte [Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Para encontrar os cmdlets do PowerShell necessários, digite “CsTeamsUpgradePolicy” ou “CsTeamsInteropPolicy” na caixa **Filtrar** na [documentação de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Políticas de interoperabilidade e atualização padrão do Teams
O Teams tem uma configuração de política padrão criada para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante a implantação do Teams. Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo encaminhadas para o Skype for Business até que você atualize a política para habilitar as chamadas de entrada para o Microsoft Teams. Isso garante que não haja interrupções involuntárias nos serviços de voz quando você começa a testar e implantar o Teams.

Por padrão, a política de atualização do Teams é mantida no modo herdado que honrará a política de interoperabilidade do Teams para determinar onde os bate-papos e as chamadas devem ser encaminhados: Teams ou Skype for Business.

> [!NOTE]
> Os comportamentos da política de atualização do Teams e da política de interoperabilidade do Teams serão alterados em breve, conforme descrito em [Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

A política de interoperabilidade do Teams tem a seguinte configuração padrão:

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Por padrão, o comportamento da configuração padrão inclui:
* **Para os clientes existentes do Skype for Business**, esta política tem como objetivo garantir que as chamadas do Skype for Business sejam direcionadas para o Skype for Business, e as chamadas do Microsoft Teams sejam direcionadas para o Microsoft Teams. As chamadas PSTN e federadas serão direcionadas para o Skype for Business quando essa política estiver em vigor.
* **Para os clientes que não têm o Skype for Business**, quando em vigor, além das chamadas entre usuários do Microsoft Teams, somente as chamadas PSTN de saída estarão disponíveis no Microsoft Teams. Para receber chamadas PSTN no Microsoft Teams, será necessário alterar a política de interoperabilidade do Microsoft Teams atribuída a seus usuários.

> [!NOTE]
> A guia Chamadas estará habilitada no Microsoft Teams para os usuários que foram provisionados com licenças do Sistema de Telefonia e de Planos de Chamadas para uso com o Skype for Business Online e que têm configurada a política de interoperabilidade global padrão do Microsoft Teams, e eles poderão fazer chamadas PSTN de saída no Microsoft Teams sem a necessidade de qualquer ação por parte dos administradores.

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configuração do Teams para receber chamadas PSTN de entrada
Para receber chamadas PSTN de entrada no Teams, é necessário configurar o Teams como aplicativo de chamadas padrão, aplicando a política de atualização do Teams com a política de interoperabilidade do Teams correspondente que define o parâmetro `CallingDefaultClient` para o Teams.

> [!IMPORTANT]
> Recomendamos aplicar essa configuração a um conjunto inicial de usuários para explorar as incríveis novas funcionalidades de chamadas do Microsoft Teams antes de fazer alterações mais abrangentes ou em toda a organização.

Se você optar por continuar a usar a política de atualização herdada do Teams, use a seguinte política de interoperabilidade do Teams pré-configurada para rotear chamadas PSTN de entrada para o Teams:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Se você optar por usar a política de atualização do Teams atualizada, será necessário atribuir o modo TeamsOnly aos usuários.

Os comportamentos da política acima são os seguintes:
* **Para os clientes existentes do Skype for Business**, esta política tem como objetivo redirecionar as chamadas de entrada para o Microsoft Teams. Isso inclui chamadas VoIP (do Teams e do Skype for Business) e chamadas PSTN. 
* **Para os clientes que não têm o Skype for Business**, quando em vigor, as chamadas PSTN serão recebidas no Teams.

> [!WARNING]
> No momento, a alteração de `CallingDefaultClient` para o Teams também afeta as chamadas para telefones IP do Skype for Business. As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams. Consulte o [Roteiro de recursos do Skype for Business para o Microsoft Teams](https://aka.ms/skype2teamsroadmap) para obter informações sobre o suporte para telefones SIP certificados existentes.

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Como configurar os usuários para receber chamadas PSTN no Teams
Ao usar a política de atualização do Teams herdada, aplique a política de interoperabilidade do Teams, conforme descrito acima, via sessão do Windows PowerShell remoto do Skype for Business para redirecionar as chamadas para o Teams:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Se você optar por usar o modo TeamsOnly, será possível alterar o modo de coexistência do usuário para TeamsOnly por meio do Centro de Administração do Microsoft Teams e do Skype for Business ou sessão do Windows PowerShell remoto do Skype for Business para redirecionar chamadas para o Teams:

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Consulte também
[Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Referência de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype)

[Referência de cmdlets do PowerShell para o Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
