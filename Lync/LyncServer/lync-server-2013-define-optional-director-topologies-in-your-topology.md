---
title: 'Lync Server 2013: definir topologias opcionais de diretor em sua topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0448ddfdb9988b791ff14dff89ab4c122df1d38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="17f38-102">Definir topologias opcionais de diretor em sua topologia para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17f38-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17f38-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="17f38-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="17f38-104">Os diretores do Lync Server 2013 podem ser servidores de instância única ou podem ser instalados como um pool de balanceamento de carga de vários diretores para maior disponibilidade e capacidade.</span><span class="sxs-lookup"><span data-stu-id="17f38-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="17f38-105">O balanceamento de carga de hardware e o balanceamento de carga do DNS (sistema de nomes de domínio) são suportados.</span><span class="sxs-lookup"><span data-stu-id="17f38-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="17f38-106">Este tópico explica como configurar o balanceamento de carga de DNS para pools de diretores.</span><span class="sxs-lookup"><span data-stu-id="17f38-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="17f38-107">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que seja membro dos grupos **RTCUniversalServerAdmins** e **Domain admins** .</span><span class="sxs-lookup"><span data-stu-id="17f38-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="17f38-108">Você também pode delegar os direitos e permissões de administrador adequados para a adição de funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="17f38-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="17f38-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="17f38-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="17f38-110">Para outras alterações de configuração, somente a associação ao grupo **RTCUniversalServerAdmins** é necessária.</span><span class="sxs-lookup"><span data-stu-id="17f38-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="17f38-111">Este tópico descreve as etapas para definir e publicar a topologia para as duas topologias de Diretor:</span><span class="sxs-lookup"><span data-stu-id="17f38-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="17f38-112">Para definir o diretor (instância única)</span><span class="sxs-lookup"><span data-stu-id="17f38-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="17f38-113">Para definir o Diretor (pool de vários Diretores)</span><span class="sxs-lookup"><span data-stu-id="17f38-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="17f38-114">Para definir o diretor (instância única)</span><span class="sxs-lookup"><span data-stu-id="17f38-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="17f38-115">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="17f38-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="17f38-116">Na página de boas-vindas, clique em **Baixar Topologia da Implantação Existente**.</span><span class="sxs-lookup"><span data-stu-id="17f38-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="17f38-117">Na caixa de diálogo **Salvar Topologia Como**, digite o nome o local da cópia local da topologia existente e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="17f38-118">Expanda o site no qual você planeja adicionar o Diretor, clique com o botão direito do mouse em **Pools de Diretores** e clique em **Novo Pool de Diretores**.</span><span class="sxs-lookup"><span data-stu-id="17f38-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="17f38-119">Na caixa de diálogo **Definir o FQDN do pool de Diretores**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="17f38-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="17f38-120">Em **FQDN do Pool**, digite o FQDN do pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="17f38-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="17f38-121">Clique em **Pool de computador único** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="17f38-122">Na caixa de diálogo **Definir o compartilhamento de arquivo**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="17f38-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="17f38-123">Para usar um compartilhamento de arquivo existente, clique em **Usar um compartilhamento de arquivos previamente definido**, selecione um compartilhamento de arquivo na lista e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="17f38-124">Para criar um novo compartilhamento de arquivo, clique em **Definir um novo compartilhamento de arquivo**, digite o FQDN do local do compartilhamento de arquivo em **FQDN do servidor de arquivos**, digite o nome do compartilhamento em **Compartilhamento de Arquivo** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17f38-125">O compartilhamento de arquivo especificado ou criado nesta etapa precisa existir ou ser criado antes da publicação da topologia.</span><span class="sxs-lookup"><span data-stu-id="17f38-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="17f38-126">O compartilhamento de arquivo atribuído a um Diretor não é realmente usado. Dessa forma, você pode atribuir o compartilhamento de arquivo de qualquer pool na organização.</span><span class="sxs-lookup"><span data-stu-id="17f38-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="17f38-127">Na caixa de diálogo **Especificar a URL dos Serviços Web**, em **URL Base Externa**, especifique o FQDN para os Diretores e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="17f38-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17f38-128">O nome deve ser resolvido a partir de servidores DNS da Internet e apontar para o endereço IP público do proxy reverso, que escuta solicitações HTTP/HTTPS para essa URL e as proxies para o diretório virtual de serviços Web externos nesse diretor.</span><span class="sxs-lookup"><span data-stu-id="17f38-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="17f38-129">Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="17f38-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="17f38-130">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="17f38-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="17f38-131">Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="17f38-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="17f38-132">Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="17f38-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="17f38-133">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="17f38-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="17f38-134">Para definir o Diretor (pool de vários Diretores)</span><span class="sxs-lookup"><span data-stu-id="17f38-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="17f38-135">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="17f38-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="17f38-136">Na página de boas-vindas, clique em **Baixar Topologia da Implantação Existente**.</span><span class="sxs-lookup"><span data-stu-id="17f38-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="17f38-137">Na caixa de diálogo **Salvar Topologia Como**, digite o nome o local da cópia local da topologia existente e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="17f38-138">Expanda o site no qual você planeja adicionar o Diretor, clique com o botão direito do mouse em **Pools de Diretores** e clique em **Novo Pool de Diretores**.</span><span class="sxs-lookup"><span data-stu-id="17f38-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="17f38-139">Na caixa de diálogo **Definir o FQDN do pool de Diretores**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="17f38-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="17f38-140">Em **FQDN do Pool**, digite o FQDN do pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="17f38-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="17f38-141">Clique em **Pool de vários computadores** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="17f38-142">Na caixa de diálogo **Definir os computadores neste pool**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="17f38-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="17f38-143">Especifique o FQDN do computador do primeiro membro do pool e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="17f38-p104">Repita a etapa anterior para cada computador que você deseja adicionar. Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="17f38-146">Na caixa de diálogo **Definir o compartilhamento de arquivo**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="17f38-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="17f38-147">Para usar um compartilhamento de arquivo existente, clique em **Usar um compartilhamento de arquivos previamente definido**, selecione um compartilhamento de arquivo na lista e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="17f38-148">Para criar um novo compartilhamento de arquivo, clique em **Definir um novo compartilhamento de arquivo**, digite o FQDN do local do compartilhamento de arquivo em **FQDN do servidor de arquivos**, digite o nome do compartilhamento em **Compartilhamento de Arquivo** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17f38-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17f38-149">O compartilhamento de arquivo especificado ou criado nesta etapa precisa existir ou ser criado antes da publicação da topologia.</span><span class="sxs-lookup"><span data-stu-id="17f38-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="17f38-150">O compartilhamento de arquivo atribuído a um Diretor não é realmente usado. Dessa forma, você pode atribuir o compartilhamento de arquivo de qualquer pool na organização.</span><span class="sxs-lookup"><span data-stu-id="17f38-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="17f38-151">Na caixa de diálogo **Especificar a URL dos Serviços Web**, em **URL Base Externa**, especifique o FQDN para os Diretores e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="17f38-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17f38-152">O nome precisa ser resolvido a partir dos servidores DNS de Internet e apontar para o endereço IP público do proxy reverso, que escuta as solicitações HTTP/HTTPS enviadas a essa URL e as atribui ao diretório virtual dos Serviços Web nesse pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="17f38-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="17f38-153">Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="17f38-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="17f38-154">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="17f38-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="17f38-155">Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="17f38-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="17f38-156">Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="17f38-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="17f38-157">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="17f38-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

