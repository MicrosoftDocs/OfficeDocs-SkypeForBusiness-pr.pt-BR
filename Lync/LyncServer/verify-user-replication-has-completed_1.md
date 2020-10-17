---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51ff7889b97a58298256cc1a1de3a5d4f901608
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517998"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="b8101-102">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="b8101-102">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8101-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b8101-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b8101-104">Ao executar o cmdlet **move-CsLegacyUser** , você pode ter uma falha devido às informações do usuário entre o AD DS (serviços de domínio Active Directory) e os bancos de dados do Lync Server 2013 que estão fora de sincronia porque a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="b8101-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="b8101-105">O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Lync Server 2013 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8101-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="b8101-106">O processo de sincronização inicial do serviço replicador de usuários do Lync Server 2013 ocorre quando o servidor front-end do Lync Server 2013 é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="b8101-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="b8101-107">Depois disso, a sincronização se baseia no intervalo do Replicador de Usuário.</span><span class="sxs-lookup"><span data-stu-id="b8101-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="b8101-108">Complete os passos a seguir para verificar que a replicação de usuário foi concluída antes de executar o cmdlet **Move-CsLegacyUser**.</span><span class="sxs-lookup"><span data-stu-id="b8101-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="b8101-109">Para verificar que a replicação de usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="b8101-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="b8101-110">No servidor front-end do Lync Server 2013, clique no menu **Iniciar** e em **executar**.</span><span class="sxs-lookup"><span data-stu-id="b8101-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="b8101-111">Insira **eventvwr.exe** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8101-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="b8101-112">No Visualizador de Eventos, clique em **Logs de Aplicativos e Serviços** para expandir e selecione Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8101-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="b8101-113">No painel **Ações**, clique em **Filtrar Log Atual**.</span><span class="sxs-lookup"><span data-stu-id="b8101-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="b8101-114">Na lista **Fontes de evento**, clique em **Replicador de Usuário LS**.</span><span class="sxs-lookup"><span data-stu-id="b8101-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="b8101-115">Em **\<All Event IDs\>** digite **30024** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8101-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="b8101-116">Na lista de eventos filtrados, na guia **Geral**, procure uma entrada que afirma que a replicação de usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="b8101-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

