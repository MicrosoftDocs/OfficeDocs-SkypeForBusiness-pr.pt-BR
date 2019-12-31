---
title: Guia de Início Rápido - Como configurar Planos de Chamadas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Guia de Início Rápido para configurar Planos de Chamadas no Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0bebe58780456435388f9f5c2b5ef75478dda12
ms.sourcegitcommit: e59914458b4c22cc12556795468bc019e00a8940
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2019
ms.locfileid: "40909999"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams
==============================================================

Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.

Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos que, em paralelo com este guia de início rápido, você leia o [sistema telefônico com planos de chamadas](calling-plan-landing-page.md) e o [FastTrack](https://aka.ms/cloudvoice) para planejar e conduzir uma implementação bem-sucedida.

Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).

![Captura de tela mostrando a página contatos no Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams
Para habilitar a guia **chamadas** em Teams os usuários precisam ter chamadas do 1:1 habilitadas no Teams e usar um cliente do teams que suporte chamadas para o 1:1 Teams. Para saber como gerenciar chamadas do 1:1 no Teams, leia [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Para saber quais clientes dão suporte à chamada, leia [limites e especificações do Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> No momento, o correio de voz não estará disponível na guia chamadas, a menos que o usuário esteja habilitado para chamadas PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Pré-requisitos para habilitar o **teclado de discagem** no Teams
Para habilitar a guia do **teclado de discagem** no Teams e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o sistema telefônico e planos de chamadas. Para saber como configurar planos de chamadas, leia [configurar planos de chamadas](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).
Além disso, somente para usuários do Teams, você deve garantir que "permitir chamadas privadas" esteja habilitado na política de chamada de equipes. Consulte [gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) para obter mais informações.
> [!NOTE]
> Você também pode usar o roteamento direto para permitir que os usuários façam e recebam chamadas PSTN. Para saber como configurar o roteamento direto, leia [Configurar roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Usar o TeamsUpgradePolicy para controlar onde as chamadas se esterram
Para controlar se as chamadas recebidas (e chats) chegam ao Teams ou ao Skype for Business, os administradores usam o TeamsUpgradePolicy usando o [centro de administração do Microsoft Teams](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com os cmdlets do [Skype for Business](https://docs.microsoft.com/powershell/module/skype) .


A configuração padrão de TeamsUpgradePolicy é o modo de ilhas, que é projetado para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante uma implantação do teams. Por padrão, VoIP, PSTN e chamadas federadas para seus usuários continuarão a ser roteadas para o Skype for Business até você atualizar a política para habilitar as chamadas de entrada para o Microsoft Teams.  Quando os destinatários estão no modo de ilhas:

 - As chamadas de VOIP recebidas que originou no Skype for Business sempre chegam ao cliente Skype for Business do destinatário.
 - Chamadas de VOIP recebidas originadas no Teams Land no Teams, *se o remetente e o receptor estiverem no mesmo locatário*.
 - VOIP federado de entrada (independentemente de qual o cliente originou) e as chamadas PSTN sempre chegam ao cliente Skype for Business do destinatário.
 
Para garantir que as chamadas VOIP e PSTN de entrada sejam sempre chamadas para o cliente do teams de um usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (ou seja, atribua a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.  Para obter mais informações sobre modos de coexistência e TeamsUpgradePolicy, consulte [orientação de migração e interoperabilidade para organizações que usam o Skype for Business em equipe](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) .

**INFORMA**
 - Os telefones IP do Skype for Business receberão chamadas, mesmo se o usuário estiver no modo TeamsOnly.  
 - Os usuários que foram provisionados com as licenças do sistema telefônico e planos de chamadas para uso com o Skype for Business online (por exemplo, um valor de OnlineVoiceRoutingPolicy) terão a guia chamadas habilitada no Teams e poderão fazer chamadas PSTN de saída de Equipes sem administradores precisarem tomar qualquer ação administrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Como configurar os usuários para receber todas as chamadas VOIP e PSTN de entrada no Microsoft Teams
Para garantir que os usuários recebam todas as chamadas VOIP e PSTN de entrada no Teams, defina o modo de coexistência do usuário como TeamsOnly no centro de administração do Microsoft Teams ou use a sessão remota do Windows PowerShell do Skype for Business para atualizar o TeamsUpgradePolicy da seguinte maneira:

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Confira também
[Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Sistema de Telefonia com Planos de Chamadas](calling-plan-landing-page.md)

[Referência do cmdlet do PowerShell do Skype for Business](https://docs.microsoft.com/powershell/module/skype)

