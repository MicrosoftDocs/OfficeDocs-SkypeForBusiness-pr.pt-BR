---
title: Discando de uma reunião para que outras pessoas possam participar
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
description: Os organizadores da reunião podem aprender a discar usando o aplicativo Teams para permitir que outras pessoas ingressem na mesma reunião usando seus telefones.
ms.openlocfilehash: f84f811d89847bfdf17f123abe9c2df88536bc76
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662101"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="53ff3-103">Discar de uma reunião do Microsoft Teams para que outras pessoas possam ingressar</span><span class="sxs-lookup"><span data-stu-id="53ff3-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="53ff3-104">Como organizador da reunião, você pode discar usando o aplicativo Teams para permitir que outras pessoas ingressem na mesma reunião usando seus telefones.</span><span class="sxs-lookup"><span data-stu-id="53ff3-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="53ff3-105">Ao discar para alguém, recomendamos que você faça isso usando números de telefone completos (incluindo o formato de código de país/região-E. 164).</span><span class="sxs-lookup"><span data-stu-id="53ff3-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="53ff3-106">Observe que:</span><span class="sxs-lookup"><span data-stu-id="53ff3-106">Please note that:</span></span>

- <span data-ttu-id="53ff3-107">Você pode discar somente se ingressar em uma reunião usando o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="53ff3-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="53ff3-108">O organizador da reunião foi habilitado para videoconferências ou, no caso de a licença de audioconferência não estiver atribuída, é permitida para fazer chamadas para a rede telefônica comutada pública via planos de chamada online ou roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="53ff3-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="53ff3-109">O organizador da reunião [recebe uma política de discagem online que permite discagem fora da conferência habilitada](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="53ff3-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="53ff3-110">Veja como fazer para discar para funcionar:</span><span class="sxs-lookup"><span data-stu-id="53ff3-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="53ff3-111">**Etapa 1:** Na reunião, use a captura de tela **adicionar pessoas** ![ da opção de botão adicionar pessoas ](media/add-people-button.png) para discar para um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="53ff3-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="53ff3-112">**Etapa 2:** Digite o número de telefone completo, incluindo o código de país/região na caixa **convidar alguém ou discar um número** .</span><span class="sxs-lookup"><span data-stu-id="53ff3-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Captura de tela da caixa convidar alguém ou discar um número](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="53ff3-114">Países e regiões aceitos</span><span class="sxs-lookup"><span data-stu-id="53ff3-114">Supported countries and regions</span></span>

<span data-ttu-id="53ff3-115">O recurso de discagem externa só está disponível para alguns países/regiões.</span><span class="sxs-lookup"><span data-stu-id="53ff3-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="53ff3-116">Para obter uma lista completa, consulte [disponibilidade de país e região para conferências de áudio e planos de chamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="53ff3-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="53ff3-117">Permitir que os usuários disquem</span><span class="sxs-lookup"><span data-stu-id="53ff3-117">Allow users to dial in</span></span>

<span data-ttu-id="53ff3-118">Se você estiver procurando instruções sobre como permitir que seus usuários disquem para uma reunião de equipe, consulte [números de telefone para videoconferência no Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="53ff3-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="53ff3-119">Quer saber mais sobre a conferência de áudio?</span><span class="sxs-lookup"><span data-stu-id="53ff3-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="53ff3-120">Experimentar ou comprar videoconferência</span><span class="sxs-lookup"><span data-stu-id="53ff3-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="53ff3-121">Licenciamento do complemento do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53ff3-121">Microsoft Teams add-on licensing</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
