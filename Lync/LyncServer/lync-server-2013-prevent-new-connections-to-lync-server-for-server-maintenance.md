---
title: Impedir novas conexões com a manutenção do Lync Server para servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06516c3d47a9ec5e491a5a16098dfae334ff4f4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="bafee-102">Impedir novas conexões com o Lync Server 2013 para manutenção do servidor</span><span class="sxs-lookup"><span data-stu-id="bafee-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bafee-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bafee-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bafee-104">O Lync Server permite que você coloque um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem nenhuma perda de serviço aos usuários.</span><span class="sxs-lookup"><span data-stu-id="bafee-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="bafee-105">Quando você especifica a opção para impedir novas conexões ou chamadas a um servidor em um pool, ele para de aceitar novas conexões e chamadas assim que você implementa essa opção.</span><span class="sxs-lookup"><span data-stu-id="bafee-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="bafee-106">As novas conexões e chamadas são roteadas através de outros servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="bafee-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="bafee-107">Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até terminarem de modo natural.</span><span class="sxs-lookup"><span data-stu-id="bafee-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="bafee-108">Quando todas as sessões existentes são concluídas, o servidor está pronto para ser colocado offline.</span><span class="sxs-lookup"><span data-stu-id="bafee-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="bafee-109">Quando você impede novas conexões a um servidor front-end, alguns recursos e serviços do Lync Server dependem do balanceamento de carga DNS para garantir que funcionem corretamente.</span><span class="sxs-lookup"><span data-stu-id="bafee-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="bafee-110">Se você não estiver usando o balanceamento de carga DNSno pool, as conexões por meio desses serviços poderão não ser redirecionados para outros servidores durante o período no qual o servidor está impedindo novas conexões e, portanto, quando o servidor é colocado offline, algumas sessões e chamadas podem ser interrompidas.</span><span class="sxs-lookup"><span data-stu-id="bafee-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="bafee-111">Estes são os recursos que dependem do balanceamento de carga DNS para garantir que esta opção funcione corretamente:</span><span class="sxs-lookup"><span data-stu-id="bafee-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="bafee-112">Automático</span><span class="sxs-lookup"><span data-stu-id="bafee-112">Attendant</span></span>

  - <span data-ttu-id="bafee-113">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="bafee-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="bafee-114">Aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="bafee-114">Response Group application</span></span>

  - <span data-ttu-id="bafee-115">Aplicativo de comunicado</span><span class="sxs-lookup"><span data-stu-id="bafee-115">Announcement application</span></span>

  - <span data-ttu-id="bafee-116">Call Park application</span><span class="sxs-lookup"><span data-stu-id="bafee-116">Call Park application</span></span>

<span data-ttu-id="bafee-117">Para obter detalhes sobre o balanceamento de carga DNS, consulte [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="bafee-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="bafee-118">Além de impedir novas conexões para todos os serviços em um servidor executando o Lync Server, você também pode impedir novas conexões para serviços individuais do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bafee-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="bafee-119">Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização do Lync Server que não exige o desligamento completo do servidor.</span><span class="sxs-lookup"><span data-stu-id="bafee-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="bafee-120">Observe que, quando você impede conexões com um serviço, deve selecionar um serviço que é agrupado e exibido na lista de serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="bafee-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="bafee-121">Por exemplo, o serviço front-end do Lync Server e o agente de coleta de dados para monitoramento são serviços separados do Lync Server, mas na lista de serviços do Windows eles são consolidados e exibidos como o serviço front-end do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bafee-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="bafee-122">Você pode impedir novas conexões para o serviço de front-ends do Lync Server, mas não pode impedir novas conexões para esses dois serviços de Lync Server subjacentes individuais separadamente.</span><span class="sxs-lookup"><span data-stu-id="bafee-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="bafee-p104">Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.</span><span class="sxs-lookup"><span data-stu-id="bafee-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="bafee-125">Para impedir novas conexões ao Lync Server:</span><span class="sxs-lookup"><span data-stu-id="bafee-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="bafee-126">Faça logon no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="bafee-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="bafee-127">Abra o console de snap-in de serviços: clique em **Iniciar**, aponte para **todos os programas**, aponte para **Ferramentas administrativas**e clique em **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="bafee-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="bafee-128">Na lista, clique duas vezes no serviço do Windows Lync Server para o qual você deseja impedir novas conexões.</span><span class="sxs-lookup"><span data-stu-id="bafee-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="bafee-129">Na caixa de diálogo Propriedades, em **status do serviço: iniciado**, clique em **Pausar**.</span><span class="sxs-lookup"><span data-stu-id="bafee-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="bafee-130">Opcionalmente, mas recomendado, ao lado de **tipo de inicialização**, clique em **manual**.</span><span class="sxs-lookup"><span data-stu-id="bafee-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="bafee-p105">Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.</span><span class="sxs-lookup"><span data-stu-id="bafee-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="bafee-133">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bafee-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

