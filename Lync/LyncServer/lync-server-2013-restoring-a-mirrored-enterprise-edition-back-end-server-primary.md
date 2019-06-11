---
title: Restaurando um servidor back-end do Enterprise Edition espelhado-primário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="78c6b-102">Restaurando um servidor back-end da edição Enterprise espelhada no Lync Server 2013-principal</span><span class="sxs-lookup"><span data-stu-id="78c6b-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78c6b-103">_**Tópico da última modificação:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="78c6b-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="78c6b-104">Se você tiver um servidor back-end do Enterprise Edition em uma configuração espelhada e somente o banco de dados principal falhar, siga os procedimentos desta seção.</span><span class="sxs-lookup"><span data-stu-id="78c6b-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="78c6b-105">Se o banco de dados primário e o espelhamento falharem, consulte [restaurando um servidor back-end do Enterprise Edition no Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="78c6b-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="78c6b-106">Se apenas o espelho falhar, consulte [restaurando um servidor back-end do espelhado Enterprise Edition no Lync server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="78c6b-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="78c6b-107">Se o banco de dados que hospeda o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="78c6b-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="78c6b-108">Se um servidor membro da edição Enterprise que não for o servidor back-end falhar, consulte [restaurando um servidor membro da Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="78c6b-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="78c6b-109">Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="78c6b-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="78c6b-110">Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="78c6b-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="78c6b-111">Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="78c6b-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="78c6b-112">Neste tópico, o banco de dados primário de exemplo terá um FQDN (nome de domínio totalmente qualificado) de BE1.contoso.com e o banco de dados espelho terá um FQDN de BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="78c6b-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="78c6b-113">Para restaurar um banco de dados primário do servidor back-end do Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="78c6b-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="78c6b-114">Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="78c6b-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="78c6b-115">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="78c6b-116">Force o failover de todos os bancos de dados configurados para o espelho.</span><span class="sxs-lookup"><span data-stu-id="78c6b-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="78c6b-117">Para cada um dos tipos de banco de dados que você configurou neste servidor, digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="78c6b-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="78c6b-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="78c6b-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="78c6b-119">Se você tiver configurado seu banco de dados back-end para usar o espelhamento sincronizado com uma testemunha, o failover será automático.</span><span class="sxs-lookup"><span data-stu-id="78c6b-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="78c6b-120">Após concluir o failover, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="78c6b-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="78c6b-121">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="78c6b-122">Desabilitar o espelhamento no servidor back-end: clique com o botão direito do mouse no pool em pools de **front-end do Enterprise Edition** e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="78c6b-123">Na guia **geral** , em **associações**, desmarque a caixa de seleção Habilitar o espelhamento da **loja do SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="78c6b-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="78c6b-124">Faça isso para arquivamento e monitoramento conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="78c6b-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="78c6b-125">Em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="78c6b-126">Clique com o botão direito do mouse no nó do Lync Server 2013, clique em **topologia**e, em seguida, clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="78c6b-127">Selecione o back-end que ainda funciona (BE2.contoso.com) para ser o novo repositório do SQL.</span><span class="sxs-lookup"><span data-stu-id="78c6b-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="78c6b-128">Para fazer isso, clique com o botão direito do mouse no pool em pools de **front-end do Enterprise Edition** e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="78c6b-129">Na guia **geral** , em **associações**, digite o FQDN do back-end que funciona no campo da **loja do SQL Server** (em nosso exemplo, BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78c6b-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="78c6b-130">Clique com o botão direito do mouse no nó do Lync Server 2013, clique em **topologia**e, em seguida, clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="78c6b-131">Reinicie os serviços para que cada servidor possa ler a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="78c6b-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="78c6b-132">Em um shell de gerenciamento do Lync Server, execute os seguintes cmdlets em cada servidor front-end que pertence a este pool:</span><span class="sxs-lookup"><span data-stu-id="78c6b-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="78c6b-133">Desinstale o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="78c6b-133">Uninstall mirroring.</span></span> <span data-ttu-id="78c6b-134">Em um shell de gerenciamento do Lync Server, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="78c6b-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="78c6b-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="78c6b-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="78c6b-136">Faça isso para todos os tipos de banco de dados neste servidor.</span><span class="sxs-lookup"><span data-stu-id="78c6b-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="78c6b-137">Crie um servidor limpo ou novo que tenha o mesmo FQDN (neste exemplo, DB1.contoso.com) como o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="78c6b-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="78c6b-138">Este servidor funcionará como o novo espelho.</span><span class="sxs-lookup"><span data-stu-id="78c6b-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="78c6b-139">Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="78c6b-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="78c6b-140">Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes das instâncias iguais aos anteriores à falha.</span><span class="sxs-lookup"><span data-stu-id="78c6b-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="78c6b-141">Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="78c6b-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="78c6b-142">Use o construtor de topologias para instalar o Mirror DB.</span><span class="sxs-lookup"><span data-stu-id="78c6b-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="78c6b-143">Execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="78c6b-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="78c6b-144">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="78c6b-145">Habilite o espelhamento no servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="78c6b-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="78c6b-146">Para fazer isso, clique com o botão direito do mouse no pool em pools de **front-end do Enterprise Edition** e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="78c6b-147">Na guia **geral** , em **associações**, marque a caixa de seleção Habilitar o espelhamento da **loja do SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="78c6b-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="78c6b-148">Além disso, faça isso para arquivamento e monitoramento, se necessário.</span><span class="sxs-lookup"><span data-stu-id="78c6b-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="78c6b-149">Em seguida, no campo espelhar o **repositório do SQL Server** , digite o FQDN do novo servidor (n este exemplo, BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78c6b-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="78c6b-150">Em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="78c6b-151">Clique com o botão direito do mouse no nó do Lync Server 2013, clique em **topologia**e clique em **instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="78c6b-152">Siga o assistente de **instalação de banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="78c6b-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="78c6b-153">Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.</span><span class="sxs-lookup"><span data-stu-id="78c6b-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="78c6b-154">Siga o assistente até chegar ao prompt, **criar banco de dados espelho**.</span><span class="sxs-lookup"><span data-stu-id="78c6b-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="78c6b-155">Selecione o banco de dados que você deseja instalar e conclua esse processo.</span><span class="sxs-lookup"><span data-stu-id="78c6b-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

