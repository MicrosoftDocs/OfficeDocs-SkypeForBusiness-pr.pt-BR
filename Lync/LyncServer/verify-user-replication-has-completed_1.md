---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="296d2-102">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="296d2-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="296d2-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="296d2-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="296d2-104">Ao executar o cmdlet **move-CsLegacyUser** , você pode ter uma falha devido a informações do usuário entre os serviços de domínio Active Directory (AD DS), e os bancos de dados do Lync Server 2013 estão fora de sincronia porque a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="296d2-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="296d2-105">O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Lync Server 2013 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="296d2-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="296d2-106">O processo de sincronização inicial do serviço Duplicador de usuários do Lync Server 2013 ocorre quando o servidor front-end do Lync Server 2013 é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="296d2-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="296d2-107">Depois disso, a sincronização é baseada no intervalo de Duplicador do usuário.</span><span class="sxs-lookup"><span data-stu-id="296d2-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="296d2-108">Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet **move-CsLegacyUser** .</span><span class="sxs-lookup"><span data-stu-id="296d2-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="296d2-109">Para verificar se a duplicação do usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="296d2-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="296d2-110">No servidor de front-end do Lync Server 2013, clique no menu **Iniciar** e, em seguida, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="296d2-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="296d2-111">Insira **eventvwr. exe** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="296d2-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="296d2-112">Em Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e selecione Lync Server.</span><span class="sxs-lookup"><span data-stu-id="296d2-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="296d2-113">No painel **ações** , clique em **Filtrar log atual**.</span><span class="sxs-lookup"><span data-stu-id="296d2-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="296d2-114">Na lista **fontes de eventos** , clique em **Duplicador de usuários ls**.</span><span class="sxs-lookup"><span data-stu-id="296d2-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="296d2-115">Em \*\* \<todas as identificações\> de evento\*\* , insira **30024** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="296d2-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="296d2-116">Na lista eventos filtrados, na guia **geral** , procure por uma entrada que declara que a duplicação do usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="296d2-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

