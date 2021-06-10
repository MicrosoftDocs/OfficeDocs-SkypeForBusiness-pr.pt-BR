---
title: Atribuir, alterar locais para locais de emergência para usuários
author: cichur
ms.author: v-cichur
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
description: Neste artigo, você aprenderá a atribuir ou alterar o local para um local de emergência para usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120823"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="1e1a8-103">Atribuir ou alterar o local para um local de emergência para um usuário</span><span class="sxs-lookup"><span data-stu-id="1e1a8-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="1e1a8-104">Cada número de telefone ativo deve ter um local de emergência associado quando você atribui o número de telefone a um usuário.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="1e1a8-105">(Você associa o endereço quando você tem um número de telefone no Office 365 ou quando você transfere um número de telefone.) Ao associar o número a um local de emergência, você também pode adicionar um local para fornecer um local mais exato em um local físico.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="1e1a8-106">Um local pode ser o piso, a asa de construção ou o número do escritório onde o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="1e1a8-107">Você pode ter um número ilimitado de locais para um determinado local de emergência e pode alterar o local se o usuário mudar para um escritório ou edifício diferente.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="1e1a8-108">Por exemplo, se o usuário mudar do piso 34 para o 35º andar.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="1e1a8-109">Para saber como obter Planos de Chamada e quanto eles custam, [consulte Teams licenciamento de complemento.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="1e1a8-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="1e1a8-110">Você pode atribuir ou alterar o local para um local de emergência para um usuário no centro de administração Microsoft Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1e1a8-111">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e1a8-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1e1a8-112">Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Voz Telefone**  >  **números**.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="1e1a8-113">Na página **Telefone números,** clique na guia **Números,** selecione um número de usuário na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="1e1a8-114">No painel **Editar,** em **Local de emergência,** faça um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="1e1a8-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="1e1a8-115">Para atribuir um local, pesquise o local ou o local e selecione o local nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="1e1a8-116">Para alterar o local já atribuído ao usuário, clique em **X** para remover o local e o local existentes, procure e selecione o local que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="1e1a8-117">Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desativar ou ativar o usuário de email com informações **de número de telefone**.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="1e1a8-118">Por padrão, isso está em.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-118">By default, this is on.</span></span>

5. <span data-ttu-id="1e1a8-119">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="1e1a8-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="1e1a8-120">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1a8-120">Using PowerShell</span></span>

<span data-ttu-id="1e1a8-121">Consulte [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="1e1a8-121">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="1e1a8-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1e1a8-122">Related topics</span></span>

- [<span data-ttu-id="1e1a8-123">Gerenciar chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="1e1a8-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="1e1a8-124">Adicionar, alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="1e1a8-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="1e1a8-125">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="1e1a8-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="1e1a8-126">Atribuir ou alterar um local de emergência para um usuário</span><span class="sxs-lookup"><span data-stu-id="1e1a8-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="1e1a8-127">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="1e1a8-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="1e1a8-128">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="1e1a8-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)