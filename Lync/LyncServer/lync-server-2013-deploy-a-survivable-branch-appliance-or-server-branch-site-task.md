---
title: Implantar um aparelho de filial persistente ou uma tarefa do site de filial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a06cbb4322a1e25b24e94140ceeaa4d89a9cd826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="56339-102">Implantar um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefa do site de filial</span><span class="sxs-lookup"><span data-stu-id="56339-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56339-103">_**Última modificação do tópico:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="56339-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="56339-104">Execute um dos dois procedimentos descritos neste tópico no site de filial, depois de concluir com êxito as tarefas de [implantação de um aparelho de filial persistente ou servidor com o Lync Server 2013 – tarefas do site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="56339-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="56339-105">Para executar este procedimento, você deve ser membro do grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="56339-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="56339-106">Para implantar o Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="56339-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="56339-107">A implantação do aparelho de filial persistente está habilitada pelo fornecedor do aparelho de filial persistente através de uma interface de usuário da Web (UI).</span><span class="sxs-lookup"><span data-stu-id="56339-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="56339-108">Para obter informações sobre como implantar o aparelho de filial persistente, consulte sua documentação de fornecedor de aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="56339-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="56339-109">Para implantar o Servidor da Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="56339-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="56339-110">Instale o Lync Server 2013 em um computador executando o Windows Server 2008 R2, o Windows Server 2012 ou o Windows Server 2012 R2, da mesma forma que você instalaria qualquer outra função de servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56339-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="56339-111">Para obter informações sobre como instalar o Lync Server, consulte <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="56339-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="56339-112">**Próxima etapa**: [Configurando usuários para resiliência de site de filial no Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="56339-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56339-113">Confira Também</span><span class="sxs-lookup"><span data-stu-id="56339-113">See Also</span></span>


[<span data-ttu-id="56339-114">Apêndice A: usando cmdlets para implantar um aparelho de filial persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56339-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

