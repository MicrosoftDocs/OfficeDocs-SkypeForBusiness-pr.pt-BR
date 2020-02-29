---
title: Configurar discagem externa da reunião-confirmação para seus usuários no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o Microsoft Teams para solicitar uma confirmação de discagem para impedir que sistemas de correio de voz se conectem a reuniões quando a pessoa chamada não conseguir atender a chamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339466"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="decc3-103">Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="decc3-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="decc3-104">As chamadas discadas na reunião e chamadas para mim são muito úteis para convidar participantes a participarem de uma reunião e para que os participantes existentes ingressem em uma reunião usando um telefone tradicional ou celular.</span><span class="sxs-lookup"><span data-stu-id="decc3-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="decc3-105">No entanto, quando a pessoa chamada não consegue atender a chamada e a chamada é atendida por um sistema de correio de voz, o sistema de correio de voz está conectado à reunião e os participantes poderão ouvi-la até ser removida da reunião.</span><span class="sxs-lookup"><span data-stu-id="decc3-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="decc3-106">Para impedir que sistemas de correio de voz se conectem a reuniões quando uma reunião discada for enviada para um número de telefone e a pessoa chamada não conseguir atender a chamada, você poderá configurar o Microsoft Teams para solicitar uma confirmação da pessoa chamada para ela ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="decc3-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="decc3-107">Se a pessoa chamada não conseguir atender a chamada e a chamada for respondida por um sistema de correio de voz, o sistema de correio de voz não será conectado à reunião porque não fornecerá uma confirmação para ingressar nela.</span><span class="sxs-lookup"><span data-stu-id="decc3-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="decc3-108">Quando essa funcionalidade estiver habilitada, as pessoas que receberem chamadas discadas ou chamadas para mim deverão confirmar que desejam ingressar na reunião pressionando 1 no seu telefone tradicional ou celular.</span><span class="sxs-lookup"><span data-stu-id="decc3-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="decc3-109">Para habilitar esse recurso para todas as reuniões em sua organização, defina ```EnableDialOutJoinConfirmation``` o parâmetro do cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como ```true```.</span><span class="sxs-lookup"><span data-stu-id="decc3-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="decc3-110">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="decc3-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="decc3-111">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="decc3-111">Related topics</span></span>

- [<span data-ttu-id="decc3-112">Configurar o recurso Telefonar para Mim para os usuários</span><span class="sxs-lookup"><span data-stu-id="decc3-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="decc3-113">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="decc3-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)