---
title: 'Implantar repositório de contatos unificado no Skype for Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumo: habilite o repositório de contatos unificado no Skype for Business Server.'
ms.openlocfilehash: 6cadba38f40a8ff12501e0fe73f4243dc96a5831
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003061"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="3057f-103">Implantar repositório de contatos unificado no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3057f-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="3057f-104">**Resumo:** Habilite o repositório de contatos unificado no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3057f-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="3057f-105">Habilitar o repositório de contatos unificado no Skype for Business Server não requer nenhuma configuração de topologia.</span><span class="sxs-lookup"><span data-stu-id="3057f-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="3057f-106">Para habilitar o repositório unificado de contatos para os usuários é necessário:</span><span class="sxs-lookup"><span data-stu-id="3057f-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="3057f-107">Que a política do repositório unificado de contatos esteja habilitada (ela é habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="3057f-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="3057f-108">Os usuários fazem logon com o Skype for Business pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="3057f-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="3057f-109">Após a migração dos contatos de um usuário, o que acontece automaticamente quando um usuário faz logon com o Skype for Business, o usuário pode acessar e gerenciar seus contatos do Skype for Business pelo Skype for Business, Outlook 2013 ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3057f-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="3057f-110">O usuário não precisa estar conectado ao Skype for Business para gerenciar seus contatos do Outlook ou do Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3057f-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3057f-111">Se um usuário fizer logon pelo Skype for Business após a migração, os contatos e grupos estarão disponíveis e atualizados, mas o usuário não poderá gerenciar (ou seja, adicionar, excluir, mover, marcar, remover ou modificar) esses contatos.</span><span class="sxs-lookup"><span data-stu-id="3057f-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="3057f-112">Habilitar usuários para repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="3057f-112">Enable users for unified contact store</span></span>

