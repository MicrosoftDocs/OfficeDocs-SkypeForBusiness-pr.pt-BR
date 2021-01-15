---
title: Guia de início rápido - Configurando planos de chamada
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guia de início rápido para configurar planos de chamada no Microsoft Teams para que você possa obter um conjunto de usuários em execução.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799761"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams
==============================================================

Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.

Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos que, em paralelo com este guia [](calling-plan-landing-page.md) de início rápido, você leia o Sistema de Telefonia com Planos de Chamadas e [o FastTrack](https://aka.ms/cloudvoice) para planejar e conduzir uma lançamento bem-sucedida.

Adicionando Planos de Chamadas - um recurso do Microsoft 365 e office 365 com o Skype for Business - agora você pode usar o Teams para fazer e receber chamadas telefônicas de ou para linhas de telefone fixos e celulares por meio da PSTN (rede telefônica pública comutado).

![Captura de tela mostrando a página Contatos no Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams
Para habilitar a guia Chamadas no Teams, os usuários precisam ter chamadas 1:1 habilitadas no Teams e usar um cliente do Teams que oferece suporte à chamada 1:1 do Teams.  Para saber como gerenciar chamadas 1:1 no Teams, leia [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Para saber quais clientes suportam a chamada, leia [Limites e especificações do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)

> [!NOTE]
> Atualmente, a caixa postal não estará disponível na guia Chamadas, a menos que o usuário esteja habilitado para chamadas PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Pré-requisitos para habilite o **Teclado de Discagem** no Teams
Para habilitar a guia **Teclado** de Discagem no Teams e permitir que seus usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o Sistema de Telefonia e Planos de Chamadas. Para saber como configurar Planos de Chamada, leia [Configurar Planos de Chamada.](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)
Além disso, somente para usuários do Teams, você deve garantir que "Permitir chamada privada" está habilitado na política de chamada do Teams. Consulte [Gerenciar o Teams durante a transição para o novo centro de administração do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) para obter mais informações.
> [!NOTE]
> Você também pode usar o Roteamento Direto para permitir que seus usuários façam e recebam chamadas PSTN. Para saber como configurar o Roteamento Direto, leia [Configurar Roteamento Direto.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Usando o TeamsUpgradePolicy para controlar onde as chamadas chegarão
Para controlar se as chamadas de entrada (e chats) chegam ao Teams ou ao Skype for Business, os administradores usam o TeamsUpgradePolicy, usando o Centro de administração do [Microsoft Teams](https://aka.ms/teamsadmincenter) ou usando uma sessão Windows PowerShell remota com os cmdlets do Skype [for Business.](https://docs.microsoft.com/powershell/module/skype)


A configuração padrão do TeamsUpgradePolicy é o modo Ilhas, projetado para garantir que fluxos de trabalho comerciais existentes não sejam interrompidos durante uma implantação do Teams. Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão a ser roteadas para o Skype for Business até que você atualize a política para habilitar chamadas de entrada para o Teams.  Quando os destinatários estão no modo de ilhas:

 - Chamadas VOIP de entrada originadas no Skype for Business sempre chegam ao cliente skype for business do destinatário.
 - Chamadas VOIP de entrada originadas no Teams chegam ao Teams, se o remetente e o *receptor estão no mesmo locatário.*
 - VoIP federado de entrada (independentemente de qual cliente se origina) e as chamadas PSTN sempre chegam no cliente skype for business do destinatário.
 
Para garantir que as chamadas VOIP e PSTN de entrada sempre chegam ao cliente do Teams de um usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (o que significa atribuir a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.  Para obter mais informações sobre modos de coexistência e TeamsUpgradePolicy, consulte diretrizes de migração e [interoperabilidade](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) para organizações que usam o Teams em conjunto com o Skype for Business

**OBSERVAÇÕES**
 - Os telefones IP do Skype for Business receberão chamadas, mesmo se o usuário estiver no modo TeamsOnly.  
 - Os usuários que foram provisionados com licenças de Sistema de Telefonia e Planos de Chamadas para uso com o Skype for Business Online (por exemplo, eles têm um valor OnlineVoiceRoutingPolicy) , terão a guia Chamadas habilitadas no Teams e poderão fazer chamadas PSTN de saída do Teams sem que os administradores tenham que tomar qualquer ação administrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Como configurar os usuários para receberem todas as chamadas VOIP e PSTN de entrada no Teams
Para garantir que os usuários recebam todas as chamadas VOIP e PSTN de entrada no Teams, de definir o modo de coexistência do usuário como TeamsOnly no centro de administração do Microsoft Teams ou use a sessão de Windows PowerShell remota do Skype for Business para atualizar o TeamsUpgradePolicy da seguinte maneira:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Confira também
[Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Sistema de Telefonia com Planos de Chamadas](calling-plan-landing-page.md)

[Referência de cmdlet do PowerShell do Skype for Business](https://docs.microsoft.com/powershell/module/skype)

