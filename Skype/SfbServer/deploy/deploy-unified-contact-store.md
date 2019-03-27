---
title: 'Implantar o armazenamento unificado de contatos no Skype para Business Server '
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumo: Habilite o repositório unificado de contatos no Skype para Business Server.'
ms.openlocfilehash: 5e7fb34d03459be5066d154e89fa8e27dc060757
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882562"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="e15ca-103">Implantar o armazenamento unificado de contatos no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e15ca-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="e15ca-104">**Resumo:** Habilite o repositório unificado de contatos no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e15ca-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="e15ca-105">Habilitar o repositório unificado de contatos no Skype para Business Server não exige qualquer configuração de topologia.</span><span class="sxs-lookup"><span data-stu-id="e15ca-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="e15ca-106">Para habilitar o repositório unificado de contatos para os usuários é necessário:</span><span class="sxs-lookup"><span data-stu-id="e15ca-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="e15ca-107">Que a política do repositório unificado de contatos esteja habilitada (ela é habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="e15ca-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="e15ca-108">Os usuários fazer logon com Skype para negócios pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="e15ca-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="e15ca-109">Depois que contatos um usuário foram migrados, que ocorre automaticamente quando um usuário fizer com Skype para os negócios, o usuário pode acessar e gerenciar seu Skype para contatos comerciais do Skype para negócios, Outlook 2013 ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="e15ca-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="e15ca-110">O usuário não precisa estar conectado ao Skype for Business gerenciar seus contatos do Outlook ou o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="e15ca-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e15ca-111">Se um usuário fizer logon de Skype para negócios após a migração, contatos e grupos disponíveis e atualizadas, mas o usuário não pode gerenciar (isto é, adicionar, excluir, mover, marca, quando você formatação ou modificar) esses contatos.</span><span class="sxs-lookup"><span data-stu-id="e15ca-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="e15ca-112">Habilitar usuários para repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="e15ca-112">Enable users for unified contact store</span></span>

