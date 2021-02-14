---
title: Discar de uma reunião para que outras pessoas possam ingressar
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Os organizadores da reunião podem aprender a discar usando o aplicativo Teams para permitir que outras pessoas in join the same meeting using their phones.
ms.openlocfilehash: 575ed18bd3dbd404dba947c0c4556d52e0653200
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788755"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="3b6b4-103">Discar de uma reunião do Microsoft Teams para que outras pessoas possam ingressar</span><span class="sxs-lookup"><span data-stu-id="3b6b4-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="3b6b4-104">Como organizador da reunião, você pode discar usando o aplicativo Teams para permitir que outras pessoas in join the same meeting using their phones.</span><span class="sxs-lookup"><span data-stu-id="3b6b4-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="3b6b4-105">Ao discar para alguém, recomendamos que você faça isso usando os números de telefone completos (incluindo o código do país/região – formato E.164).</span><span class="sxs-lookup"><span data-stu-id="3b6b4-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="3b6b4-106">Observe que:</span><span class="sxs-lookup"><span data-stu-id="3b6b4-106">Please note that:</span></span>

- <span data-ttu-id="3b6b4-107">Você só poderá discar se ingressar em uma reunião usando o Teams.</span><span class="sxs-lookup"><span data-stu-id="3b6b4-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="3b6b4-108">O organizador da reunião foi habilitado para audioconferência, OU, caso nenhuma licença de audioconferência seja atribuída, tem permissão para fazer chamadas para a rede telefônica pública comutado por meio de planos de chamada online ou roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="3b6b4-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="3b6b4-109">O organizador da reunião [recebe uma política de discagem online que habilita](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps) a discagem de conferência</span><span class="sxs-lookup"><span data-stu-id="3b6b4-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="3b6b4-110">Veja como fazer a discagem funcionar:</span><span class="sxs-lookup"><span data-stu-id="3b6b4-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="3b6b4-111">**Etapa 1:** Na reunião, use a captura de tela Adicionar **pessoas** da opção do botão Adicionar ![ pessoas para ](media/add-people-button.png) discar para um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="3b6b4-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="3b6b4-112">**Etapa 2:** Insira o número de telefone completo, incluindo o código do país/região na caixa Convidar **alguém ou disque um** número.</span><span class="sxs-lookup"><span data-stu-id="3b6b4-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Captura de tela da caixa Convidar alguém ou discar um número](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="3b6b4-114">Países e regiões com suporte</span><span class="sxs-lookup"><span data-stu-id="3b6b4-114">Supported countries and regions</span></span>

<span data-ttu-id="3b6b4-115">A discagem está disponível apenas para alguns países/regiões.</span><span class="sxs-lookup"><span data-stu-id="3b6b4-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="3b6b4-116">Para ver a lista completa, consulte a disponibilidade de país e [região para Planos de Audioconferência e Chamada.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="3b6b4-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="3b6b4-117">Permitir que os usuários disquem</span><span class="sxs-lookup"><span data-stu-id="3b6b4-117">Allow users to dial in</span></span>

<span data-ttu-id="3b6b4-118">Se você estiver procurando instruções sobre como permitir que os usuários disquem para uma reunião do Teams, consulte números de telefone para [Audioconferência no Microsoft Teams.](phone-numbers-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3b6b4-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="3b6b4-119">Quer saber mais sobre audioconferência?</span><span class="sxs-lookup"><span data-stu-id="3b6b4-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="3b6b4-120">Experimentar ou comprar Audioconferência</span><span class="sxs-lookup"><span data-stu-id="3b6b4-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="3b6b4-121">Licenciamento do complemento do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b6b4-121">Microsoft Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