<span data-ttu-id="3057f-113">Quando você implanta o Skype for Business Server e publica a topologia, o repositório de contatos unificado é habilitado para todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="3057f-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="3057f-114">Você não precisa executar nenhuma ação adicional para habilitar o repositório de contatos unificado após a implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3057f-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="3057f-115">Contudo, você pode usar o cmdlet **Set-CsUserServicesPolicy** para definir quais usuários têm o repositório unificado de contatos disponível.</span><span class="sxs-lookup"><span data-stu-id="3057f-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="3057f-116">Você pode habilitar esse recurso globalmente, por local, por locatário ou por indivíduos ou grupos de indivíduos.</span><span class="sxs-lookup"><span data-stu-id="3057f-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="3057f-117">Para permitir o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="3057f-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="3057f-118">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="3057f-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3057f-119">Execute qualquer uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="3057f-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="3057f-120">Para habilitar o repositório de contatos unificado globalmente para todos os usuários do Skype for Business Server, entre o cmdlet a seguir na interface de linha de comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3057f-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="3057f-121">Para permitir o repositório unificado de contatos para os usuários em um local específico, digite no prompt:</span><span class="sxs-lookup"><span data-stu-id="3057f-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="3057f-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3057f-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="3057f-123">Para permitir o repositório unificado de contatos por locatário, digite no prompt:</span><span class="sxs-lookup"><span data-stu-id="3057f-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="3057f-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3057f-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="3057f-125">Para permitir o repositório unificado de contatos para usuários específicos, digite no prompt:</span><span class="sxs-lookup"><span data-stu-id="3057f-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="3057f-126">Você também pode alterar o URI do SIP ou o usuário remoto em vez do nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="3057f-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="3057f-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3057f-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="3057f-128">No exemplo anterior, o primeiro comando cria uma nova política por usuário chamada Usuários do UCS Permitidos, com o sinalizador AcsAllowed definido como True.</span><span class="sxs-lookup"><span data-stu-id="3057f-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="3057f-129">O segundo comando atribui a política ao usuário com o nome Ken Myer, o que significa que Ken Myer está habilitado para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="3057f-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="3057f-130">Migrar usuários para o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="3057f-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="3057f-131">Os contatos de um usuário são migrados automaticamente para o servidor Exchange 2013 quando o usuário:</span><span class="sxs-lookup"><span data-stu-id="3057f-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="3057f-132">For atribuído com uma política de serviços do usuário com UcsAllowed definido para True.</span><span class="sxs-lookup"><span data-stu-id="3057f-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="3057f-133">Foi provisionado com uma caixa de correio do Exchange 2013 e entrou na caixa de correio pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="3057f-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="3057f-134">Conecta-se usando um cliente avançado Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3057f-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="3057f-135">Se o usuário fizer logon com um cliente do Lync ou anterior, ou se o usuário não estiver conectado a um servidor do Exchange 2013, a política de serviços do usuário será ignorada e os contatos do usuário permanecerão no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3057f-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="3057f-136">É possível determinar se os contatos do usuário foram migrados usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="3057f-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="3057f-137">Verifique a chave do registro no computador cliente:</span><span class="sxs-lookup"><span data-stu-id="3057f-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="3057f-138">HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<URL\>SIP \UCS</span><span class="sxs-lookup"><span data-stu-id="3057f-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="3057f-139">Se os contatos do usuário estiverem armazenados no Exchange 2013, essa chave contém um valor de InUCSMode com um valor de 2165.</span><span class="sxs-lookup"><span data-stu-id="3057f-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="3057f-140">Execute o cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="3057f-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="3057f-141">Na linha de comando do Shell de gerenciamento do Skype for Business Server, digite:</span><span class="sxs-lookup"><span data-stu-id="3057f-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="3057f-142">Se o **Test-CsUnifiedContactStore** tiver êxito, os contatos do usuário foram migrados para o repositório de contatos unificados.</span><span class="sxs-lookup"><span data-stu-id="3057f-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="3057f-143">Reversão de Usuários Migrados</span><span class="sxs-lookup"><span data-stu-id="3057f-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="3057f-144">Se você precisar reverter o recurso de repositório de contatos unificado, reverta os contatos apenas se mover o usuário de volta para o Exchange 2010 ou o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3057f-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="3057f-145">Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="3057f-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="3057f-146">Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="3057f-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="3057f-147">Por exemplo, se um usuário for revertido porque o Exchange 2013 é revertido para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do repositório de contatos unificado será iniciada novamente sete dias após a reversão, desde que o repositório de contatos unificado ainda está habilitado para o usuário na política de serviços de usuário.</span><span class="sxs-lookup"><span data-stu-id="3057f-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="3057f-148">O cmdlet **move-CsUser** retorna automaticamente a loja de contatos do usuário do Exchange 2013 para o Skype for Business Server nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="3057f-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="3057f-149">Quando os usuários forem movidos do Skype for Business Server para o Microsoft Lync Server 2013 ou o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3057f-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="3057f-150">Quando os usuários são migrados de forma cruzada, como quando um usuário é movido do Skype for Business online para o Skype for Business Server no local, ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="3057f-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="3057f-p107">Importar os dados do repositório de contato unificado de um banco de dados de backup pode fazer com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3057f-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="3057f-153">Se você exportar listas de contatos antes de os contatos dos usuários serem migrados para o Exchange 2013 e depois, após a migração, importar os mesmos dados, os dados do repositório de contatos unificado e as listas de contatos serão corrompidos.</span><span class="sxs-lookup"><span data-stu-id="3057f-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="3057f-154">Se você exportar dados do usuário depois de migrar os usuários para o Exchange 2013, reverta a migração e, por algum motivo, importar os dados após a migração, os dados do repositório de contatos unificado e as listas de contatos serão corrompidos.</span><span class="sxs-lookup"><span data-stu-id="3057f-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3057f-155">Antes de mover uma caixa de correio do Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve verificar se o administrador do Skype for Business Server primeiro reverteu os contatos do usuário do Skype for Business Server do Exchange 2013 para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3057f-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="3057f-156">Para reverter contatos do repositório de contatos unificados para o Skype for Business Server, consulte procedimento "para reverter contatos do repositório de contatos unificados do Exchange 2013 para o Skype for Business Server", posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="3057f-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="3057f-157">**Como recuperar contatos do usuário:** Se você usar o cmdlet **move-CsUser** para mover os usuários entre o Skype for Business Server 2015 e o Lync Server 2010, poderá ignorar essas etapas porque o cmdlet **move-CsUser** automaticamente recupera o repositório de contatos unificado quando move usuários do Skype for Business Server 2015 para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3057f-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="3057f-158">**Move-CsUser** não desabilita a política de repositório de contatos unificado, portanto, a migração para o repositório de contatos unificado será recorrente se o usuário for movido de volta para o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3057f-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

