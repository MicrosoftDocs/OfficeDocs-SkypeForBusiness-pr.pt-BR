---
title: 'Lync Server 2013: reverter usuários migrados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbc2c46b462ec50c1f5796a9a6a03cd39f7b44dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="a7eb9-102">Reverter usuários migrados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7eb9-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7eb9-103">_**Última modificação do tópico:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="a7eb9-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="a7eb9-104">Se você precisar reverter o recurso de repositório unificado de contatos, reverta os contatos apenas se mover o usuário de volta para o Exchange 2010 ou o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="a7eb9-105">Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="a7eb9-106">Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="a7eb9-107">Por exemplo, se um usuário for revertido porque o Exchange 2013 é revertido para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do repositório unificado de contatos será iniciada novamente sete dias após a reversão, contanto que o repositório unificado de contatos o ainda está habilitado para o usuário na política de serviços de usuário.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a7eb9-108">O cmdlet <STRONG>move-CsUser</STRONG> reverte automaticamente o repositório de contato do usuário do Exchange 2013 para o Lync Server 2013 nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a7eb9-109">Quando os usuários são movidos do Lync Server 2013 para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="a7eb9-110">Quando os usuários são migrados entre locais, como quando um usuário é movido do Lync Online para o Lync Server 2013 local ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a7eb9-p102">Importar os dados do repositório de contato unificado de um banco de dados de backup pode causar com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a7eb9-113">Se você exportar as listas de contatos antes que os contatos dos usuários sejam migrados para o Exchange 2013 e, após a migração, importar os mesmos dados, os dados do repositório de contato unificado e as listas de contatos serão corrompidos.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="a7eb9-114">Se você exportar UserData após migrar usuários para o Exchange 2013, reverter a migração e, por algum motivo, importar os dados de após a migração, os dados do repositório de contato unificado e as listas de contatos serão corrompidos.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a7eb9-115">Antes de mover uma caixa de correio do Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve garantir que o administrador do Lync Server primeiro tenha revertido os contatos do usuário do Lync Server do Exchange 2013 para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="a7eb9-116">Para reverter os contatos do repositório unificado de contatos para o Lync Server, consulte Procedure "para reverter os contatos do repositório unificado de contatos do Exchange 2013 para o Lync Server 2013", mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="a7eb9-117">O seguinte procedimento descreve como reverter contatos do usuário.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="a7eb9-118">Se você usar o cmdlet **move-CsUser** para mover os usuários entre o lync Server 2013 e o lync Server 2010, é possível ignorar essas etapas porque o cmdlet **move-CsUser** automaticamente é revertido unifed o repositório de contatos quando move os usuários do Lync Server 2013 para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="a7eb9-119">O **move-CsUser** não desabilita a política de repositório unificado de contatos, portanto, a migração para o repositório unificado de contatos será recorrente se o usuário for transferido de volta para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="a7eb9-120">Para reverter os contatos do usuário do Lync Server 2013 para o Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a7eb9-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="a7eb9-121">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a7eb9-p105">Desabilite o repositório de contato unificado para os usuários serem revertidos se eles não irão ser migrados novamente após a reversão. (Realize esta etapa apenas se desejar garantir que os usuários não serão migrados novamente no futuro.) Para desabilitar o repositório de contato unificado para usuários individuais, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="a7eb9-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="a7eb9-125">Antes de mover um usuário do Lync Server 2013 para o Lync Server 2010, reverta a lista de amigos para os usuários especificados no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7eb9-126">Se esta etapa é omitida, a Lista de Amigos será perdida.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="a7eb9-p106">Reverta os usuários especificados. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="a7eb9-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7eb9-p107">Não recomendamos usar a opção –Force para forçar a reversão. Se você usar esta opção, os contatos do usuário serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="a7eb9-132">Para reverter os contatos do repositório unificado de contatos do Exchange 2013 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7eb9-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="a7eb9-133">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a7eb9-p108">Desabilitar o repositório de contato unificado para que os usuários sejam revertidos de forma que eles não serão migrados novamente após a reversão. Para desabilitar o repositório de contato unificado de usuários individuais, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="a7eb9-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="a7eb9-p109">Reverta os usuários especificados. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="a7eb9-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7eb9-140">Primeiro, você deve reverter o usuário do Lync Server e, em seguida, mover a caixa de correio do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="a7eb9-141">O administrador do Exchange é impedido de reverter o Exchange até que a reversão do Lync Server esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="a7eb9-142">Não recomendamos usar a opção –Force para forçar a reversão.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="a7eb9-143">Se você usar esta opção, os contatos do usuário serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="a7eb9-144">Após reverter o usuário para o Lync Server, o administrador do Exchange pode reverter o usuário do Exchange do Exchange 2013 para o Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

