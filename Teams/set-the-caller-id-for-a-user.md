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
description: Saiba mais sobre o recurso de identificação de chamadas padrão do Office 365 (um número de telefone atribuído a um usuário), também conhecido como identificação da linha de chamada. Você pode alterar ou bloquear o recurso de identificação de chamadas de um usuário.
ms.openlocfilehash: c04fdfa7dc395f31eb3277fe0ab2f77aa92605c7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140904"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="33f83-104">Definir a identificação de chamadas para um usuário</span><span class="sxs-lookup"><span data-stu-id="33f83-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="33f83-105">O sistema telefônico no Office 365 fornece uma ID de chamada padrão que é o número de telefone atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="33f83-105">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="33f83-106">Você pode alterar ou bloquear a ID de chamadas (também chamada de ID da linha de chamada) de um usuário.</span><span class="sxs-lookup"><span data-stu-id="33f83-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="33f83-107">Você pode saber mais sobre como usar o recurso de identificação de chamadas em sua organização, indo [como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="33f83-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="33f83-108">Você não pode bloquear as chamadas recebidas atualmente no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="33f83-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="33f83-109">Há duas configurações que você pode alterar:</span><span class="sxs-lookup"><span data-stu-id="33f83-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="33f83-110">[!OBSERVAçãO] Isso **não é** para organizações locais com o Lync ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="33f83-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="33f83-p103">**Mudar a ID de chamadas de saída** Você pode substituir a ID de chamadas de um usuário (que, por padrão, é seu número de telefone) por outro número de telefone. Por exemplo, você pode mudar a ID de chamadas do usuário de seu número de telefone para o número de telefone principal de sua empresa ou alterar a ID de Linha de Chamada do usuário de seu número de telefone para o número de telefone principal do departamento jurídico. Você pode mudar o número de ID de chamadas para o número de qualquer **serviço** online (chamada tarifada ou gratuita).</span><span class="sxs-lookup"><span data-stu-id="33f83-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33f83-114">[!OBSERVAçãO] Se você desejar usar o parâmetro  _Service_, especifique um número de serviço válido.</span><span class="sxs-lookup"><span data-stu-id="33f83-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="33f83-115">**Bloquear a identificação de chamadas de saída** Você pode impedir que a identificação de chamadas de saída seja enviada nas chamadas PSTN de um usuário.</span><span class="sxs-lookup"><span data-stu-id="33f83-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="33f83-116">Isso impede que o número de telefone seja exibido no telefone da pessoa que está sendo chamada.</span><span class="sxs-lookup"><span data-stu-id="33f83-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="33f83-117">**Bloquear a identificação de chamadas de entrada** Você pode impedir que um usuário receba a identificação de chamadas em chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="33f83-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="33f83-118">[!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas).</span><span class="sxs-lookup"><span data-stu-id="33f83-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="33f83-p105">Por padrão, essas configurações de ID de chamadas são **desativadas**. Isso significa que o número de telefone do usuário do Skype for Business Online pode ser visto quando o usuário faz uma chamada para um telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="33f83-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="33f83-121">Para saber mais sobre essas configurações e como você pode usá-las, clique [Como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="33f83-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="33f83-122">Definir as configurações de política de ID de chamadas</span><span class="sxs-lookup"><span data-stu-id="33f83-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="33f83-123">Para todas as configurações de identificação de chamadas no Skype for Business Online, você deve usar o Windows PowerShell e **não pode usar** o **centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="33f83-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="33f83-124">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33f83-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="33f83-125">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="33f83-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="33f83-126">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="33f83-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="33f83-127">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="33f83-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="33f83-128">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33f83-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="33f83-129">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="33f83-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="33f83-130">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="33f83-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="33f83-p107">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="33f83-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="33f83-134">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="33f83-134">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="33f83-135">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="33f83-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="33f83-136">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="33f83-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="33f83-137">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="33f83-137">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="33f83-138">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="33f83-138">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="33f83-139">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="33f83-139">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="33f83-140">Veja todas as configurações de ID de chamadas em sua organização</span><span class="sxs-lookup"><span data-stu-id="33f83-140">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="33f83-141">Para ver todas as configurações de política de identificação de chamadas em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="33f83-141">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="33f83-142">Veja mais exemplos e detalhes do [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="33f83-142">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="33f83-143">Criar uma nova política de ID de chamadas para sua organização</span><span class="sxs-lookup"><span data-stu-id="33f83-143">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="33f83-144">Para criar uma nova política de identificação de chamadas que defina a identificação de chamadas como anônima, execute:</span><span class="sxs-lookup"><span data-stu-id="33f83-144">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="33f83-145">Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.</span><span class="sxs-lookup"><span data-stu-id="33f83-145">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="33f83-146">Veja mais exemplos e detalhes do [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="33f83-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="33f83-147">Para aplicar a nova política criada para o Marble Amos, execute:</span><span class="sxs-lookup"><span data-stu-id="33f83-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="33f83-148">Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="33f83-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="33f83-149">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="33f83-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="33f83-150">Defina a política para que a ID de chamadas de entrada seja bloqueada</span><span class="sxs-lookup"><span data-stu-id="33f83-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="33f83-151">Para bloquear a identificação de chamadas de entrada, execute:</span><span class="sxs-lookup"><span data-stu-id="33f83-151">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="33f83-152">Veja mais exemplos e detalhes do [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="33f83-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="33f83-153">Para aplicar a configuração de política que você criou a um usuário em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="33f83-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="33f83-154">Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="33f83-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="33f83-155">Remover uma política de ID de chamadas</span><span class="sxs-lookup"><span data-stu-id="33f83-155">Remove a caller ID policy</span></span>

<span data-ttu-id="33f83-156">Para remover uma política da sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="33f83-156">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="33f83-157">Para remover uma política de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="33f83-157">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="33f83-158">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="33f83-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="33f83-159">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="33f83-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="33f83-160">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="33f83-160">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="33f83-161">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="33f83-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="33f83-162">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="33f83-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="33f83-163">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Office 365</span><span class="sxs-lookup"><span data-stu-id="33f83-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="33f83-164">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="33f83-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="33f83-165">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="33f83-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="33f83-166">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33f83-166">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="33f83-167">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="33f83-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="33f83-168">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="33f83-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="33f83-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="33f83-169">Related topics</span></span>
[<span data-ttu-id="33f83-170">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="33f83-170">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="33f83-171">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="33f83-171">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="33f83-172">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="33f83-172">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="33f83-173">Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador</span><span class="sxs-lookup"><span data-stu-id="33f83-173">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="33f83-174">Termos e condições para chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="33f83-174">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="33f83-175">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="33f83-175">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
