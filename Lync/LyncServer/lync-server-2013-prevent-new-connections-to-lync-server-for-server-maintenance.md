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
ms.openlocfilehash: fb0e2db6eeff584c4d1ab08bdd293113f1394e4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="71dcc-102">Impedir novas conexões com o Lync Server 2013 para manutenção do servidor</span><span class="sxs-lookup"><span data-stu-id="71dcc-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71dcc-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="71dcc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="71dcc-104">O Lync Server permite que você coloque um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem perda de serviço aos usuários.</span><span class="sxs-lookup"><span data-stu-id="71dcc-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="71dcc-105">Quando você especificar a opção para impedir novas conexões ou chamadas para um servidor em um pool, ela deixará de fazer novas conexões e chamadas assim que você implementar essa opção.</span><span class="sxs-lookup"><span data-stu-id="71dcc-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="71dcc-106">Essas novas conexões e chamadas são roteadas por meio de outros servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="71dcc-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="71dcc-107">Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até que elas terminem naturalmente.</span><span class="sxs-lookup"><span data-stu-id="71dcc-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="71dcc-108">Quando todas as sessões existentes terminarem, o servidor estará pronto para ser colocado offline.</span><span class="sxs-lookup"><span data-stu-id="71dcc-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="71dcc-109">Quando você impede novas conexões a um servidor front-end, alguns recursos e serviços do Lync Server dependem do balanceamento de carga de DNS para garantir que ele funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="71dcc-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="71dcc-110">Se você não estiver usando o balanceamento de carga de DNS no pool, as conexões por meio desses serviços não poderão ser reencaminhadas a outros servidores durante o período em que o servidor está impedindo novas conexões e, portanto, quando o servidor for colocado offline, algumas sessões e chamadas poderão ser interrompido.</span><span class="sxs-lookup"><span data-stu-id="71dcc-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="71dcc-111">Os recursos que dependem do balanceamento de carga de DNS para garantir que essa opção funcione corretamente são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="71dcc-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="71dcc-112">Atendedor</span><span class="sxs-lookup"><span data-stu-id="71dcc-112">Attendant</span></span>

  - <span data-ttu-id="71dcc-113">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="71dcc-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="71dcc-114">Aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="71dcc-114">Response Group application</span></span>

  - <span data-ttu-id="71dcc-115">Aplicativo Comunicado</span><span class="sxs-lookup"><span data-stu-id="71dcc-115">Announcement application</span></span>

  - <span data-ttu-id="71dcc-116">Aplicativo de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="71dcc-116">Call Park application</span></span>

<span data-ttu-id="71dcc-117">Para obter detalhes sobre o balanceamento de carga de DNS, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="71dcc-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="71dcc-118">Além de impedir novas conexões para todos os serviços em um servidor que executa o Lync Server, você também pode impedir novas conexões para serviços individuais do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71dcc-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="71dcc-119">Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização do Lync Server que não exija que todo o servidor seja desligado.</span><span class="sxs-lookup"><span data-stu-id="71dcc-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="71dcc-120">Observe que, ao impedir conexões para um serviço, você deve selecionar um serviço como ele está agrupado e exibido na lista de serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="71dcc-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="71dcc-121">Por exemplo, o serviço de front-end do Lync Server e o agente de coleta de dados para monitoramento são serviços do Lync Server separados, mas na lista de serviços do Windows eles são consolidados e exibidos como o serviço de front-end do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71dcc-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="71dcc-122">Você pode impedir novas conexões para o serviço de front-end do Lync Server, mas não pode impedir novas conexões para esses dois serviços individuais do Lync Server subjacentes separadamente.</span><span class="sxs-lookup"><span data-stu-id="71dcc-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="71dcc-123">Quando você define um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão, o servidor começará imediatamente a aceitar novas conexões depois que ele for iniciado.</span><span class="sxs-lookup"><span data-stu-id="71dcc-123">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="71dcc-124">Para evitar isso, defina o servidor para pausar e retomar manualmente, antes de reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="71dcc-124">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="71dcc-125">Para impedir novas conexões com o Lync Server:</span><span class="sxs-lookup"><span data-stu-id="71dcc-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="71dcc-126">Faça logon no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="71dcc-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="71dcc-127">Abra o console do snap-in Serviços: clique em **Iniciar**, aponte para **todos os programas**, aponte para **Ferramentas administrativas**e clique em **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="71dcc-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="71dcc-128">Na lista, clique duas vezes no serviço do Windows Lync Server ao qual você deseja impedir novas conexões.</span><span class="sxs-lookup"><span data-stu-id="71dcc-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="71dcc-129">Na caixa de diálogo Propriedades, em **status do serviço: iniciado**, clique em **Pausar**.</span><span class="sxs-lookup"><span data-stu-id="71dcc-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="71dcc-130">Opcionalmente, mas recomendado, ao lado de **tipo de inicialização**, clique em **manual**.</span><span class="sxs-lookup"><span data-stu-id="71dcc-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="71dcc-131">Quando você define um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão, o servidor começará imediatamente a aceitar novas conexões depois que ele for iniciado.</span><span class="sxs-lookup"><span data-stu-id="71dcc-131">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="71dcc-132">Para evitar isso, defina o servidor para pausar e retomar manualmente, antes de reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="71dcc-132">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="71dcc-133">Ao concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="71dcc-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

