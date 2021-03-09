---
title: Definir a identificação de chamadas para um usuário
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Saiba mais sobre a ID padrão do chamador do Microsoft 365 e do Office 365 (o número de telefone atribuído pelo usuário), também conhecido como ID de Linha de Chamada. Você pode alterar ou bloquear a ID do chamador do usuário.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569413"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="14819-104">Definir a identificação de chamadas para um usuário</span><span class="sxs-lookup"><span data-stu-id="14819-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="14819-105">O Sistema de Telefonia no Microsoft 365 e no Office 365 fornece uma ID padrão do chamador que é o número de telefone atribuído pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="14819-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="14819-106">Você pode alterar ou bloquear a ID de chamadas (também chamada de ID da linha de chamada) de um usuário.</span><span class="sxs-lookup"><span data-stu-id="14819-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="14819-107">Você pode saber mais sobre como usar a ID do chamador em sua organização, indo Como a ID do chamador pode ser [usada em sua organização.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="14819-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="14819-108">Você não pode bloquear as chamadas recebidas atualmente no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="14819-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="14819-109">Há duas configurações que você pode alterar:</span><span class="sxs-lookup"><span data-stu-id="14819-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="14819-110">[!OBSERVAçãO] Isso **não é** para organizações locais com o Lync ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="14819-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="14819-p103">**Mudar a ID de chamadas de saída** Você pode substituir a ID de chamadas de um usuário (que, por padrão, é seu número de telefone) por outro número de telefone. Por exemplo, você pode mudar a ID de chamadas do usuário de seu número de telefone para o número de telefone principal de sua empresa ou alterar a ID de Linha de Chamada do usuário de seu número de telefone para o número de telefone principal do departamento jurídico. Você pode mudar o número de ID de chamadas para o número de qualquer **serviço** online (chamada tarifada ou gratuita).</span><span class="sxs-lookup"><span data-stu-id="14819-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14819-114">[!OBSERVAçãO] Se você desejar usar o parâmetro  _Service_, especifique um número de serviço válido.</span><span class="sxs-lookup"><span data-stu-id="14819-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="14819-115">**Bloquear a ID do chamador de saída** Você pode impedir que a ID do Chamador de saída seja enviada em chamadas PSTN de saída de um usuário.</span><span class="sxs-lookup"><span data-stu-id="14819-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="14819-116">Isso impede que o número de telefone seja exibido no telefone da pessoa que está sendo chamada.</span><span class="sxs-lookup"><span data-stu-id="14819-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="14819-117">**Bloquear a ID do chamador de entrada** Você pode impedir que um usuário receba a ID do Chamador em qualquer chamada PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="14819-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="14819-118">[!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas).</span><span class="sxs-lookup"><span data-stu-id="14819-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="14819-p105">Por padrão, essas configurações de ID de chamadas são **desativadas**. Isso significa que o número de telefone do usuário do Skype for Business Online pode ser visto quando o usuário faz uma chamada para um telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="14819-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="14819-121">Para saber mais sobre essas configurações e como você pode usá-las, clique [Como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="14819-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="14819-122">Definir as configurações de política de ID de chamadas</span><span class="sxs-lookup"><span data-stu-id="14819-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="14819-123">Para todas as configurações de ID do Chamador no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de administração **do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="14819-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="14819-124">Iniciar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="14819-124">Start PowerShell</span></span>

- <span data-ttu-id="14819-125">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="14819-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="14819-126">Veja todas as configurações de ID de chamadas em sua organização</span><span class="sxs-lookup"><span data-stu-id="14819-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="14819-127">Para exibir todas as configurações de política de ID do chamador em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="14819-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="14819-128">Consulte mais exemplos e detalhes [para Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="14819-128">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="14819-129">Criar uma nova política de ID de chamadas para sua organização</span><span class="sxs-lookup"><span data-stu-id="14819-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="14819-130">Para criar uma nova política de ID do chamador que define a ID do chamador como anônima, execute:</span><span class="sxs-lookup"><span data-stu-id="14819-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="14819-131">Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.</span><span class="sxs-lookup"><span data-stu-id="14819-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="14819-132">Consulte mais exemplos e detalhes [para New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="14819-132">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="14819-133">Para aplicar a nova política criada ao Amos Marble, execute:</span><span class="sxs-lookup"><span data-stu-id="14819-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="14819-134">Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="14819-134">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="14819-135">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="14819-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="14819-136">Defina a política para que a ID de chamadas de entrada seja bloqueada</span><span class="sxs-lookup"><span data-stu-id="14819-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="14819-137">Para bloquear a ID do chamador de entrada, execute:</span><span class="sxs-lookup"><span data-stu-id="14819-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="14819-138">Consulte mais exemplos e detalhes [para Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="14819-138">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="14819-139">Para aplicar a configuração de política criada a um usuário em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="14819-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="14819-140">Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="14819-140">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="14819-141">Remover uma política de ID de chamadas</span><span class="sxs-lookup"><span data-stu-id="14819-141">Remove a caller ID policy</span></span>

<span data-ttu-id="14819-142">Para remover uma política da sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="14819-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="14819-143">Para remover uma política de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="14819-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="14819-144">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="14819-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="14819-145">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="14819-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="14819-146">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="14819-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="14819-147">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="14819-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="14819-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="14819-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="14819-149">Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="14819-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="14819-150">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="14819-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="14819-151">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="14819-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="14819-152">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14819-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="14819-153">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="14819-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="14819-154">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="14819-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="14819-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="14819-155">Related topics</span></span>
[<span data-ttu-id="14819-156">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="14819-156">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="14819-157">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="14819-157">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="14819-158">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="14819-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="14819-159">Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador</span><span class="sxs-lookup"><span data-stu-id="14819-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="14819-160">Termos e condições para chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="14819-160">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="14819-161">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="14819-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
