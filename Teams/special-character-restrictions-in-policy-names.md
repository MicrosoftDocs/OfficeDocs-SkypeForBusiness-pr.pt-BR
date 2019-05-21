---
title: Quais são as restrições de caracteres especiais nas políticas do Teams?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Veja quais são os problemas que há caracteres especiais nos nomes das políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: 03858de420cf77f8a8088f86c8c5feae5828c21a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298598"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="c32a2-103">Quais são as restrições de caracteres especiais nas políticas do Teams?</span><span class="sxs-lookup"><span data-stu-id="c32a2-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="c32a2-104">**Você não pode criar ou editar políticas (para mensagens, reuniões etc.) que tenham um caractere especial no nome do centro de administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="c32a2-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="c32a2-105">Se um nome de política contiver caracteres especiais, você será limitado ao gerenciamento dessas políticas no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c32a2-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c32a2-106">**Assim, recomendamos enfaticamente que os nomes das políticas não incluam caracteres especiais**.</span><span class="sxs-lookup"><span data-stu-id="c32a2-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="c32a2-107">Os nomes de política que foram criados usando o PowerShell para reuniões e mensagens no Microsoft Teams podem ter caracteres especiais, como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="c32a2-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="c32a2-108">No entanto, se você quiser fazer alterações na política no centro de administração do Microsoft Teams, não será possível.</span><span class="sxs-lookup"><span data-stu-id="c32a2-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="c32a2-109">Se você tiver uma política com caracteres especiais, será necessário editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no centro de administração do Microsoft Teams com as mesmas configurações da política antiga e atribuí-la ao mesmo grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="c32a2-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="c32a2-110">Para remover caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="c32a2-110">To remove special characters</span></span>

<span data-ttu-id="c32a2-111">**Etapa 1-fazer uma conexão remota com o PowerShell.** 
 [Configure seu computador para Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , se ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="c32a2-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="c32a2-112">**Etapa 2: obter as configurações da política antiga e capturar a saída.**</span><span class="sxs-lookup"><span data-stu-id="c32a2-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="c32a2-113">Este exemplo é para uma política de [mensagens](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c32a2-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="c32a2-114">As etapas seriam iguais para outros tipos de política, mas você deve usar o cmdlet correto.</span><span class="sxs-lookup"><span data-stu-id="c32a2-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="c32a2-115">**Etapa 3: criar uma nova política.**</span><span class="sxs-lookup"><span data-stu-id="c32a2-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="c32a2-116">Você pode criar uma nova política com a mesma configuração usando o centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c32a2-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="c32a2-117">Executar isso criará uma nova política para você, mas você precisará adicionar as configurações corretas vendo [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e, em seguida, executá-lo:</span><span class="sxs-lookup"><span data-stu-id="c32a2-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="c32a2-118">**Etapa 4-atribuir a política.**</span><span class="sxs-lookup"><span data-stu-id="c32a2-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="c32a2-119">Consulte [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c32a2-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="c32a2-120">**Etapa 5-excluir a política antiga.**</span><span class="sxs-lookup"><span data-stu-id="c32a2-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="c32a2-121">Isso excluirá a política antiga com os caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="c32a2-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="c32a2-122">Consulte [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c32a2-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="c32a2-123">Se esse comando tiver êxito, você terminou.</span><span class="sxs-lookup"><span data-stu-id="c32a2-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="c32a2-124">Se o comando acima retornar um erro, é porque a antiga política é atribuída aos usuários, portanto, você precisa executar para remover todos os usuários atribuídos da política:</span><span class="sxs-lookup"><span data-stu-id="c32a2-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c32a2-125">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c32a2-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="c32a2-p105">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c32a2-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c32a2-129">Por que você precisa usar o PowerShell do Office 365?</span><span class="sxs-lookup"><span data-stu-id="c32a2-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c32a2-130">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c32a2-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c32a2-131">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configurações para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="c32a2-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="c32a2-132">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c32a2-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c32a2-133">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c32a2-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="c32a2-134">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c32a2-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c32a2-135">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c32a2-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c32a2-136">O módulo do Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online e ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c32a2-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="c32a2-137">Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="c32a2-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

