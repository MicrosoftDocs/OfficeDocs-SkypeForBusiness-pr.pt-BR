---
title: 'Lync Server 2013: Configurando o Lync Server para usar o repositório unificado de contatos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f913b321d700337d1cb3649c2e1351971b6d7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506248"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="5836b-102">Configurando o Microsoft Lync Server 2013 para usar o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="5836b-102">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5836b-103">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="5836b-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="5836b-104">O repositório unificado de contatos permite que os usuários mantenham uma única lista de contatos e, em seguida, tenham esses contatos disponíveis em vários aplicativos, incluindo o Microsoft Lync 2013, o Microsoft Outlook 2013 e o Microsoft Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="5836b-104">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="5836b-105">Quando você habilita o repositório unificado de contatos para um usuário que os contatos do usuário não são armazenados no Microsoft Lync Server 2013 e recuperados usando o protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="5836b-105">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="5836b-106">Em vez disso, seus contatos são armazenados no Microsoft Exchange Server 2013 e recuperados usando os serviços Web do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5836b-106">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5836b-107">Tecnicamente, as informações de contato são armazenadas em um par de pastas encontradas na caixa de correio do Exchange 2013 do usuário.</span><span class="sxs-lookup"><span data-stu-id="5836b-107">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="5836b-108">Os contatos propriamente ditos são armazenados em uma pasta denominada contatos do Lync, que é visível para os usuários finais; os metadados sobre os contatos são armazenados em uma subpasta que não é visível para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="5836b-108">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="5836b-109">Habilitando o repositório unificado de contatos para um usuário</span><span class="sxs-lookup"><span data-stu-id="5836b-109">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="5836b-110">Se você já configurou a autenticação de servidor para servidor entre o Lync Server 2013 e o Exchange 2013, você também habilitou o uso do repositório unificado de contatos; nenhuma configuração adicional do servidor é necessária.</span><span class="sxs-lookup"><span data-stu-id="5836b-110">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="5836b-111">No entanto, será necessária configuração adicional da conta do usuário para transferir os contatos de um usuário para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-111">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="5836b-112">Por padrão, os contatos do usuário são mantidos no Lync Server e não no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-112">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="5836b-113">O acesso ao repositório unificado de contatos é gerenciado usando políticas de serviços de usuário do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5836b-113">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="5836b-114">As políticas de serviços de usuário têm uma única propriedade (UcsAllowed), que é usada para determinar o local onde os contatos de um usuário são armazenados.</span><span class="sxs-lookup"><span data-stu-id="5836b-114">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="5836b-115">Se um usuário é gerenciado por uma política de serviços de usuário em que o UcsAllowed foi definido como true ($True), os contatos do usuário serão armazenados no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-115">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="5836b-116">Se o usuário for gerenciado por uma política de serviços de usuário em que o UcsAllowed foi definido como false ($False), seus contatos serão armazenados no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5836b-116">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="5836b-117">Quando você instala o Lync Server 2013, uma única política de serviços de usuário (configurada no escopo global) também é instalada.</span><span class="sxs-lookup"><span data-stu-id="5836b-117">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="5836b-118">O valor UcsAllowed nessa política é definido como true, o que significa que, por padrão, os contatos do usuário serão armazenados no repositório unificado de contatos (supondo que isso tenha sido implantado e configurado).</span><span class="sxs-lookup"><span data-stu-id="5836b-118">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="5836b-119">Se você quiser migrar todos os seus contatos de usuário para o repositório unificado de contatos, não será necessário fazer nada.</span><span class="sxs-lookup"><span data-stu-id="5836b-119">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="5836b-120">Se preferir não migrar todos os seus contatos para o repositório unificado de contatos, você poderá desabilitar o repositório unificado de contatos para todos os usuários, definindo a propriedade UcsAllowed na política global como false:</span><span class="sxs-lookup"><span data-stu-id="5836b-120">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="5836b-121">Depois de desabilitar o repositório unificado de contatos na política global, você pode criar uma política por usuário que permite o uso do repositório unificado de contatos; Isso permite que alguns usuários mantenham seus contatos no repositório unificado de contatos enquanto outros usuários continuam a manter seus contatos no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5836b-121">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="5836b-122">Você pode criar uma política de serviços de usuário por usuário usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="5836b-122">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="5836b-p107">Depois que você tiver criado a nova política, precisará atribuí-la aos usuários que deverão ter acesso ao repositório unificado de contatos. As políticas por usuário podem ser atribuídas aos usuários com o uso de comandos semelhantes ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="5836b-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="5836b-125">Depois que a política tiver sido atribuída, o Lync Server começará a migrar os contatos do usuário para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-125">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="5836b-126">Após a conclusão da migração, o usuário terá seus contatos armazenados no Exchange, e não no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5836b-126">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="5836b-127">Se o usuário estiver conectado ao Lync 2013 no momento em que a migração for concluída, uma caixa de mensagem será exibida e ele será solicitado a fazer logoff do Lync e, em seguida, fazer logon novamente para finalizar o processo.</span><span class="sxs-lookup"><span data-stu-id="5836b-127">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="5836b-128">Os usuários que não tiverem sido atribuídos essa política por usuário não terão seus contatos migrados para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-128">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="5836b-129">Isso ocorre porque esses usuários estão sendo gerenciados pela política global e o uso do repositório unificado de contatos foi desabilitado na política global.</span><span class="sxs-lookup"><span data-stu-id="5836b-129">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="5836b-130">Você pode verificar se os contatos de um usuário foram migrados com êxito para o repositório unificado de contatos executando o cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) de dentro do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="5836b-130">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="5836b-131">Se Test-CsUnifiedContactStore for bem-sucedido, significa que os contatos do usuário sip:kenmyer@litwareinc.com foram migrados para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-131">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="5836b-132">Revertendo o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="5836b-132">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="5836b-133">Se você precisar remover os contatos de um usuário do repositório unificado de contatos (por exemplo, se o usuário precisar ser rehospedado no Microsoft Lync Server 2010 e não puder mais usar o repositório unificado de contatos), você deverá fazer duas coisas.</span><span class="sxs-lookup"><span data-stu-id="5836b-133">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="5836b-134">Primeiro, você deve atribuir ao usuário uma nova política de serviços de usuário, que proíba o armazenamento de contatos no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-134">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="5836b-135">(Ou seja, uma política na qual a propriedade UcsAllowed foi definida como $False.) Se você não tem essa política, você pode criar uma usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="5836b-135">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="5836b-136">Em seguida, você pode atribuir essa nova política por usuário (NoUnifiedContactStore) usando um comando como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5836b-136">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="5836b-137">O comando anterior atribui a nova política ao usuário Ken Myer e também impede que os contatos de Ken sejam migrados para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-137">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5836b-p110">Em alguns casos, é possível obter o mesmo efeito simplesmente cancelando a atribuição da política de serviços de usuário atual do usuário. Por exemplo, suponha que Ken Myer tenha uma política de serviços de usuário por usuário que habilita o repositório unificado de contatos, mas sua política global proíbe o uso do repositório unificado de contatos. Nesse caso, você pode cancelar a atribuição da política de serviços por usuário de Ken. Quando você fizer isso, Ken será automaticamente gerenciado pela política global e deixará de ter acesso ao repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-p110">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy. For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store. In that case, you could unassign Ken's per-user services policy. When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="5836b-142">Para cancelar a atribuição de uma política por usuário atribuída anteriormente, use o mesmo comando mostrado antes, mas, desta vez, defina o parâmetro PolicyName para um valor nulo:</span><span class="sxs-lookup"><span data-stu-id="5836b-142">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="5836b-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –NomedaPolítica $Null</span><span class="sxs-lookup"><span data-stu-id="5836b-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="5836b-144">É importante lembrar-se da frase "impede que os contatos de Ken sejam migrados para o repositório unificado de contatos" ao trabalhar com o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-144">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="5836b-145">Simplesmente atribuir uma nova política de serviços de usuário a Ken não removerá seus contatos do repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-145">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="5836b-146">Quando um usuário faz logon no Lync Server 2013, o sistema verifica a política de serviços de usuário do usuário para ver se seus contatos devem ser mantidos no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-146">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="5836b-147">Se a resposta for sim (ou seja, se a propriedade UcsAllowed estiver definida como $True), esses contatos serão migrados para o repositório unificado de contatos (pressupondo que eles ainda não estejam no repositório unificado de contatos).</span><span class="sxs-lookup"><span data-stu-id="5836b-147">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="5836b-148">Se a resposta for não, o Lync Server simplesmente ignora os contatos do usuário e se move para a próxima tarefa.</span><span class="sxs-lookup"><span data-stu-id="5836b-148">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="5836b-149">Isso significa que o Lync Server não moverá automaticamente os contatos de um usuário do repositório unificado de contatos, independentemente do valor da propriedade UcsAllowed.</span><span class="sxs-lookup"><span data-stu-id="5836b-149">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="5836b-150">Isso também significa que, após a atribuição do usuário a uma nova política de serviços de usuário, você deverá executar o cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) para mover os contatos do usuário para fora do Exchange 2013 e de volta para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5836b-150">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="5836b-151">Por exemplo, após atribuir uma nova política de serviços de usuário a Ken Myer, você poderá remover seus contatos do repositório unificado de contatos usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5836b-151">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="5836b-152">Se você alterar a política de serviços de usuário, mas não executar o cmdlet Invoke-CsUcsRollback, os contatos de Ken não serão removidos do repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-152">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="5836b-153">E se você executar o Invoke-CsUcsRollback, mas não alterar a política de serviços de usuário de Ken Myer?</span><span class="sxs-lookup"><span data-stu-id="5836b-153">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="5836b-154">Nesse caso, os contatos de Ken serão temporariamente removidos do repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-154">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="5836b-155">É importante atentar ao fato de que essa remoção é temporária.</span><span class="sxs-lookup"><span data-stu-id="5836b-155">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="5836b-156">Após os contatos de Ken terem sido removidos do repositório unificado de contatos, o Lync Server 2013 aguardará 7 dias e verificará qual política de serviços de usuário foi atribuída a Ken.</span><span class="sxs-lookup"><span data-stu-id="5836b-156">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="5836b-157">Se uma política que permite o uso do repositório unificado de contatos ainda estiver atribuída a Ken, seus contatos serão automaticamente transferidos de volta para o repositório de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-157">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="5836b-158">Para remover permanentemente os contatos do repositório unificado de contatos, você precisa alterar a política de serviços de usuário e também executar o cmdlet Invoke-CsUcsRollback.</span><span class="sxs-lookup"><span data-stu-id="5836b-158">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="5836b-159">Devido ao grande número de variáveis que podem afetar a migração, é difícil estimar quanto tempo levará para que as contas sejam totalmente migradas para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5836b-159">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="5836b-160">No entanto, como regra geral, a migração não tem efeito imediato: mesmo ao migrar um pequeno número de contatos, pode levar 10 minutos ou mais antes da conclusão da movimentação.</span><span class="sxs-lookup"><span data-stu-id="5836b-160">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

