---
title: 'Lync Server 2013: restaurando um servidor back-end Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429bf681e157beece170b9fe10e64fa8dea749ef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="b873a-102">Restaurando um servidor back-end Enterprise Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b873a-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b873a-103">_**Última modificação do tópico:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="b873a-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="b873a-104">Use o procedimento descrito neste tópico nos dois casos a seguir:</span><span class="sxs-lookup"><span data-stu-id="b873a-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="b873a-105">Os bancos de dados primário e espelho de um servidor back-end Enterprise Edition espelhado falha.</span><span class="sxs-lookup"><span data-stu-id="b873a-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="b873a-106">Um servidor de back-end Enterprise Edition que não é espelhado falha.</span><span class="sxs-lookup"><span data-stu-id="b873a-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="b873a-107">Se você tiver um back-end do Enterprise Edition espelhado e apenas o espelho ou banco de dados primário falhar, consulte [restaurando um servidor back-end do espelhado Enterprise Edition no Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar o banco de dados primário e [restaurar um servidor de back-end Enterprise Edition espelhado no Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar o espelho.</span><span class="sxs-lookup"><span data-stu-id="b873a-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="b873a-108">Se o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="b873a-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="b873a-109">Se um servidor membro Enterprise Edition que não seja o servidor back-end falhar, consulte [restaurando um servidor membro Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="b873a-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="b873a-110">Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="b873a-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="b873a-111">Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="b873a-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="b873a-112">Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="b873a-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="b873a-113">Para restaurar um servidor back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b873a-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="b873a-114">Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="b873a-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b873a-115">Siga os procedimentos de implantação de servidor de sua organização para executar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="b873a-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="b873a-116">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon no servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="b873a-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="b873a-117">Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes de instância o mesmo que antes da falha.</span><span class="sxs-lookup"><span data-stu-id="b873a-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b873a-118">Dependendo da sua implantação, o servidor back-end pode incluir vários bancos de dados posicionados ou separados.</span><span class="sxs-lookup"><span data-stu-id="b873a-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="b873a-119">Siga o mesmo procedimento para instalar o SQL Server que você usou originalmente para implantar o servidor, incluindo logons e permissões do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b873a-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="b873a-120">Após instalar o SQL Server, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="b873a-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="b873a-121">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b873a-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="b873a-122">Clique em **Baixar Topologia da implantação existente** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b873a-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="b873a-p104">Selecione a topologia e clique em **Salvar**. Clique em **Sim** para confirmar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="b873a-p104">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="b873a-125">Clique com o botão direito do mouse no nó **Lync Server 2013** e clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="b873a-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="b873a-126">Siga o assistente **Publicar a Topologia**.</span><span class="sxs-lookup"><span data-stu-id="b873a-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="b873a-127">Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.</span><span class="sxs-lookup"><span data-stu-id="b873a-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b873a-128">Somente os bancos de dados autônomos são exibidos na página <STRONG>Criar bancos de dados</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b873a-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="b873a-129">Se você estiver restaurando um back-end espelhado, continue a seguir o restante do assistente até que o prompt **criar banco de dados espelho** seja exibido.</span><span class="sxs-lookup"><span data-stu-id="b873a-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="b873a-130">Selecione o banco de dados que você deseja instalar e conclua o processo.</span><span class="sxs-lookup"><span data-stu-id="b873a-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="b873a-131">Siga o restante do assistente e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b873a-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="b873a-132">Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsDatabase</STRONG> para criar cada banco de dados e o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="b873a-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="b873a-133">Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b873a-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="b873a-134">Restaure os dados do usuário executando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b873a-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="b873a-135">Copie ExportedUserData. zip de $Backup\\ para um diretório local.</span><span class="sxs-lookup"><span data-stu-id="b873a-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="b873a-136">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b873a-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="b873a-137">Antes de restaurar os dados do usuário, você deve interromper os serviços do Lync.</span><span class="sxs-lookup"><span data-stu-id="b873a-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="b873a-138">Para fazer isso, digite:</span><span class="sxs-lookup"><span data-stu-id="b873a-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="b873a-139">Para restaurar os dados do usuário, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="b873a-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="b873a-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b873a-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="b873a-141">Reinicie os serviços do Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="b873a-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="b873a-142">Se você implantou o grupo de resposta nesse pool, restaure os dados de configuração do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="b873a-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="b873a-143">Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b873a-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="b873a-144">Se você estiver restaurando um servidor back-end que incluiu bancos de dados de arquivamento ou monitoramento, restaure os dados de arquivamento ou monitoramento usando uma ferramenta do SQL Server, como o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b873a-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="b873a-145">Para obter detalhes, consulte [restaurando o monitoramento ou arquivando dados no Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="b873a-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

