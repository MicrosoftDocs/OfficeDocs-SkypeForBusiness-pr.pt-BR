---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed93912b62e323186a902fb717548c16b405299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="e2cfa-102">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="e2cfa-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2cfa-103">_**Tópico da última modificação:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e2cfa-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e2cfa-104">Ao executar o cmdlet **move-CsUser** , você pode enfrentar uma falha porque as informações do usuário entre os serviços de domínio Active Directory (AD DS) e os bancos de dados do Lync Server 2013 estão fora de sincronia porque a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="e2cfa-105">O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Lync Server 2013 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="e2cfa-106">O processo de sincronização inicial do serviço Duplicador de usuários do Lync Server 2013 ocorre quando o servidor front-end do Lync Server 2013 é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="e2cfa-107">Depois disso, a sincronização é baseada no intervalo de Duplicador do usuário.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="e2cfa-108">Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="e2cfa-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="e2cfa-109">Para verificar se a replicação do usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="e2cfa-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="e2cfa-110">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e2cfa-111">Clique no menu **Iniciar** e, em seguida, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="e2cfa-112">Insira **eventvwr. exe** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="e2cfa-113">Em Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e selecione Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="e2cfa-114">No painel **ações** , clique em **Filtrar log atual**.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="e2cfa-115">Na lista **fontes de eventos** , clique em **Duplicador de usuários ls**.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="e2cfa-116">Em \*\* \<todas as identificações\> de evento\*\* , insira **30024** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="e2cfa-117">Na lista eventos filtrados, na guia **geral** , procure por uma entrada que declara que a duplicação do usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="e2cfa-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

