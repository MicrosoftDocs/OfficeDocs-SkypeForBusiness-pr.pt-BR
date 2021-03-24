---
title: Atribuir ou alterar um local de emergência para um usuário
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
description: Neste artigo, você aprenderá sobre como atribuir ou alterar um local de emergência para usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102977"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="7a87f-103">Atribuir ou alterar um local de emergência para um usuário</span><span class="sxs-lookup"><span data-stu-id="7a87f-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="7a87f-104">Ao configurar Planos de Chamadas, você precisa atribuir um local de emergência a cada número de telefone ou usuário.</span><span class="sxs-lookup"><span data-stu-id="7a87f-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="7a87f-105">Em países europeus, o local de emergência é associado ao número de telefone quando você o consegue do Microsoft 365 ou do Office 365 ou quando você transfere um número de telefone para o Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a87f-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7a87f-106">Nos Estados Unidos, o local de emergência é associado ao número de telefone quando é atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7a87f-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="7a87f-107">O endereço de emergência pode ser alterado se o usuário atribuído a ele se mover para um novo local.</span><span class="sxs-lookup"><span data-stu-id="7a87f-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="7a87f-108">Para obter mais informações sobre endereços e locais de emergência, consulte [O que são locais de emergência, locais e roteamento de chamadas?](./what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="7a87f-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="7a87f-109">Para saber como obter um Plano de Chamada e quanto eles custam, consulte [Licenciamento de complemento do Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="7a87f-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="7a87f-110">Você pode atribuir ou alterar um local de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a87f-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="7a87f-111">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a87f-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="7a87f-112">Na navegação à esquerda do Centro de administração do Microsoft Teams, clique em **Números de Telefone** de  >  **Voz**.</span><span class="sxs-lookup"><span data-stu-id="7a87f-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="7a87f-113">Na página **Números de** telefone, clique na guia **Números,** selecione um número de usuário na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7a87f-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="7a87f-114">No painel **Editar,** em **Local de emergência,** faça um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7a87f-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="7a87f-115">Para atribuir um local de emergência, pesquise e selecione um local de emergência.</span><span class="sxs-lookup"><span data-stu-id="7a87f-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="7a87f-116">Para alterar o local de emergência já atribuído ao usuário, clique em **X** para remover o local existente e, em seguida, procure e selecione o local que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="7a87f-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="7a87f-117">Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desativar ou ativar o usuário de email com informações **de número de telefone**.</span><span class="sxs-lookup"><span data-stu-id="7a87f-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="7a87f-118">Por padrão, isso está em.</span><span class="sxs-lookup"><span data-stu-id="7a87f-118">By default, this is on.</span></span>

5. <span data-ttu-id="7a87f-119">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7a87f-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="7a87f-120">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a87f-120">Using PowerShell</span></span>

<span data-ttu-id="7a87f-121">Consulte [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="7a87f-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="7a87f-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7a87f-122">Related topics</span></span>

- [<span data-ttu-id="7a87f-123">Gerenciar chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="7a87f-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="7a87f-124">Adicionar, alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="7a87f-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="7a87f-125">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="7a87f-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="7a87f-126">Atribuir ou alterar um endereço de um local de emergência para um usuário</span><span class="sxs-lookup"><span data-stu-id="7a87f-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="7a87f-127">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="7a87f-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="7a87f-128">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="7a87f-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="7a87f-129">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="7a87f-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)