---
title: Definir idiomas do atendedor automático para audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Veja como selecionar os idiomas do atendedor automático de audioconferência para um número de audioconferência no Microsoft Teams.
ms.openlocfilehash: 73498e348b45b0fa2d9996344b569a92320a06b6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23893014"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="162e5-103">Definir idiomas do atendedor automático para audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="162e5-103">For information about setting the auto attendant language in Microsoft Teams, see Set auto attendant languages for Audio Conferencing in Microsoft Teams.</span></span>

<span data-ttu-id="162e5-104">O atendedor automático de audioconferência do Microsoft Teams pode cumprimentar os chamadores de áudio em diversos idiomas quando entram na reunião.</span><span class="sxs-lookup"><span data-stu-id="162e5-104">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="162e5-105">Escolha um idioma primário e até quatro idiomas secundários.</span><span class="sxs-lookup"><span data-stu-id="162e5-105">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="162e5-106">O idioma primário definido será usado primeiro e os idiomas secundários serão usados pelo atendedor automático na ordem que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="162e5-106">The primary language that you set will be used first and the secondary languages will be used in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="162e5-107">Você pode configurar os idiomas somente em números de telefone de acesso a áudio locais.</span><span class="sxs-lookup"><span data-stu-id="162e5-107">You can configure the languages on domestic dial-in access numbers only.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="162e5-108">Definir os idiomas do atendedor automático de audioconferência</span><span class="sxs-lookup"><span data-stu-id="162e5-108">Set the conferencing auto attendant languages</span></span>

1. <span data-ttu-id="162e5-109">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="162e5-109">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

2. <span data-ttu-id="162e5-110">Selecione o número de telefone da audioconferência na lista e, no topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="162e5-110">Select the audio conferencing phone number from the list, and at the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="162e5-111">No painel à direita, escolha o idioma padrão desejado e os idiomas alternativos.</span><span class="sxs-lookup"><span data-stu-id="162e5-111">In the pane on the right, choose the default language you want and any alternate languages.</span></span> 
 
    > [!NOTE]
    > <span data-ttu-id="162e5-112">Os idiomas padrão e alternativos aceitos são listados.</span><span class="sxs-lookup"><span data-stu-id="162e5-112">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="162e5-113">A ordem selecionada nas listas será a ordem em que os idiomas serão apresentados aos chamadores.</span><span class="sxs-lookup"><span data-stu-id="162e5-113">The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.</span></span> 

4. <span data-ttu-id="162e5-114">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="162e5-114">Click **Save**.</span></span>

    
## <a name="want-else-should-i-know"></a><span data-ttu-id="162e5-115">O que mais preciso saber?</span><span class="sxs-lookup"><span data-stu-id="162e5-115">Want else should I know?</span></span>

- <span data-ttu-id="162e5-116">Para ver a lista de idiomas com suporte para Audioconferência, consulte [Idiomas com suporte para Audioconferência](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).</span><span class="sxs-lookup"><span data-stu-id="162e5-116">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="162e5-117">Os idiomas podem ser definidos para números de telefone dedicados, mas não para números compartilhados.</span><span class="sxs-lookup"><span data-stu-id="162e5-117">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="162e5-118">Para ver uma lista de países/regiões onde a Audioconferência no Office 365 usando a Microsoft como provedor está disponível, consulte [Números de telefone para AudioConferência](phone-numbers-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="162e5-118">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="162e5-119">Deseja usar o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="162e5-119">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="162e5-120">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="162e5-120">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="162e5-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="162e5-121">Related topics</span></span>

[<span data-ttu-id="162e5-122">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="162e5-122">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

