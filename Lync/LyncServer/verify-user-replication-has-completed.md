---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d883b5446c843ac8b79e2b29d15f8a1c99f0089
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="21f53-102">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="21f53-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21f53-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="21f53-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="21f53-104">Ao executar o cmdlet **move-CsUser** , você pode ter uma falha porque as informações do usuário entre os serviços de domínio do Active Directory (AD DS) e os bancos de dados do Lync Server 2013 estão fora de sincronia porque a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="21f53-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="21f53-105">O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Lync Server 2013 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21f53-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="21f53-106">O processo de sincronização inicial do serviço replicador de usuários do Lync Server 2013 ocorre quando o servidor front-end do Lync Server 2013 é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="21f53-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="21f53-107">Depois disso, a sincronização se baseia no intervalo do User Replicator.</span><span class="sxs-lookup"><span data-stu-id="21f53-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="21f53-108">Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="21f53-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="21f53-109">Para verificar se a replicação de usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="21f53-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="21f53-110">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="21f53-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="21f53-111">Clique no menu **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="21f53-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="21f53-112">Insira **eventvwr.exe** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="21f53-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="21f53-113">No Visualizador de Eventos, clique em **Logs de Aplicativos e Serviços** para expandir e selecione Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21f53-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="21f53-114">No painel **Ações**, clique em **Filtrar Log Atual**.</span><span class="sxs-lookup"><span data-stu-id="21f53-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="21f53-115">Na lista **Fontes de evento**, clique em **Replicador de Usuário LS**.</span><span class="sxs-lookup"><span data-stu-id="21f53-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="21f53-116">Em **\<All Event IDs\>** digite **30024** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="21f53-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="21f53-117">Na lista de eventos filtrados, na guia **Geral**, procure uma entrada que afirma que a replicação de usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="21f53-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

