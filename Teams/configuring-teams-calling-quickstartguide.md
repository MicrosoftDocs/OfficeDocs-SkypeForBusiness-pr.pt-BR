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
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f3145455553c8126d66b3e56b69ec646f5f19ad
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530692"
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
Para habilitar a guia **chamadas** em equipes os usuários precisam ter o 1:1 chamando ativados nas equipes e usando um cliente de equipes que ofereça suporte a chamada de equipes de 1:1. Para saber como gerenciar 1:1 chamando em equipes, leia [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Para saber quais clientes suportam a chamada, leia [limites e as especificações para equipes da Microsoft](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Atualmente, caixa postal não estarão disponível na guia chamadas, a menos que o usuário está habilitado para chamadas PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Pré-requisitos para habilitar o **Teclado de discagem** em equipes
Para habilitar a guia **Teclado de discagem** em equipes e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o sistema telefônico e planos de chamada. Para saber como configurar planos de chamada, leia [Configurar planos de chamada](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Você também pode usar o roteamento direto para permitir que os usuários Obrigat e receber chamadas PSTN. Para saber como configurar o roteamento direto, leia a [Configurar o roteamento direto](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).

## <a name="teams-interop-policy-configuration"></a>Configuração da política de interoperabilidade do Microsoft Teams
Para permitir que equipes começar a receber chamadas, você precisará atualizar a política de atualização de equipes e política de interoperabilidade de equipes, usando [as equipes da Microsoft & Skype para Business Admin Center](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com o Skype para negócios [ `*-CsTeamsUpgradePolicy`e `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) cmdlets, para redirecionar chamadas para equipes.

Para obter mais informações sobre a política de atualização de equipes e política de interoperabilidade de equipes, consulte [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Para localizar os cmdlets do PowerShell que você precisa, digite "CsTeamsUpgradePolicy" ou "CsTeamsInteropPolicy" na caixa **filtro** no [Skype para documentação de cmdlet do PowerShell de negócios](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Padrão às equipes políticas de atualização e interoperabilidade
O Microsoft Teams tem uma configuração de política padrão criada para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante a implantação do Microsoft Teams. Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo encaminhadas para o Skype for Business até que você atualize a política para habilitar as chamadas de entrada para o Microsoft Teams. Isso garante que não haja interrupções involuntárias nos serviços de voz quando você começa a testar e implantar o Microsoft Teams.

As equipes de política de atualização por padrão é mantida em modo herdado que aceita a diretiva de interoperabilidade de equipes para determinar onde bate-papos e chamadas devem ser roteadas – equipes ou Skype para negócios.

> [!NOTE]
> Os comportamentos de equipes atualizar a política e política de interoperabilidade de equipes em breve será alterada conforme descrito na [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

A política de interoperabilidade do Microsoft Teams tem a seguinte configuração padrão:

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Por padrão, o comportamento da configuração padrão inclui:
* **Para os clientes existentes do Skype for Business**, esta política tem como objetivo garantir que as chamadas do Skype for Business sejam direcionadas para o Skype for Business, e as chamadas do Microsoft Teams sejam direcionadas para o Microsoft Teams. As chamadas PSTN e federadas serão direcionadas para o Skype for Business quando essa política estiver em vigor.
* **Para os clientes que não têm o Skype for Business**, quando em vigor, além das chamadas entre usuários do Microsoft Teams, somente as chamadas PSTN de saída estarão disponíveis no Microsoft Teams. Para receber chamadas PSTN no Microsoft Teams, será necessário alterar a política de interoperabilidade do Microsoft Teams atribuída a seus usuários.

> [!NOTE]
> A guia Chamadas estará habilitada no Microsoft Teams para os usuários que foram provisionados com licenças do Sistema de Telefonia e de Planos de Chamadas para uso com o Skype for Business Online e que têm configurada a política de interoperabilidade global padrão do Microsoft Teams, e eles poderão fazer chamadas PSTN de saída no Microsoft Teams sem a necessidade de qualquer ação por parte dos administradores.

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configuração do Microsoft Teams para receber chamadas PSTN de entrada
Para receber chamadas de PSTN de entrada em equipes, você precisará configurar equipes como o aplicativo de chamada pela aplicação da diretiva de atualização de equipes com a política de interoperabilidade de equipes correspondente que define o padrão `CallingDefaultClient` parâmetro às equipes.

> [!IMPORTANT]
> Recomendamos aplicar essa configuração a um conjunto inicial de usuários para explorar as incríveis novas funcionalidades de chamadas do Microsoft Teams antes de fazer alterações mais abrangentes ou em toda a organização.

Se você escolher continuar a usar a política de atualização de equipes herdada, use a diretiva de interoperabilidade de equipes pré-configurado seguinte para rotear chamadas de entrada PSTN às equipes:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Se você optar por usar a diretiva de atualização de equipes atualizada, você precisará atribuir o modo de TeamsOnly para seus usuários.

O comportamento da política acima inclui:
* **Para os clientes existentes do Skype for Business**, esta política tem como objetivo redirecionar as chamadas de entrada para o Microsoft Teams. Isso inclui chamadas VoIP (do Microsoft Teams e do Skype for Business) e PSTN. 
* **Para os clientes que não têm o Skype for Business**, quando em vigor, as chamadas PSTN serão recebidas no Microsoft Teams.

> [!WARNING]
> No momento, a alteração de `CallingDefaultClient` para o Microsoft Teams também afeta as chamadas para telefones IP do Skype for Business. As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams. Consulte o [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) para obter informações sobre o suporte para telefones SIP certificados existentes.

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Como configurar usuários para PSTN de receber chamadas em equipes
Ao usar a política de atualização de equipes herdada, aplica a política de interoperabilidade de equipes, conforme descrito acima via Skype para a sessão do Windows PowerShell remoto de negócios para redirecionar chamadas às equipes:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Se você optar por usar o modo de TeamsOnly, você pode alterar o modo de coexistência do usuário para TeamsOnly via Teams Microsoft & Skype para Business Admin Center, ou via Skype para a sessão do Windows PowerShell remoto de negócios para redirecionar chamadas às equipes:

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Consulte também
[Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Diretrizes de migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Referência de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype)

[Referência de cmdlets do PowerShell para o Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
