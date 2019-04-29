---
title: Guia de Início Rápido - Como configurar Planos de Chamadas no Microsoft Teams
author: arachmanGitHub
ms.author: Rowille
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: Rowille, lolaj
search.appverid: MET150
description: Guia de Início Rápido para configurar Planos de Chamadas no Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6c719d17938986ff6568b73864bc131667e4e7
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401979"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams
==============================================================

Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.

Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos que, em paralelo com este guia de início rápido, você leia [O sistema telefônico com planos de chamada](calling-plan-landing-page.md) e [FastTrack](https://aka.ms/cloudvoice) planejar e a unidade uma distribuição bem-sucedida.

Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams
Para habilitar a guia **chamadas** em equipes os usuários precisam ter o 1:1 chamando ativados nas equipes e usando um cliente de equipes que ofereça suporte a chamada de equipes de 1:1. Para saber como gerenciar 1:1 chamando em equipes, leia [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Para saber quais clientes suportam a chamada, leia [limites e as especificações para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Atualmente, caixa postal não estarão disponível na guia chamadas, a menos que o usuário está habilitado para chamadas PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Pré-requisitos para habilitar o **Teclado de discagem** em equipes
Para habilitar a guia **Teclado de discagem** em equipes e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o sistema telefônico e planos de chamada. Para saber como configurar planos de chamada, leia [Configurar planos de chamada](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Você também pode usar o roteamento direto para permitir que os usuários façam e recebam chamadas PSTN. Para saber como configurar o roteamento direto, leia a [Configurar o roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Usando TeamsUpgradePolicy para controlar onde chamadas land
Para controlar se as chamadas de entrada (e bate-papos) land em equipes ou Skype para os negócios, os administradores usam TeamsUpgradePolicy, usando o [Centro de administração de equipes da Microsoft](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com o [Skype para negócios](https://docs.microsoft.com/powershell/module/skype) cmdlets.


A configuração padrão do TeamsUpgradePolicy é o modo de ilhas, que foi projetado para garantir que os fluxos de trabalho não são interrompidos durante uma implantação de equipes de negócios existentes. Por padrão, a VoIP, PSTN e chamadas federadas para seus usuários continuarão a ser roteadas para Skype para negócios até que você atualiza a política para permitir que as chamadas de entrada para equipes.  Quando os destinatários estão no modo de ilhas:

 - Entrada VOIP chama esse Skype originado na for Business sempre land no Skype do destinatário para o cliente de negócios.
 - Entrada VOIP chama originados no land equipes em equipes, *se o remetente e o receptor estiverem no mesmo inquilino*.
 - Entrada federados VOIP (independentemente de qual cliente originado) e chamadas PSTN sempre land no Skype do destinatário para o cliente de negócios.
 
Para garantir a entrada VOIP e PSTN sempre chama land no cliente de equipes de um usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (o que significa que atribuí-las a instância de "UpgradeToTeams" do TeamsUpgradePolicy.  Para obter mais informações sobre os modos de coexistência e TeamsUpgradePolicy, consulte [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**NOTAS**
 - Skype para telefones IP Business receberá chamadas, mesmo se o usuário está no modo de TeamsOnly.  
 - Usuários que tenham sido configurados com o sistema telefônico e planos de chamar licenças para uso com o Skype para Business Online (por exemplo, eles tiverem sido atribuídos um valor de OnlineVoiceRoutingPolicy), terá a guia chamadas habilitada em equipes e pode fazer chamadas de PSTN de saída de Equipes sem precisar realizar qualquer ação administrativa de administradores.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Como configurar usuários para todos os VOIP e PSTN de entrada de receber chamadas em equipes
Para garantir que os usuários recebem todas as chamadas recebidas de VOIP e PSTN em equipes, definir o modo de coexistência do usuário para TeamsOnly no Centro de administração do Microsoft Teams, ou usar Skype para a sessão do Windows PowerShell remoto de negócios para atualizar TeamsUpgradePolicy da seguinte maneira:

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Confira também
[Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Sistema telefônico com a chamada de planos](calling-plan-landing-page.md)

[Skype para referência de cmdlet do PowerShell de negócios](https://docs.microsoft.com/powershell/module/skype)

