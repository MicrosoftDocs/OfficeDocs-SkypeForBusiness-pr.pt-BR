---
title: Guia de início rápido – Configurando planos de chamada
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guia de início rápido para configurar planos de chamadas no Microsoft Teams para que você possa obter um conjunto de usuários em funcionamento.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789576"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guia de Início Rápido: Como configurar Planos de Chamadas no Microsoft Teams

Este guia ajudará você a obter um conjunto de usuários em funcionamento para que eles possam explorar os Planos de Chamadas no Teams.

Leia o comunicado de 12 de dezembro de 2017 sobre Planos de Chamadas no Teams: Comunicações Inteligentes dá a próxima etapa com a [chamada no Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos que, em paralelo com este guia de início rápido, você leia [](calling-plan-landing-page.md) o Sistema de Telefonia com Planos de Chamadas e [o FastTrack](https://aka.ms/cloudvoice) para planejar e impulsionar uma distribuição bem-sucedida.

Ao adicionar Planos de Chamadas - um recurso microsoft 365 e Office 365 da plataforma Skype for Business - agora você pode usar o Teams para fazer e receber chamadas telefônicas de ou para linhas terrestres e telefones celulares por meio da PSTN (rede telefônica pública comuada).

![Captura de tela mostrando a página Contatos no Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Pré-requisitos para habilitar a guia **Chamadas** no Teams
Para **habilitar a** guia Chamadas no Teams, os usuários precisam ter a chamada 1:1 habilitada no Teams e usar um cliente do Teams que dê suporte à chamada do Teams 1:1. Para saber como gerenciar chamadas 1:1 no Teams, leia [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Para saber quais clientes dão suporte à chamada, leia [Limites e especificações do Microsoft Teams](./limits-specifications-teams.md).

> [!NOTE]
> Atualmente, a caixa postal não estará disponível na guia Chamadas, a menos que o usuário esteja habilitado para chamadas PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Pré-requisitos para habilitar o Teclado **de Discagem** no Teams
Para habilitar a guia **Teclado** de Discagem no Teams e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o Sistema de Telefonia e Planos de Chamadas. Para saber como configurar Planos de Chamadas, leia [Configurar Planos de Chamadas](./set-up-calling-plans.md).
Além disso, somente para usuários do Teams, você deve garantir que "Permitir chamada privada" esteja habilitado na política de chamada do Teams. Consulte [Gerenciar o Teams durante a transição para o novo centro de administração do Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md) para obter mais informações.
> [!NOTE]
> Você também pode usar o Roteamento Direto para permitir que os usuários façam e recebam chamadas PSTN. Para saber como configurar o Roteamento Direto, leia [Configurar Roteamento Direto](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Usando TeamsUpgradePolicy para controlar onde as chamadas chegarão
Para controlar se as chamadas de entrada (e chats) são recebidas no Teams ou no Skype for Business, os administradores usam o TeamsUpgradePolicy, usando o centro de administração do [Microsoft Teams](https://aka.ms/teamsadmincenter) ou usando uma sessão Windows PowerShell remota com os cmdlets [Skype for Business](/powershell/module/skype).


A configuração padrão do TeamsUpgradePolicy é o modo Ilhas, que foi projetado para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante uma implantação do Teams. Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo roteadas para o Skype for Business até que você atualize a política para habilitar chamadas de entrada para o Teams.  Quando os destinatários estão no modo de ilhas:

 - Chamadas VOIP de entrada originadas Skype for Business sempre chegar ao cliente Skype for Business destinatário.
 - As chamadas VOIP de entrada originadas no Teams chegarão ao Teams, se o *remetente e o destinatário estão no mesmo locatário*.
 - VoIP federado de entrada (independentemente de qual cliente se origina) e chamadas PSTN sempre chegarão ao cliente Skype for Business destinatário.
 
Para garantir que as chamadas VOIP e PSTN de entrada sempre sejam feitas no cliente do Teams de um usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (o que significa atribuir a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.  Para obter mais informações sobre modos de coexistência e TeamsUpgradePolicy, consulte diretrizes de migração e interoperabilidade para organizações que usam o [Teams junto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

**NOTAS**
 - Skype for Business telefones IP receberão chamadas, mesmo se o usuário estiver no modo TeamsOnly.  
 - Os usuários que foram provisionados com licenças do Sistema de Telefonia e planos de chamadas para uso com o Skype for Business Online (por exemplo, eles recebem um valor de OnlineVoiceRoutingPolicy), terão a guia Chamadas habilitada no Teams e poderão fazer chamadas PSTN de saída do Teams sem que os administradores precisem tomar nenhuma ação administrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Como configurar os usuários para receber todas as chamadas VOIP e PSTN de entrada no Teams
Para garantir que os usuários recebam todas as chamadas VOIP e PSTN de entrada no Teams, defina o modo de coexistência do usuário como TeamsOnly no centro de administração do Microsoft Teams ou use Skype for Business sessão Windows PowerShell remota para atualizar o TeamsUpgradePolicy da seguinte maneira:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Confira também
[Configurar Planos de Chamadas](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Sistema de Telefonia com Planos de Chamadas](calling-plan-landing-page.md)

[Skype for Business de cmdlet do PowerShell](/powershell/module/skype)
