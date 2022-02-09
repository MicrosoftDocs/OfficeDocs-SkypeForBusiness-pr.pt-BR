---
title: Guia de início rápido - Configurando planos de chamada
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guia de início rápido para configurar planos de chamada em Microsoft Teams para que você possa obter um conjunto de usuários em execução.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7be6b946d174241467d2afa1b9d2e30f7946365c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398435"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guia de Início Rápido: Como configurar Planos de Chamadas no Microsoft Teams

Este guia ajudará você a obter um conjunto de usuários em execução para que eles possam explorar Planos de Chamada em Teams.

Leia o comunicado de 12 de dezembro de 2017 sobre Planos de Chamada no Teams: Comunicações Inteligentes dá a próxima etapa com a chamada [no Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos que, em paralelo com este guia de início rápido, você leia [](calling-plan-landing-page.md) Sistema de Telefonia com Planos de Chamada e FastTrack [](https://aka.ms/cloudvoice) para planejar e conduzir uma rolagem bem-sucedida.

Adicionando Planos de Chamadas - um recurso de Microsoft 365 e Office 365 alimentado pelo Skype for Business - agora você pode usar o Teams para fazer e receber chamadas telefônicas para ou para linhas de telefone fixo e telefones celulares por meio da PSTN (rede telefônica pública comutado).

![Captura de tela mostrando a página Contatos Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Pré-requisitos para habilite a guia **Chamadas** no Teams
Para habilitar Teams guia Chamadas no Teams os usuários precisam ter a chamada 1:1 habilitada no Teams e usando um cliente Teams que oferece suporte Teams chamada 1:1. Para saber como gerenciar chamadas 1:1 no Teams, leia [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Para saber quais clientes suportam a chamada, leia [Limites e especificações para](./limits-specifications-teams.md) Microsoft Teams.

> [!NOTE]
> Atualmente, a Caixa Postal não estará disponível na guia Chamadas, a menos que o usuário esteja habilitado para chamadas PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Pré-requisitos para habilite o **Dial Pad** no Teams
Para habilitar a guia **Dial Pad** no Teams e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para Sistema de Telefonia e Planos de Chamadas. Para saber como configurar Planos de Chamada, leia [Configurar Planos de Chamada](./set-up-calling-plans.md).
Além disso, para Teams usuários, você deve garantir que "Permitir chamada privada" está habilitado na política Teams chamada. Consulte [Gerenciar Teams durante a transição para o novo Microsoft Teams de administração](./manage-teams-skypeforbusiness-admin-center.md) para obter mais informações.
> [!NOTE]
> Você também pode usar o Roteamento Direto para permitir que seus usuários façam e recebam chamadas PSTN. Para saber como configurar o Roteamento Direto, leia [Configurar Roteamento Direto](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Usando o TeamsUpgradePolicy para controlar onde as chamadas estão em terra
Para controlar se as chamadas de entrada (e chats) chegam no Teams ou Skype for Business, os administradores usam o TeamsUpgradePolicy, usando o centro de administração do [Microsoft Teams](https://aka.ms/teamsadmincenter) ou usando uma sessão Windows PowerShell remota [com a sessão Skype for Business](/powershell/module/skype) cmdlets.


A configuração padrão do TeamsUpgradePolicy é o modo Ilhas, que foi projetado para garantir que os fluxos de trabalho comerciais existentes não sejam interrompidos durante uma implantação Teams. Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo roteadas para Skype for Business até que você atualize a política para habilitar chamadas de entrada para Teams.  Quando os destinatários estão no modo de ilhas:

 - Chamadas VOIP de entrada que se originaram Skype for Business sempre chegam no cliente Skype for Business destinatário.
 - Chamadas VOIP de entrada originadas em Teams no Teams, se o remetente e o receptor *estão no mesmo locatário*.
 - VoIP federado de entrada (independentemente de qual cliente se origina) e as chamadas PSTN sempre chegam no cliente Skype for Business destinatário.
 
Para garantir que as chamadas VOIP e PSTN de entrada sempre chegam no cliente Teams do usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (o que significa, atribua a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.  Para obter mais informações sobre modos de coexistência e TeamsUpgradePolicy, consulte [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

**NOTES**
 - Skype for Business telefones IP receberão chamadas, mesmo se o usuário estiver no modo TeamsOnly.  
 - Os usuários que foram provisionados com licenças de Sistema de Telefonia e Planos de Chamadas para uso com o Skype for Business Online (por exemplo, eles foram atribuídos a um valor de OnlineVoiceRoutingPolicy) , terão a guia Chamadas habilitadas no Teams e poderão fazer chamadas PSTN de saída do Teams sem que os administradores tenham que aceitar qualquer recurso administrativo action.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Como configurar os usuários para receber todas as chamadas VOIP e PSTN de entrada no Teams
Para garantir que os usuários recebam todas as chamadas VOIP e PSTN de entrada no Teams, de definir o modo de coexistência do usuário como TeamsOnly no centro de administração do Microsoft Teams ou use Skype for Business sessão de Windows PowerShell remota para atualizar o TeamsUpgradePolicy da seguinte maneira:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Confira também
[Configurar Planos de Chamadas](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Sistema de Telefonia com Planos de Chamadas](calling-plan-landing-page.md)

[Skype for Business referência de cmdlet do PowerShell](/powershell/module/skype)
