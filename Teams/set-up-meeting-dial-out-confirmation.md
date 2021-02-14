---
title: Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como configurar o Teams para solicitar uma confirmação de discagem para impedir que os sistemas de caixa postal se conectem a reuniões quando a pessoa chamada não puder atender a chamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806141"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="47e0a-103">Configurar a confirmação de discagem de reunião para seus usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47e0a-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="47e0a-104">As discações de reunião e as chamadas de Telefonar para mim são maneiras muito úteis de convidar participantes para ingressar em uma reunião e para que os participantes existentes in join a meeting using a traditional or mobile phone.</span><span class="sxs-lookup"><span data-stu-id="47e0a-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="47e0a-105">No entanto, quando a pessoa chamada não consegue atender a chamada e a chamada é atendida por um sistema de caixa postal, o sistema de caixa postal é conectado à reunião e os participantes poderão ouvi-la até que ela seja removida da reunião.</span><span class="sxs-lookup"><span data-stu-id="47e0a-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="47e0a-106">Para impedir que os sistemas de caixa postal se conectem a reuniões quando uma discagem de reunião é enviada para um número de telefone e a pessoa chamada não consegue atender a chamada, você pode configurar o Teams para solicitar uma confirmação da pessoa chamada para que ela entre na reunião.</span><span class="sxs-lookup"><span data-stu-id="47e0a-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="47e0a-107">Se a pessoa chamada não puder atender a chamada e a chamada for atendida por um sistema de caixa postal, o sistema de caixa postal não será conectado à reunião porque ele não fornecerá uma confirmação para ingressar nele.</span><span class="sxs-lookup"><span data-stu-id="47e0a-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="47e0a-108">Quando esse recurso estiver habilitado, as pessoas que receberem uma chamada de discagem ou Telefonar para mim deverão confirmar que querem ingressar na reunião pressionando 1 em seu telefone tradicional ou celular.</span><span class="sxs-lookup"><span data-stu-id="47e0a-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="47e0a-109">Para habilitar esse recurso para todas as reuniões em sua organização, defina o parâmetro do ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como ```true``` .</span><span class="sxs-lookup"><span data-stu-id="47e0a-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="47e0a-110">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="47e0a-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="47e0a-111">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="47e0a-111">Related topics</span></span>

- [<span data-ttu-id="47e0a-112">Configurar o recurso Telefonar para Mim para os usuários</span><span class="sxs-lookup"><span data-stu-id="47e0a-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="47e0a-113">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="47e0a-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)