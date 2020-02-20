---
title: Restaurando um servidor back-end Enterprise Edition espelhado-primário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dfc3f9a44adbd4967e3d32ac7a515a55bc5d974
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="6e197-102">Restaurando um servidor back-end Enterprise Edition espelhado no Lync Server 2013-principal</span><span class="sxs-lookup"><span data-stu-id="6e197-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e197-103">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="6e197-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="6e197-104">Se você tiver um servidor back-end Enterprise Edition em uma configuração espelhada e apenas o banco de dados primário falhar, siga os procedimentos desta seção.</span><span class="sxs-lookup"><span data-stu-id="6e197-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="6e197-105">Se o banco de dados primário e o espelho falharem, consulte [restaurando um servidor de back-end Enterprise Edition no Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="6e197-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="6e197-106">Se apenas o espelho falhar, consulte [restaurando um servidor back-end do Enterprise Edition espelhado no Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="6e197-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="6e197-107">Se o banco de dados que hospeda o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="6e197-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="6e197-108">Se um servidor membro Enterprise Edition que não seja o servidor back-end falhar, consulte [restaurando um servidor membro Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="6e197-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="6e197-109">Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="6e197-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="6e197-110">Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="6e197-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="6e197-111">Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="6e197-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="6e197-112">Neste tópico, o banco de dados primário de exemplo terá um FQDN (nome de domínio totalmente qualificado) do BE1.contoso.com e o banco de dados espelho terá um FQDN de BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6e197-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="6e197-113">Para restaurar um banco de dados primário do servidor back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6e197-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="6e197-114">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6e197-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="6e197-115">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6e197-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6e197-116">Forçar o failover de todos os bancos de dados configurados para o espelho.</span><span class="sxs-lookup"><span data-stu-id="6e197-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="6e197-117">Para cada um dos tipos de banco de dados que você configurou neste servidor, digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6e197-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="6e197-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6e197-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="6e197-119">Caso tenha configurado o banco de dados back-end para usar espelhamento sincronizado com uma testemunha, o failover será automático.</span><span class="sxs-lookup"><span data-stu-id="6e197-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="6e197-120">Após concluir o failover, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e197-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="6e197-121">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6e197-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="6e197-122">Desabilitar o espelhamento no servidor back-end: clique com o botão direito do mouse no pool em **pools de front-ends do Enterprise Edition** e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6e197-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="6e197-123">Na guia **geral** , em **associações**, desmarque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="6e197-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="6e197-124">Faça isso para arquivamento e monitoramento, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="6e197-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="6e197-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e197-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="6e197-126">Clique com o botão direito do mouse no nó Lync Server 2013, clique em **topologia**e em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="6e197-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="6e197-127">Selecione o back-end (BE2.contoso.com) ainda funcional para ser o novo repositório do SQL.</span><span class="sxs-lookup"><span data-stu-id="6e197-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="6e197-128">Para fazer isso, clique com o botão direito do mouse no pool em **pools de front-ends do Enterprise Edition** e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6e197-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="6e197-129">Na guia **geral** , em **associações**, digite o FQDN do back-end em funcionamento no campo **repositório do SQL Server** (no nosso exemplo, BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6e197-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="6e197-130">Clique com o botão direito do mouse no nó Lync Server 2013, clique em **topologia**e em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="6e197-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="6e197-131">Reinicie os serviços para que cada servidor possa ler a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="6e197-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="6e197-132">A partir de um shell de gerenciamento do Lync Server, execute os seguintes cmdlets em cada servidor de front-end que pertença a este pool:</span><span class="sxs-lookup"><span data-stu-id="6e197-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="6e197-133">Desinstale o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6e197-133">Uninstall mirroring.</span></span> <span data-ttu-id="6e197-134">A partir de um shell de gerenciamento do Lync Server, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6e197-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="6e197-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6e197-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="6e197-136">Faça isso para todos os tipos de banco de dados neste servidor.</span><span class="sxs-lookup"><span data-stu-id="6e197-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="6e197-137">Crie um servidor limpo ou novo que tenha o mesmo FQDN (neste exemplo, DB1.contoso.com) como o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="6e197-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="6e197-138">Este servidor funcionará como o novo espelho.</span><span class="sxs-lookup"><span data-stu-id="6e197-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="6e197-139">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="6e197-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="6e197-140">Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes de instância o mesmo que antes da falha.</span><span class="sxs-lookup"><span data-stu-id="6e197-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="6e197-141">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6e197-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="6e197-142">Use o construtor de topologias para instalar o banco de BD espelho.</span><span class="sxs-lookup"><span data-stu-id="6e197-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="6e197-143">Execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="6e197-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="6e197-144">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6e197-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="6e197-145">Habilite o espelhamento no servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="6e197-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="6e197-146">Para fazer isso, clique com o botão direito do mouse no pool em **pools de front-ends do Enterprise Edition** e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6e197-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="6e197-147">Na guia **geral** , em **associações**, marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="6e197-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="6e197-148">Além disso, faça isso para arquivamento e monitoramento, se necessário.</span><span class="sxs-lookup"><span data-stu-id="6e197-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="6e197-149">Em seguida, no campo **espelhamento do SQL Server Store** , digite o FQDN do novo servidor (n este exemplo, BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6e197-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="6e197-150">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e197-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="6e197-151">Clique com o botão direito do mouse no nó Lync Server 2013, clique em **topologia**e em **instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="6e197-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="6e197-152">Siga o assistente de **instalação de banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="6e197-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="6e197-153">Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.</span><span class="sxs-lookup"><span data-stu-id="6e197-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="6e197-154">Siga o assistente até chegar ao prompt, criar um **banco de dados espelho**.</span><span class="sxs-lookup"><span data-stu-id="6e197-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="6e197-155">Selecione o banco de dados que você deseja instalar e conclua o processo.</span><span class="sxs-lookup"><span data-stu-id="6e197-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

