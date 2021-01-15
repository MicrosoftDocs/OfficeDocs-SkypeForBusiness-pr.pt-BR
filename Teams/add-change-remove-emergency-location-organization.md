---
title: Adicionar, alterar, remover locais de emergência
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
description: 'Saiba como adicionar, alterar ou remover um local de emergência para sua organização no centro de administração do Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799941"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="73778-103">Adicionar, alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="73778-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="73778-104">Um local de emergência deve ser associado a um número de telefone, mas quando isso acontece pode variar entre países e regiões.</span><span class="sxs-lookup"><span data-stu-id="73778-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="73778-105">Por exemplo, nos Estados Unidos, você precisa associar um local de emergência ao atribuir o número de telefone ao usuário.</span><span class="sxs-lookup"><span data-stu-id="73778-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="73778-106">No Reino Unido, você precisa associar um local de emergência ao número de telefone quando receber os números de telefone do Microsoft 365 ou Office 365 ou transferir números de telefone do seu provedor de serviços atual.</span><span class="sxs-lookup"><span data-stu-id="73778-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="73778-107">Não importa em qual país ou região você está, você pode adicionar um local ou locais a um local de emergência e remover um local de emergência.</span><span class="sxs-lookup"><span data-stu-id="73778-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="73778-108">Dependendo do número de locais físicos em sua organização, você pode criar locais para edifícios, andares e escritórios.</span><span class="sxs-lookup"><span data-stu-id="73778-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="73778-109">Consulte [Gerenciar chamada de emergência.](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="73778-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="73778-110">Para saber como obter um Plano de Chamada e quanto eles custam, consulte o licenciamento [de complementos do Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="73778-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="73778-111">Você gerencia locais de emergência para sua organização no centro de administração do Microsoft Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73778-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="73778-112">Adicionar um local de emergência</span><span class="sxs-lookup"><span data-stu-id="73778-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73778-113">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73778-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="73778-114">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** de Emergência de  >  **Locais.**</span><span class="sxs-lookup"><span data-stu-id="73778-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="73778-115">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="73778-115">Click **Add**.</span></span>
3. <span data-ttu-id="73778-116">Insira um nome e uma descrição para o local.</span><span class="sxs-lookup"><span data-stu-id="73778-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="73778-117">Selecione o país ou região e insira o endereço.</span><span class="sxs-lookup"><span data-stu-id="73778-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="73778-118">Na Bélgica, França, Alemanha, Irlanda, Países Baixos e Espanha, é importante entender que, para ativar com êxito um número de telefone no Microsoft 365 ou No Office 365, o endereço definido no local de emergência, que é usado para adquirir o número, deve corresponder ao código de área do número de telefone.</span><span class="sxs-lookup"><span data-stu-id="73778-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="73778-119">Se o endereço não for encontrado e você quiser editar manualmente o endereço, a opção **Editar o endereço manualmente.**</span><span class="sxs-lookup"><span data-stu-id="73778-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="73778-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73778-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73778-121">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73778-121">Using PowerShell</span></span>

<span data-ttu-id="73778-122">Consulte [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="73778-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="73778-123">Alterar um local de emergência</span><span class="sxs-lookup"><span data-stu-id="73778-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73778-124">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73778-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="73778-125">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** de Emergência de  >  **Locais.**</span><span class="sxs-lookup"><span data-stu-id="73778-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="73778-126">Na lista, selecione o local que você deseja alterar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="73778-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="73778-127">Faça as alterações que você deseja.</span><span class="sxs-lookup"><span data-stu-id="73778-127">Make the changes you want.</span></span>
4. <span data-ttu-id="73778-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73778-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="73778-129">Você só poderá alterar as informações de endereço de um local se o endereço não for validado.</span><span class="sxs-lookup"><span data-stu-id="73778-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="73778-130">Se o endereço já estiver validado e você precisar alterar o endereço, exclua o local e crie um novo local com o endereço correto.</span><span class="sxs-lookup"><span data-stu-id="73778-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73778-131">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73778-131">Using PowerShell</span></span>

<span data-ttu-id="73778-132">Consulte [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="73778-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="73778-133">Remover um local de emergência</span><span class="sxs-lookup"><span data-stu-id="73778-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73778-134">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73778-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="73778-135">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** de Emergência de  >  **Locais.**</span><span class="sxs-lookup"><span data-stu-id="73778-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="73778-136">Na lista, selecione o local que você deseja remover e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="73778-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73778-137">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73778-137">Using PowerShell</span></span>

<span data-ttu-id="73778-138">Consulte [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="73778-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="73778-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="73778-139">Related topics</span></span>

- [<span data-ttu-id="73778-140">Gerenciar chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="73778-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="73778-141">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="73778-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="73778-142">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="73778-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="73778-143">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="73778-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
