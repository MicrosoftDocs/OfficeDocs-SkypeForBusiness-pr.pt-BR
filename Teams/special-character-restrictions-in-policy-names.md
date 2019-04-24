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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Consulte quais problemas que existem com caracteres especiais nos nomes de políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: 40cf70b61c8e939c2a1096825e83c676083b9950
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204526"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="15a16-103">Quais são as restrições de caracteres especiais nas políticas do Teams?</span><span class="sxs-lookup"><span data-stu-id="15a16-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="15a16-104">**Não é possível criar ou editar diretivas (para mensagens, reuniões, etc.) que possuem um caractere especial no nome de usuário na administração do Microsoft equipes center**.</span><span class="sxs-lookup"><span data-stu-id="15a16-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="15a16-105">Se um nome de política contiver caracteres especiais, você será limitada no gerenciamento essas diretivas no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="15a16-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="15a16-106">**Sendo assim, é altamente recomendável que os nomes de política não incluem caracteres especiais**.</span><span class="sxs-lookup"><span data-stu-id="15a16-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="15a16-107">Nomes de política que foram criados usando o PowerShell para reuniões e equipes de mensagens podem ter caracteres especiais, como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="15a16-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="15a16-108">No entanto, se você estiver buscando fazer alterações à política no Centro de administração do Microsoft Teams, você não conseguirá.</span><span class="sxs-lookup"><span data-stu-id="15a16-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="15a16-109">Se você tiver uma diretiva com caracteres especiais, você precisará editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no Centro de administração do Microsoft Teams com as mesmas configurações como a diretiva old e atribuí-lo ao mesmo grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="15a16-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="15a16-110">Para remover caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="15a16-110">To remove special characters</span></span>

<span data-ttu-id="15a16-111">**Etapa 1 - fazer uma conexão remota com o PowerShell.** 
 [Configurar seu computador para o Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , se ainda não o fez.</span><span class="sxs-lookup"><span data-stu-id="15a16-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="15a16-112">**Etapa 2 - Obtenha as configurações para a diretiva old e capturar a saída.**</span><span class="sxs-lookup"><span data-stu-id="15a16-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="15a16-113">Este exemplo é para uma política de [mensagens](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="15a16-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="15a16-114">As etapas que podem ser as mesmas para outros tipos de política, mas você deve usar o cmdlet correto.</span><span class="sxs-lookup"><span data-stu-id="15a16-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="15a16-115">**Etapa 3: criar uma nova política.**</span><span class="sxs-lookup"><span data-stu-id="15a16-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="15a16-116">Você pode criar a nova política com a mesma configuração usando o Centro de administração do Microsoft Teams ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15a16-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="15a16-117">Executando isso criará uma nova política para você, mas você precisará adicionar as configurações corretas vendo [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e, em seguida, executá-lo:</span><span class="sxs-lookup"><span data-stu-id="15a16-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="15a16-118">**Etapa 4 - atribuir a política.**</span><span class="sxs-lookup"><span data-stu-id="15a16-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="15a16-119">Consulte, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15a16-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="15a16-120">**Etapa 5 - excluir a diretiva old.**</span><span class="sxs-lookup"><span data-stu-id="15a16-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="15a16-121">Isso excluirá a diretiva old com os caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="15a16-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="15a16-122">Consulte, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15a16-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="15a16-123">Se este comando for bem-sucedido, terminar.</span><span class="sxs-lookup"><span data-stu-id="15a16-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="15a16-124">Se o comando acima retornará um erro, é porque a diretiva old é atribuída a usuários e, portanto, você precisará executar para remover todos os usuários atribuídos da diretiva:</span><span class="sxs-lookup"><span data-stu-id="15a16-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="15a16-125">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="15a16-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="15a16-p105">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="15a16-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="15a16-129">Por que você precisa usar o PowerShell do Office 365?</span><span class="sxs-lookup"><span data-stu-id="15a16-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="15a16-130">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15a16-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="15a16-131">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="15a16-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="15a16-132">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="15a16-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="15a16-133">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="15a16-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="15a16-134">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="15a16-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="15a16-135">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="15a16-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="15a16-136">O módulo do Windows PowerShell para Skype para Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype para Business Online e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15a16-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="15a16-137">Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="15a16-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

