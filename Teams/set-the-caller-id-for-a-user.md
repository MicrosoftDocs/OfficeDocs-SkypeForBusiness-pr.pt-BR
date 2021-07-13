---
title: Definir a identificação de chamadas para um usuário
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Saiba mais sobre o Microsoft 365 e Office 365 ID padrão do chamador (número de telefone atribuído a um usuário), também conhecido como ID de Linha de Chamada. Você pode alterar ou bloquear a ID do chamador do usuário.
ms.openlocfilehash: 2e94dde2c3271e2b31e4c679c5e020c121d28c25
ms.sourcegitcommit: 41e2e97b5856e727e42ebf5bfebceede9af56481
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53388646"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="57a3c-104">Definir a identificação de chamadas para um usuário</span><span class="sxs-lookup"><span data-stu-id="57a3c-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="57a3c-105">Sistema de Telefonia no Microsoft 365 fornece uma ID de chamador padrão que é o número de telefone atribuído pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="57a3c-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="57a3c-106">Você pode alterar ou bloquear a ID de chamadas (também chamada de ID da linha de chamada) de um usuário.</span><span class="sxs-lookup"><span data-stu-id="57a3c-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="57a3c-107">Você pode saber mais sobre como usar a ID do chamador em sua organização, indo Como a ID do chamador pode ser [usada em sua organização.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="57a3c-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="57a3c-108">Por padrão, as configurações de ID do chamador a seguir são **desligadas**.</span><span class="sxs-lookup"><span data-stu-id="57a3c-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="57a3c-109">Isso significa que o Teams de telefone do usuário pode ser visto quando esse usuário faz uma chamada para um telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="57a3c-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="57a3c-110">Você pode alterar essas configurações da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="57a3c-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="57a3c-111">**ID do chamador de saída** Você pode substituir a ID do Chamador do usuário, que por padrão é seu número de telefone, por outro número de telefone.</span><span class="sxs-lookup"><span data-stu-id="57a3c-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="57a3c-112">Por exemplo, você pode alterar a ID do Chamador do usuário de seu número de telefone para um número de telefone principal para sua empresa ou para um número de telefone principal para o departamento jurídico.</span><span class="sxs-lookup"><span data-stu-id="57a3c-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or to a main phone number for the legal department.</span></span> <span data-ttu-id="57a3c-113">Além disso, você pode definir o número de ID de chamada para qualquer número de serviço online (gratuito ou gratuito) ou para um número de telefone local por meio do Roteamento Direto atribuído a uma conta de recurso usada por um Atendedor Automático ou uma Fila de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="57a3c-113">Additionally, you can set the Calling ID number to any online service number (toll or toll-free) or to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or a Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="57a3c-114">Se quiser usar o parâmetro *Service,* especifique um número de serviço válido.</span><span class="sxs-lookup"><span data-stu-id="57a3c-114">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  > <span data-ttu-id="57a3c-115">Você precisa usar os cmdlets do PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity no módulo do Teams PowerShell 2.3.1 ou posterior para o número da conta resource se ele não estiver visível no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="57a3c-115">You need to use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later for the Resource account number if it is not visible in the dropdown.</span></span>
  
- <span data-ttu-id="57a3c-116">**Bloquear a ID do chamador de saída.**</span><span class="sxs-lookup"><span data-stu-id="57a3c-116">**Block outbound caller ID.**</span></span> <span data-ttu-id="57a3c-117">Você pode impedir que a ID do Chamador de saída seja enviada em chamadas PSTN de saída de um usuário.</span><span class="sxs-lookup"><span data-stu-id="57a3c-117">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="57a3c-118">Isso impede que o número de telefone seja exibido no telefone da pessoa que está sendo chamada.</span><span class="sxs-lookup"><span data-stu-id="57a3c-118">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="57a3c-119">**Bloquear a ID do chamador de entrada.**</span><span class="sxs-lookup"><span data-stu-id="57a3c-119">**Block incoming caller ID.**</span></span> <span data-ttu-id="57a3c-120">Você pode impedir que um usuário receba a ID do Chamador em qualquer chamada PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="57a3c-120">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="57a3c-121">**Definir Nome da Parte de Chamada (CNAM).**</span><span class="sxs-lookup"><span data-stu-id="57a3c-121">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="57a3c-122">Para seus Microsoft Teams, você pode enviar um CNAM em chamadas PSTN de saída.</span><span class="sxs-lookup"><span data-stu-id="57a3c-122">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="57a3c-123">[!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas).</span><span class="sxs-lookup"><span data-stu-id="57a3c-123">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="57a3c-124">Para saber mais sobre essas configurações e como usá-las, consulte Como a ID do chamador pode ser [usada em sua organização.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="57a3c-124">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="57a3c-125">Definir as configurações de política de ID de chamadas</span><span class="sxs-lookup"><span data-stu-id="57a3c-125">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="57a3c-126">Para definir a ID do chamador como um número de telefone da conta de recurso e definir o nome da parte de chamada, use os cmdlets do PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity no módulo 2.3.1 do Teams PowerShell ou posterior.</span><span class="sxs-lookup"><span data-stu-id="57a3c-126">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="57a3c-127">(Essas opções não estão disponíveis no Microsoft Teams de administração.)</span><span class="sxs-lookup"><span data-stu-id="57a3c-127">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="57a3c-128">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="57a3c-128">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="57a3c-129">Exibir, criar e aplicar configurações de política</span><span class="sxs-lookup"><span data-stu-id="57a3c-129">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="57a3c-130">Para exibir todas as configurações de política de ID do chamador em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="57a3c-130">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="57a3c-131">Para obter mais informações, [consulte Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="57a3c-131">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="57a3c-132">Para criar uma nova política de ID do chamador para sua organização, use o cmdlet New-CsCallingIdentity de chamada:</span><span class="sxs-lookup"><span data-stu-id="57a3c-132">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="57a3c-133">Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.</span><span class="sxs-lookup"><span data-stu-id="57a3c-133">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="57a3c-134">Para obter mais informações, [consulte New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="57a3c-134">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="57a3c-135">Aplique a nova política criada usando o cmdlet Grant-CsCallingIdentity.</span><span class="sxs-lookup"><span data-stu-id="57a3c-135">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="57a3c-136">Por exemplo, o exemplo a seguir aplica a nova política ao usuário Amos Marble.</span><span class="sxs-lookup"><span data-stu-id="57a3c-136">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="57a3c-137">Para obter mais informações, [consulte Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="57a3c-137">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="57a3c-138">Se você quiser bloquear a ID do chamador de entrada, execute:</span><span class="sxs-lookup"><span data-stu-id="57a3c-138">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="57a3c-139">Para obter mais informações, [consulte Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="57a3c-139">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="57a3c-140">Para aplicar a configuração de política criada a um usuário em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="57a3c-140">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="57a3c-141">Para obter mais informações, [consulte Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="57a3c-141">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="57a3c-142">Para criar uma nova política de ID do Chamador que define a ID do Chamador como o número de telefone da conta de recurso especificada e define o nome da parte de chamada como Contoso:</span><span class="sxs-lookup"><span data-stu-id="57a3c-142">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="57a3c-143">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="57a3c-143">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="57a3c-144">Remover uma configuração de política</span><span class="sxs-lookup"><span data-stu-id="57a3c-144">Remove a policy setting</span></span>

<span data-ttu-id="57a3c-145">Para remover uma política da sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="57a3c-145">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="57a3c-146">Para remover uma política de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="57a3c-146">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="57a3c-147">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="57a3c-147">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="57a3c-148">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="57a3c-148">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="57a3c-149">Com Windows PowerShell, você pode gerenciar Microsoft 365 usando um único ponto de administração que pode simplificar seu trabalho diário.</span><span class="sxs-lookup"><span data-stu-id="57a3c-149">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="57a3c-150">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="57a3c-150">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="57a3c-151">Uma introdução ao Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57a3c-151">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="57a3c-152">Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57a3c-152">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="57a3c-153">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="57a3c-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="57a3c-154">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="57a3c-154">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="57a3c-155">[Melhores maneiras de gerenciar Microsoft 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="57a3c-155">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="57a3c-156">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="57a3c-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="57a3c-157">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="57a3c-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="57a3c-158">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="57a3c-158">Related topics</span></span>
[<span data-ttu-id="57a3c-159">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="57a3c-159">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="57a3c-160">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="57a3c-160">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="57a3c-161">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="57a3c-161">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="57a3c-162">Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador</span><span class="sxs-lookup"><span data-stu-id="57a3c-162">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="57a3c-163">Termos e condições para chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="57a3c-163">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="57a3c-164">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="57a3c-164">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
