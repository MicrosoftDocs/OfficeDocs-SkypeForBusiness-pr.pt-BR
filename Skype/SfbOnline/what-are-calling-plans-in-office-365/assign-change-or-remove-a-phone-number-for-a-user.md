---
title: Atribuir, alterar ou remover um número de telefone de um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Saiba como atribuir, alterar ou remover um número de telefone de trabalho para usuários do Skype for Business de modo que outras empresas e clientes possam ligar para eles.
ms.openlocfilehash: 8c80bf9da5471f1a7293a01ed9e2d56f6e1aa15b
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780935"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="53149-103">Atribuir, alterar ou remover um número de telefone de um usuário</span><span class="sxs-lookup"><span data-stu-id="53149-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="53149-104">Ao configurar Planos de Chamadas no Office 365, você atribui números de telefone para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="53149-104">When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> 

<span data-ttu-id="53149-105">No cliente do Microsoft Teams, os números de telefone atribuídos podem ser visualizados clicando em **Chamadas**.</span><span class="sxs-lookup"><span data-stu-id="53149-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Número de telefone do usuário exibido no Microsoft Teams.](../images/teams-phone-number.png)

<span data-ttu-id="53149-107">No cliente do Skype for Business, o número de telefone que você atribuir será listado na caixa **Telefone Comercial** e não poderá ser alterado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="53149-107">The phone number you assign will be listed in the **This Work Phone** box in their Skype for Business client and can't be changed by a user.</span></span>
  
