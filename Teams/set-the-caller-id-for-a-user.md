---
title: Definir a identificação de chamadas para um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
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
description: The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going How can caller ID be used in your organization.
ms.openlocfilehash: 41fe8775ae98828a5c242c21a910906f8f4699eb
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221375"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="b960b-105">Definir a identificação de chamadas para um usuário</span><span class="sxs-lookup"><span data-stu-id="b960b-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="b960b-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span><span class="sxs-lookup"><span data-stu-id="b960b-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="b960b-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span><span class="sxs-lookup"><span data-stu-id="b960b-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="b960b-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="b960b-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="b960b-109">Você não pode bloquear as chamadas recebidas atualmente no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="b960b-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="b960b-110">Há duas configurações que você pode alterar:</span><span class="sxs-lookup"><span data-stu-id="b960b-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="b960b-111">[!OBSERVAçãO] Isso **não é** para organizações locais com o Lync ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b960b-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="b960b-p103">**Mudar a ID de chamadas de saída** Você pode substituir a ID de chamadas de um usuário (que, por padrão, é seu número de telefone) por outro número de telefone. Por exemplo, você pode mudar a ID de chamadas do usuário de seu número de telefone para o número de telefone principal de sua empresa ou alterar a ID de Linha de Chamada do usuário de seu número de telefone para o número de telefone principal do departamento jurídico. Você pode mudar o número de ID de chamadas para o número de qualquer **serviço** online (chamada tarifada ou gratuita).</span><span class="sxs-lookup"><span data-stu-id="b960b-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b960b-115">[!OBSERVAçãO] Se você desejar usar o parâmetro  _Service_, especifique um número de serviço válido.</span><span class="sxs-lookup"><span data-stu-id="b960b-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="b960b-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span><span class="sxs-lookup"><span data-stu-id="b960b-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="b960b-118">**Bloquear a identificação de chamadas de entrada** Você pode impedir que um usuário receba a identificação de chamadas em chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="b960b-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b960b-119">[!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas).</span><span class="sxs-lookup"><span data-stu-id="b960b-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="b960b-p105">Por padrão, essas configurações de ID de chamadas são **desativadas**. Isso significa que o número de telefone do usuário do Skype for Business Online pode ser visto quando o usuário faz uma chamada para um telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="b960b-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="b960b-122">Para saber mais sobre essas configurações e como você pode usá-las, clique [Como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="b960b-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="b960b-123">Definir as configurações de política de ID de chamadas</span><span class="sxs-lookup"><span data-stu-id="b960b-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="b960b-124">Para todas as configurações de identificação de chamadas no Skype for Business Online, você deve usar o Windows PowerShell e **não pode usar** o **centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="b960b-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="b960b-125">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b960b-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="b960b-126">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="b960b-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="b960b-127">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b960b-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b960b-128">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b960b-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="b960b-129">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b960b-129">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="b960b-130">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="b960b-130">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="b960b-131">Restart your computer when you are prompted.</span><span class="sxs-lookup"><span data-stu-id="b960b-131">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="b960b-p107">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="b960b-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="b960b-135">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="b960b-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="b960b-136">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b960b-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="b960b-137">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b960b-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b960b-138">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="b960b-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="b960b-139">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="b960b-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="b960b-140">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b960b-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="b960b-141">Veja todas as configurações de ID de chamadas em sua organização</span><span class="sxs-lookup"><span data-stu-id="b960b-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="b960b-142">Para ver todas as configurações de política de identificação de chamadas em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="b960b-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="b960b-143">Veja mais exemplos e detalhes do [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="b960b-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="b960b-144">Criar uma nova política de ID de chamadas para sua organização</span><span class="sxs-lookup"><span data-stu-id="b960b-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="b960b-145">Para criar uma nova política de identificação de chamadas que defina a identificação de chamadas como anônima, execute:</span><span class="sxs-lookup"><span data-stu-id="b960b-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="b960b-146">Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.</span><span class="sxs-lookup"><span data-stu-id="b960b-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="b960b-147">Veja mais exemplos e detalhes do [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="b960b-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="b960b-148">Para aplicar a nova política criada para o Marble Amos, execute:</span><span class="sxs-lookup"><span data-stu-id="b960b-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="b960b-149">Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="b960b-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="b960b-150">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b960b-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="b960b-151">Defina a política para que a ID de chamadas de entrada seja bloqueada</span><span class="sxs-lookup"><span data-stu-id="b960b-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="b960b-152">Para bloquear a identificação de chamadas de entrada, execute:</span><span class="sxs-lookup"><span data-stu-id="b960b-152">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="b960b-153">Veja mais exemplos e detalhes do [set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="b960b-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="b960b-154">Para aplicar a configuração de política que você criou a um usuário em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="b960b-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="b960b-155">Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="b960b-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="b960b-156">Remover uma política de ID de chamadas</span><span class="sxs-lookup"><span data-stu-id="b960b-156">Remove a caller ID policy</span></span>

<span data-ttu-id="b960b-157">Para remover uma política da sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="b960b-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="b960b-158">Para remover uma política de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="b960b-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b960b-159">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b960b-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b960b-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="b960b-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b960b-163">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b960b-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b960b-164">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Office 365</span><span class="sxs-lookup"><span data-stu-id="b960b-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="b960b-p109">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b960b-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b960b-167">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b960b-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b960b-168">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b960b-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b960b-169">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b960b-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="b960b-170">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b960b-170">Related topics</span></span>
[<span data-ttu-id="b960b-171">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="b960b-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="b960b-172">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="b960b-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="b960b-173">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="b960b-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="b960b-174">Mais informações sobre a Identificação de linha da chamada e o nome do chamador</span><span class="sxs-lookup"><span data-stu-id="b960b-174">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="b960b-175">Termos e condições para chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="b960b-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="b960b-176">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="b960b-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
