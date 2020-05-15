---
title: Atribuir, alterar locais para locais de emergência para usuários
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Neste artigo, você aprenderá a atribuir ou alterar o local de um local de emergência para os usuários da sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5b13cf5d4b4a0cf22077318e3c2c2196840f66e
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232462"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="9782a-103">Atribuir ou alterar o local de um local de emergência de um usuário</span><span class="sxs-lookup"><span data-stu-id="9782a-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="9782a-104">Cada número de telefone ativo deve ter um local de emergência associado ao atribuir o número de telefone a um usuário.</span><span class="sxs-lookup"><span data-stu-id="9782a-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="9782a-105">(Você associa o endereço quando recebe um número de telefone no Office 365 ou quando transfere um número de telefone.) Ao associar o número a um local de emergência, você também pode adicionar um local para fornecer um local mais exato em um local físico.</span><span class="sxs-lookup"><span data-stu-id="9782a-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="9782a-106">Um local pode ser o andar, o asa do prédio ou o número do escritório onde o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="9782a-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="9782a-107">Você pode ter um número ilimitado de locais para um determinado local de emergência, e você pode alterar o local se o usuário se mover para um escritório ou prédio diferente.</span><span class="sxs-lookup"><span data-stu-id="9782a-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="9782a-108">Por exemplo, se o usuário se move do andar 34 para o andar 35.</span><span class="sxs-lookup"><span data-stu-id="9782a-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="9782a-109">Para saber como obter planos de chamada e quanto eles custam, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="9782a-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="9782a-110">Você pode atribuir ou alterar o local de uma localização de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9782a-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9782a-111">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9782a-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9782a-112">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em números de telefone de **voz**  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="9782a-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="9782a-113">Na página **números de telefone** , selecione um número de usuário na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9782a-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="9782a-114">No painel **Editar** , em **local de emergência**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9782a-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="9782a-115">Para atribuir um local, procure o local ou o local e selecione o local nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9782a-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="9782a-116">Para alterar o local que já está atribuído ao usuário, clique em **X** para remover o local e o local existentes, procure e selecione o local que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="9782a-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="9782a-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9782a-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="9782a-118">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9782a-118">Using PowerShell</span></span>

<span data-ttu-id="9782a-119">Consulte [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="9782a-119">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9782a-120">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9782a-120">Related topics</span></span>

- [<span data-ttu-id="9782a-121">Gerenciar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="9782a-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="9782a-122">Adicionar, alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="9782a-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="9782a-123">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="9782a-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="9782a-124">Atribuir ou alterar um local de emergência para um usuário</span><span class="sxs-lookup"><span data-stu-id="9782a-124">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="9782a-125">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="9782a-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="9782a-126">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="9782a-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