![O número de telefone comercial está em cinza.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="53149-109">Se um usuário desejar [alterar o número de telefone dele do Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) e o número no aplicativo do Skype for Business não puder ser alterado ou estiver cinza, isso significa que ele foi configurado por um administrador e pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="53149-109">If they want to [Change my phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) \*\* and the phone number in the Skype for Business app can't be changed or is grayed out\*\*, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="53149-110">Ao configurar usuários para fazer e receber chamadas telefônicas, você deve primeiro usar o centro de administração do Skype for Business para atribuir um número de telefone, mas ele pode ser alterado ou removido, se necessário.</span><span class="sxs-lookup"><span data-stu-id="53149-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="53149-111">Para saber como obter Planos de Chamadas no Office 365 e quanto custam, consulte [Licenças complementares do Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="53149-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="53149-112">Uma maneira de verificar se um usuário tem uma licença atribuída é acessando o **centro de administração do Skype for Business** > **Voz** > **Usuários de voz** e selecionando o usuário.</span><span class="sxs-lookup"><span data-stu-id="53149-112">One way to see if a user has a license assigned is in the **Skype for Business admin center** > **Voice** > **Voice users** and select the user.</span></span> <span data-ttu-id="53149-113">Se houver uma licença atribuída, ela estará listada sob **Licença atribuída**.</span><span class="sxs-lookup"><span data-stu-id="53149-113">If a license is assigned, it will be listed under the **Assigned license**.</span></span> <span data-ttu-id="53149-114">Você também pode usar o centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="53149-114">You can use the Office 365 admin center though too.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="53149-115">Atribuir um número de telefone a um usuário</span><span class="sxs-lookup"><span data-stu-id="53149-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="53149-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="53149-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="53149-117">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="53149-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="53149-118">Acesse o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="53149-118">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="53149-119">No painel de navegação esquerdo, clique em **Voz** > **Usuários de voz**.</span><span class="sxs-lookup"><span data-stu-id="53149-119">In the left navigation, **Voice** > **Voice users**.</span></span>
   > [!NOTE]
 <span data-ttu-id="53149-120">Para ver a opção **Voz** no painel de navegação à esquerda no centro de administração do Skype for Business, primeiro você deve comprar pelo menos uma **licença Enterprise E5**, uma licença complementar do **Sistema de Telefonia** ou de **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="53149-120">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="53149-121">Na página **Usuários de voz**, localize e selecione o usuário ou usuários a quem deseja atribuir um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="53149-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="53149-122">No Painel de ações, clique em **Atribuir número**.</span><span class="sxs-lookup"><span data-stu-id="53149-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="53149-123">Na página **Atribuir número**, na lista **Selecionar um número para atribuir**, selecione o número de telefone para o usuário.</span><span class="sxs-lookup"><span data-stu-id="53149-123">On the **Assign number** page in the **Select number to assign** list, then select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="53149-124">Se não houver nenhum número de telefone listado, você precisa [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md) primeiro.</span><span class="sxs-lookup"><span data-stu-id="53149-124">If you don't see any phone numbers listed, you need to go Getting Skype for Business phone numbers for your users first or If you use the Skype for Business admin center  Voice  Phone numbers page > click Add then New user numbers.</span></span> <span data-ttu-id="53149-125">Ou, se você usar o **centro de administração do Skype for Business** > **Voz** > página de**Números de telefone**, clique em **Adicionar**e depois em **Novos números de usuário**.</span><span class="sxs-lookup"><span data-stu-id="53149-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="53149-126">Para atribuir ou alterar o endereço de emergência associado, em **Selecionar a localização de emergência validada**, selecione a localização na lista ou, se você tiver muitas localizações definidas, insira o nome da cidade na caixa de pesquisa e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="53149-126">To assign or change the associated emergency address under Select validated emergency location, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
8. <span data-ttu-id="53149-127">Depois de escolher o número de telefone e o endereço de emergência, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="53149-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="53149-128">Devido à latência entre o Office 365 e o Skype for Business Online, pode levar até 24 horas para que os usuários sejam habilitados.</span><span class="sxs-lookup"><span data-stu-id="53149-128">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for user to be enabled.</span></span> <span data-ttu-id="53149-129">Se, após 24 horas, o número do telefone não for atribuído corretamente, [entre em contato o suporte para produtos de empresas - Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="53149-129">If after 24 hours, the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="53149-130">Estamos aqui para ajudar!</span><span class="sxs-lookup"><span data-stu-id="53149-130">We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="53149-131">Alterar um número de telefone de um usuário</span><span class="sxs-lookup"><span data-stu-id="53149-131">To change a phone number for a user</span></span>
 
<span data-ttu-id="53149-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="53149-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="53149-133">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="53149-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="53149-134">Acesse o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="53149-134">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="53149-135">No painel de navegação esquerdo, clique em **Voz** > **Usuários de voz**.</span><span class="sxs-lookup"><span data-stu-id="53149-135">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="53149-136">Na página **Usuários de voz**, localize e selecione o usuário ou usuários para quem deseja alterar o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="53149-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="53149-137">No Painel de ações em **Número atribuído**, clique em **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="53149-137">In the Action pane, under **Assigned number** click **Change number**.</span></span> 
    
6. <span data-ttu-id="53149-138">Na página **Atribuir número**, clique em **Alterar número**.</span><span class="sxs-lookup"><span data-stu-id="53149-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="53149-139">Na página **Atribuir número**, em **Selecionar número para atribuir**, use a lista para selecionar o novo número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="53149-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="53149-140">Para alterar o endereço de emergência associado, clique em **Alterar localização** e em **Alterar endereço de emergência** selecione a localização na lista ou, se você tiver muitas localizações definidas, insira o nome da cidade na caixa de pesquisa e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="53149-140">To change the associated emergency address click Change location and under Change emergency address to, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
9. <span data-ttu-id="53149-141">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="53149-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="53149-142">Remover um número de telefone de um usuário</span><span class="sxs-lookup"><span data-stu-id="53149-142">To remove a phone number from a user</span></span>
 
<span data-ttu-id="53149-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="53149-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="53149-144">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="53149-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="53149-145">Acesse o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="53149-145">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="53149-146">No painel de navegação esquerdo, clique em **Voz** > **Usuários de voz**.</span><span class="sxs-lookup"><span data-stu-id="53149-146">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="53149-147">Na página **Usuários de voz**, localize e selecione o usuário ou usuários de quem deseja remover o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="53149-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="53149-148">No Painel de ações, em **Número atribuído**, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="53149-148">In the Action pane, under **Assigned number** click **Remove**.</span></span> 
    
6. <span data-ttu-id="53149-149">Na página **Remover número atribuído selecionado?**, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="53149-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="53149-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="53149-150">Related topics</span></span>
[<span data-ttu-id="53149-151">O que é validação de endereço?</span><span class="sxs-lookup"><span data-stu-id="53149-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="53149-152">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="53149-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="53149-153">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="53149-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="53149-154">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="53149-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 