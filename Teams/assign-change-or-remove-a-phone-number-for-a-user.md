---
title: Atribuir, alterar ou remover o número de telefone de um usuário
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Saiba como atribuir, alterar ou remover um número de telefone comercial para suas equipes ou usuários do Skype for Business para que empresas e clientes externos possam fazer chamadas.
ms.openlocfilehash: f9792edf76d5d86a562516aa620bfbb62d26fdd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286281"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="419aa-103">Atribuir, alterar ou remover o número de telefone de um usuário</span><span class="sxs-lookup"><span data-stu-id="419aa-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="419aa-104">Ao configurar planos de chamada no Office 365, você atribui números de telefone a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="419aa-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="419aa-105">No cliente do Microsoft Teams, os números de telefone atribuídos podem ser visualizados clicando em **Chamadas**.</span><span class="sxs-lookup"><span data-stu-id="419aa-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Número de telefone do usuário exibido no Microsoft Teams.](media/teams-phone-number.png)

<span data-ttu-id="419aa-107">No cliente Skype for Business, o número de telefone que você atribuir será listado na caixa **telefone comercial** e não poderá ser alterado por um usuário.</span><span class="sxs-lookup"><span data-stu-id="419aa-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Work Phone Number is Greyed Out.](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="419aa-109">Se um usuário quiser [mudar seu número de telefone para o Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) e o número de telefone no aplicativo Skype for Business não puder ser alterado ou estiver esmaecido, isso significará que um administrador o definiu para ele e ele não poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="419aa-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="419aa-110">Ao configurar os usuários para que eles possam fazer e receber chamadas telefônicas, você deve primeiro usar o centro de administração do Skype for Business e atribuir um número de telefone, mas você pode alterar ou remover o número de telefone, se necessário.</span><span class="sxs-lookup"><span data-stu-id="419aa-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="419aa-111">Para saber como obter Planos de Chamadas no Office 365 e quanto custam, consulte [Licenças complementares do Skype for Business e Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="419aa-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
  
> [!NOTE]
> <span data-ttu-id="419aa-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="419aa-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="419aa-115">Atribuir um número de telefone a um usuário</span><span class="sxs-lookup"><span data-stu-id="419aa-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="419aa-116">![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="419aa-116">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="419aa-117">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="419aa-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="419aa-118">Vá para o > **portal herdado** **do centro de administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="419aa-118">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="419aa-119">Na navegação à esquerda, clique em**usuários de voz**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="419aa-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="419aa-120">Para ver a opção de **voz** no painel de navegação à esquerda no centro de administração do Skype for Business, primeiro você deve comprar pelo menos uma **licença do Enterprise E5**, uma licença complementar do **sistema de telefonia** ou uma licença do suplemento de conferência de **áudio** .</span><span class="sxs-lookup"><span data-stu-id="419aa-120">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="419aa-121">Na página **Usuários de voz**, localize e selecione o usuário ou usuários aos quais você quer atribuir um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="419aa-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="419aa-122">No painel Ação, clique em **Atribuir número**.</span><span class="sxs-lookup"><span data-stu-id="419aa-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="419aa-123">Na página **atribuir número** , na lista **selecionar número para atribuir** , selecione o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="419aa-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="419aa-124">Se você não vir nenhum número de telefone listado, será necessário [obter números de telefone para os usuários](/microsoftteams/getting-phone-numbers-for-your-users) primeiro.</span><span class="sxs-lookup"><span data-stu-id="419aa-124">If you don't see any phone numbers listed, you need to [get phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users) first.</span></span> <span data-ttu-id="419aa-125">Ou, se você usar o **centro de administração do Skype for Business** > **Voz** > página de**Números de telefone**, clique em **Adicionar**e depois em **Novos números de usuário**.</span><span class="sxs-lookup"><span data-stu-id="419aa-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="419aa-126">Para atribuir ou alterar o endereço de emergência associado, em **Selecione um local de emergência validado**, selecione o local na lista ou, se você tiver muitos locais definidos, insira o nome da cidade na caixa de pesquisa e clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="419aa-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="419aa-127">Depois de escolher o número de telefone e o endereço de emergência, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="419aa-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="419aa-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span><span class="sxs-lookup"><span data-stu-id="419aa-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="419aa-131">Alterar um número de telefone para um usuário</span><span class="sxs-lookup"><span data-stu-id="419aa-131">Change a phone number for a user</span></span>
 
<span data-ttu-id="419aa-132">![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="419aa-132">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="419aa-133">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="419aa-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="419aa-134">Vá para o > **portal herdado** **do centro de administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="419aa-134">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="419aa-135">Na navegação à esquerda, clique em**usuários de voz**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="419aa-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="419aa-136">Na página **Usuários de voz**, localize e selecione o usuário ou usuários para os quais você quer alterar o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="419aa-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="419aa-137">No painel Ação, em **número atribuído**, clique em **alterar**.</span><span class="sxs-lookup"><span data-stu-id="419aa-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="419aa-138">Na página **Atribuir número**, clique em **Alterar número**.</span><span class="sxs-lookup"><span data-stu-id="419aa-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="419aa-139">Na página **Atribuir número**, em **Selecionar número para atribuir**, use a lista para selecionar o novo número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="419aa-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="419aa-140">Para alterar o endereço de emergência associado, clique em **alterar local**e, em **Alterar endereço de emergência para**, selecione o local na lista ou, se você tiver muitos locais definidos, insira o nome da cidade na caixa de pesquisa e clique em **Pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="419aa-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="419aa-141">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="419aa-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="419aa-142">Remover um número de telefone de um usuário</span><span class="sxs-lookup"><span data-stu-id="419aa-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="419aa-143">![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="419aa-143">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="419aa-144">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="419aa-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="419aa-145">Vá para o > **portal herdado** **do centro de administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="419aa-145">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="419aa-146">Na navegação à esquerda, clique em**usuários de voz**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="419aa-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="419aa-147">Na página **Usuários de voz**, localize e selecione o usuário ou usuários dos quais você quer remover o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="419aa-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="419aa-148">No painel Ação, em **número atribuído**, clique em **remover**.</span><span class="sxs-lookup"><span data-stu-id="419aa-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="419aa-149">Na página **Remover número atribuído selecionado?**, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="419aa-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="419aa-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="419aa-150">Related topics</span></span>
[<span data-ttu-id="419aa-151">O que é validação de endereço?</span><span class="sxs-lookup"><span data-stu-id="419aa-151">What is address validation?</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[<span data-ttu-id="419aa-152">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="419aa-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="419aa-153">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="419aa-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="419aa-154">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="419aa-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 