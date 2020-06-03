---
title: Atribuir ou alterar um local de emergência para um usuário
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
description: Neste artigo, você aprenderá a atribuir ou alterar um local de emergência para os usuários da sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f11bfd9762667823b4ec6b2883c9661f9f5754d0
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539498"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="6d4db-103">Atribuir ou alterar um local de emergência para um usuário</span><span class="sxs-lookup"><span data-stu-id="6d4db-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="6d4db-104">Quando você estiver configurando planos de chamada, será necessário atribuir um local de emergência para cada número de telefone ou usuário.</span><span class="sxs-lookup"><span data-stu-id="6d4db-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="6d4db-105">Em países europeus, o local de emergência está associado ao número de telefone quando você o recebe do Office 365 ou quando transfere um número de telefone para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d4db-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="6d4db-106">Nos Estados Unidos, o local de emergência está associado ao número de telefone quando ele é atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="6d4db-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="6d4db-107">O endereço de emergência pode ser alterado se o usuário ao qual ele está atribuído for movido para um novo local.</span><span class="sxs-lookup"><span data-stu-id="6d4db-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="6d4db-108">Para obter mais informações sobre endereços e locais de emergência, consulte [gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6d4db-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="6d4db-109">Para saber como obter um plano de chamadas e quanto eles custam, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6d4db-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="6d4db-110">Você pode atribuir ou alterar um local de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d4db-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6d4db-111">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d4db-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6d4db-112">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em números de telefone de **voz**  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="6d4db-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="6d4db-113">Na página **números de telefone** , clique na guia **números** , selecione um número de usuário na lista e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d4db-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="6d4db-114">No painel **Editar** , em **local de emergência**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6d4db-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="6d4db-115">Para atribuir um local de emergência, procure e selecione um local de emergência.</span><span class="sxs-lookup"><span data-stu-id="6d4db-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="6d4db-116">Para alterar o local de emergência que já está atribuído ao usuário, clique em **X** para remover o local existente e, em seguida, procure e selecione o local que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="6d4db-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="6d4db-117">Dependendo se você deseja enviar um email para o usuário com as informações do número de telefone, desative ou ative o **usuário de email com informações de número de telefone**.</span><span class="sxs-lookup"><span data-stu-id="6d4db-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="6d4db-118">Por padrão, ele está ativado.</span><span class="sxs-lookup"><span data-stu-id="6d4db-118">By default, this is on.</span></span>

5. <span data-ttu-id="6d4db-119">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6d4db-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="6d4db-120">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d4db-120">Using PowerShell</span></span>

<span data-ttu-id="6d4db-121">Consulte [set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="6d4db-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="6d4db-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6d4db-122">Related topics</span></span>

- [<span data-ttu-id="6d4db-123">Gerenciar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="6d4db-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="6d4db-124">Adicionar, alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="6d4db-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="6d4db-125">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="6d4db-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="6d4db-126">Atribuir ou alterar um endereço de um local de emergência para um usuário</span><span class="sxs-lookup"><span data-stu-id="6d4db-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="6d4db-127">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="6d4db-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="6d4db-128">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="6d4db-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="6d4db-129">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="6d4db-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