<span data-ttu-id="e15ca-113">Quando você implantar Skype para Business Server e publica a topologia, o armazenamento unificado de contatos está habilitado para todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="e15ca-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="e15ca-114">Você não precisará executar qualquer ação adicional para permitir o armazenamento de contato unificado após a implantação do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e15ca-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="e15ca-115">Contudo, você pode usar o cmdlet **Set-CsUserServicesPolicy** para definir quais usuários têm o repositório unificado de contatos disponível.</span><span class="sxs-lookup"><span data-stu-id="e15ca-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="e15ca-116">Você pode habilitar esse recurso globalmente, por local, por locatário ou por indivíduos ou grupos de indivíduos.</span><span class="sxs-lookup"><span data-stu-id="e15ca-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="e15ca-117">Para permitir o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="e15ca-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="e15ca-118">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique **Skype para negócios**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="e15ca-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e15ca-119">Execute qualquer uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e15ca-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="e15ca-120">Para habilitar o armazenamento unificado de contatos globalmente para todos os Skype para usuários corporativos Server, inter o seguinte cmdlet na interface de linha de comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e15ca-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="e15ca-121">Para permitir o repositório unificado de contatos para os usuários em um local específico, digite no prompt:</span><span class="sxs-lookup"><span data-stu-id="e15ca-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="e15ca-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e15ca-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="e15ca-123">Para permitir o repositório unificado de contatos por locatário, digite no prompt:</span><span class="sxs-lookup"><span data-stu-id="e15ca-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="e15ca-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e15ca-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="e15ca-125">Para permitir o repositório unificado de contatos para usuários específicos, digite no prompt:</span><span class="sxs-lookup"><span data-stu-id="e15ca-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="e15ca-126">Você também pode alterar o URI do SIP ou o usuário remoto em vez do nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="e15ca-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="e15ca-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e15ca-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="e15ca-128">No exemplo anterior, o primeiro comando cria uma nova política por usuário chamada Usuários do UCS Permitidos, com o sinalizador AcsAllowed definido como True.</span><span class="sxs-lookup"><span data-stu-id="e15ca-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="e15ca-129">O segundo comando atribui a política ao usuário com o nome Ken Myer, o que significa que Ken Myer está habilitado para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="e15ca-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="e15ca-130">Migrar usuários para o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="e15ca-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="e15ca-131">Contatos do usuário são migrados automaticamente para o servidor Exchange 2013 quando o usuário:</span><span class="sxs-lookup"><span data-stu-id="e15ca-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="e15ca-132">For atribuído com uma política de serviços do usuário com UcsAllowed definido para True.</span><span class="sxs-lookup"><span data-stu-id="e15ca-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="e15ca-133">Tenha sido provisionado com uma caixa de correio do Exchange 2013 e tiver entrado na caixa de correio pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="e15ca-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="e15ca-134">Faça o login usando um Skype para clientes avançados de negócios.</span><span class="sxs-lookup"><span data-stu-id="e15ca-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="e15ca-135">Se o usuário fizer logon com um cliente anterior ou o Lync, ou se o usuário não estiver conectado a um servidor Exchange 2013, a política de serviços do usuário será ignorada e os contatos do usuário permanecem no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e15ca-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="e15ca-136">É possível determinar se os contatos do usuário foram migrados usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="e15ca-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="e15ca-137">Verifique a chave do registro no computador cliente:</span><span class="sxs-lookup"><span data-stu-id="e15ca-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="e15ca-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="e15ca-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="e15ca-139">Se os contatos do usuário são armazenados no Exchange 2013, essa chave contém um valor do InUCSMode de 2165.</span><span class="sxs-lookup"><span data-stu-id="e15ca-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="e15ca-140">Execute o cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="e15ca-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="e15ca-141">No Skype para a linha de comando do Shell de gerenciamento do servidor de negócios, digite:</span><span class="sxs-lookup"><span data-stu-id="e15ca-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="e15ca-142">Se o **Test-CsUnifiedContactStore** tiver êxito, os contatos do usuário foram migrados para o repositório de contatos unificados.</span><span class="sxs-lookup"><span data-stu-id="e15ca-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="e15ca-143">Reversão de Usuários Migrados</span><span class="sxs-lookup"><span data-stu-id="e15ca-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="e15ca-144">Se você precisar reverter o contato unificado armazenar recurso, reverter os contatos somente se você mover o usuário de volta para o Exchange 2010 ou o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e15ca-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="e15ca-145">Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="e15ca-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="e15ca-146">Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e15ca-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="e15ca-147">Por exemplo, se um usuário é revertido porque Exchange 2013 será revertida para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do repositório unificado de contatos será iniciada novamente sete dias após a reversão, desde que o repositório de contato unificado ainda está habilitado para o usuário na política de serviços de usuário.</span><span class="sxs-lookup"><span data-stu-id="e15ca-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="e15ca-148">O cmdlet **Move-CsUser** automaticamente reverte o repositório de contatos do usuário do Exchange 2013 para Skype para Business Server nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="e15ca-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="e15ca-149">Quando os usuários são movidos do Skype para Business Server para Microsoft Lync Server 2013 ou o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e15ca-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="e15ca-150">Quando os usuários são migrados entre locais, como quando um usuário é movido do Skype para Business Online para Skype para Business Server local, ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e15ca-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="e15ca-p107">Importar os dados do repositório de contato unificado de um banco de dados de backup pode fazer com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e15ca-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="e15ca-153">Se você exportar listas de contato antes de contatos dos usuários são migrados para o Exchange 2013 e em seguida, após a migração, importe os mesmos dados, os dados do repositório unificado de contatos e as listas de contatos serão corrompidas.</span><span class="sxs-lookup"><span data-stu-id="e15ca-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="e15ca-154">Se você exportar os dados do usuário depois de migrar os usuários para o Exchange 2013, reverter a migração e, em seguida, por algum motivo você importar os dados de após a migração, o contato unificado armazenar dados e listas de contatos serão corrompidas.</span><span class="sxs-lookup"><span data-stu-id="e15ca-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="e15ca-155">Antes de mover uma caixa de correio do Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve Certifique-se de que o Skype para o administrador do servidor de negócios tem primeiro revertida o Skype para contatos do usuário de servidor de negócios do Exchange 2013 para Skype para Servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e15ca-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="e15ca-156">Para reverter os contatos de repositório unificado de contatos para Skype para Business Server, consulte o procedimento "para reverter os contatos de repositório unificado de contatos do Exchange 2013 para Skype para Business Server," mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="e15ca-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="e15ca-157">**Como reverter contatos do usuário:** Se você usar o cmdlet **Move-CsUser** para mover usuários entre Skype para Business Server 2015 e o Lync Server 2010, pule essas etapas porque o cmdlet **Move-CsUser** automaticamente reverte repositório unificado de contatos quando ele se move os usuários do Skype para 2015 comerciais de servidor para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e15ca-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="e15ca-158">**Move-CsUser** não desabilite a política do repositório unificado de contatos, para que a migração para o armazenamento unificado de contatos será executado se o usuário é movido para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e15ca-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

