---
title: 'Lync Server 2013: restaurar o servidor que hospeda o repositório de gerenciamento central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="bf561-102">Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf561-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf561-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bf561-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bf561-104">Uma implantação do Lync Server tem um único repositório central de gerenciamento, uma cópia do que é replicada para cada servidor executando uma função de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf561-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="bf561-105">Este tópico descreve como restaurar um servidor back-end ou Standard Edition que hospeda o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="bf561-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="bf561-106">Para localizar o pool em que o servidor de gerenciamento central está localizado, abra o construtor de topologias, clique em **Lync Server**e examine o painel à direita em **servidor de gerenciamento central**.</span><span class="sxs-lookup"><span data-stu-id="bf561-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="bf561-107">Se o servidor back-end que hospeda o repositório de gerenciamento central estiver em uma instalação espelhada e o banco de dados espelho ainda estiver funcional, recomendamos que você faça um backup desse espelho ainda funcional e execute uma restauração completa no banco de dados primário e no banco de dados espelho, usando este backup, seguindo o procedimento de restauração abaixo.</span><span class="sxs-lookup"><span data-stu-id="bf561-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="bf561-108">Isso é necessário porque a restauração de back-end exige a modificação e a publicação da topologia, e isso pode ser feito apenas se o CMS primário que hospeda o CMS estiver operacional.</span><span class="sxs-lookup"><span data-stu-id="bf561-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="bf561-109">Observe também que as funções de banco de dados principal e espelho não poderão ser trocadas se não for possível publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="bf561-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf561-110">Se um servidor back-end do servidor ou da edição Standard que não hospeda o repositório de gerenciamento central falhar, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restaurando um servidor back-end do Enterprise Edition no Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restaurando um servidor Standard Edition no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bf561-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="bf561-111">Se um servidor back-end que hospeda o repositório de gerenciamento central estiver em uma configuração espelhada e somente o espelho falhar, consulte <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restaurando um servidor back-end do Enterprise Edition espelhado no Lync Server 2013-Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="bf561-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="bf561-112">Se houver falha em qualquer outro servidor, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restaurando um servidor membro do Enterprise Edition no Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bf561-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="bf561-113">Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="bf561-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="bf561-114">Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="bf561-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="bf561-115">Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="bf561-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="bf561-116">Para restaurar o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="bf561-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="bf561-117">Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="bf561-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf561-118">Siga os procedimentos de implantação do servidor da sua organização para executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="bf561-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="bf561-119">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins e do grupo Administradores local, faça logon no servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="bf561-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="bf561-120">Se você estiver restaurando um servidor Standard Edition, restaure o repositório de arquivos copiando o repositório de arquivos apropriado de $Backup para o local do repositório de arquivos no servidor e, em seguida, compartilhe a pasta.</span><span class="sxs-lookup"><span data-stu-id="bf561-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf561-121">O caminho e o nome do arquivo do repositório de arquivos restaurados devem ser exatamente os mesmos do armazenamento de arquivos em backup para que os componentes que usam os arquivos possam acessá-los.</span><span class="sxs-lookup"><span data-stu-id="bf561-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="bf561-122">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="bf561-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="bf561-123">Se você estiver instalando um servidor Standard Edition, navegue até a pasta de instalação ou a mídia do Lync Server e inicie o assistente de implantação do \\Lync\\Server\\localizado em setup AMD64 setup. exe.</span><span class="sxs-lookup"><span data-stu-id="bf561-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="bf561-124">No assistente de implantação, clique em **preparar primeiro servidor Standard Edition** e siga o assistente para instalar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="bf561-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="bf561-125">Se você estiver instalando um servidor de back-end corporativo, instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes das instâncias iguais aos da falha.</span><span class="sxs-lookup"><span data-stu-id="bf561-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bf561-126">Dependendo do servidor que você está restaurando e na sua implantação, o servidor pode incluir vários bancos de dados posicionados ou separados.</span><span class="sxs-lookup"><span data-stu-id="bf561-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="bf561-127">Siga o mesmo procedimento para instalar o SQL Server que você usou originalmente para implantar o servidor, incluindo as permissões e os logons do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf561-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="bf561-128">Em um servidor front-end, inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf561-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="bf561-129">Crie novamente o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="bf561-129">Re-create the Central Management store.</span></span> <span data-ttu-id="bf561-130">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="bf561-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="bf561-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bf561-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="bf561-132">Defina o ponto de controle dos serviços de domínio Active Directory para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="bf561-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="bf561-133">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="bf561-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="bf561-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bf561-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf561-135">Se você perder o ponto de conexão, poderá executar novamente esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bf561-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="bf561-136">Importar os dados do repositório de gerenciamento central de $Backup.</span><span class="sxs-lookup"><span data-stu-id="bf561-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="bf561-137">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="bf561-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="bf561-138">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bf561-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="bf561-139">Habilite as alterações que você acabou de fazer.</span><span class="sxs-lookup"><span data-stu-id="bf561-139">Enable the changes you have just made.</span></span> <span data-ttu-id="bf561-140">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="bf561-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf561-141">Depois de habilitar a topologia, você pode encontrar o documento de topologia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bf561-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="bf561-142">Se você estiver restaurando um servidor back-end do Enterprise Edition que também hospedava o CMS ou se precisar recriar um espelho do CMS, siga esta etapa.</span><span class="sxs-lookup"><span data-stu-id="bf561-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="bf561-143">Caso contrário, pule para a etapa 11.</span><span class="sxs-lookup"><span data-stu-id="bf561-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="bf561-144">Instale os bancos de dados autônomos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="bf561-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="bf561-145">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf561-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="bf561-146">Clique em **baixar topologia da implantação existente**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf561-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="bf561-147">Selecione a topologia e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="bf561-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="bf561-148">Clique em **Sim** para confirmar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="bf561-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="bf561-149">Clique com o botão direito do mouse no nó do **Lync Server 2013** e clique em **instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="bf561-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="bf561-150">Siga o assistente de **instalação de banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="bf561-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="bf561-151">Se você estiver restaurando um banco de dados diferente do repositório de gerenciamento central neste servidor, na página **criar bancos** de dados, selecione os bancos de dados que você deseja recriar.</span><span class="sxs-lookup"><span data-stu-id="bf561-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bf561-152">Somente bancos de dados autônomos são exibidos na página <STRONG>criar bancos de dados</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="bf561-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="bf561-153">Bancos de dados posicionados são criados quando você executa o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf561-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="bf561-154">Se você estiver restaurando um servidor back-end espelhado, continue a acompanhar o restante do assistente até chegar à solicitação de criar banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="bf561-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="bf561-155">Selecione o banco de dados que você deseja instalar e conclua o processo.</span><span class="sxs-lookup"><span data-stu-id="bf561-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="bf561-156">Siga o restante do assistente e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="bf561-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="bf561-157">Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsDatabase</STRONG> para criar cada banco de dados e o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="bf561-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="bf561-158">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="bf561-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="bf561-159">Se você estiver restaurando um servidor Standard Edition, navegue até a pasta de instalação ou a mídia do Lync Server e inicie o assistente de implantação \\do\\Lync\\Server localizado em setup AMD64 setup. exe.</span><span class="sxs-lookup"><span data-stu-id="bf561-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="bf561-160">Use o assistente de implantação do Lync Server para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bf561-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="bf561-161">Execute a **etapa 1: instalar o repositório de configuração local** para instalar os arquivos de configuração local.</span><span class="sxs-lookup"><span data-stu-id="bf561-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="bf561-162">Execute a **etapa 2: configurar ou remover componentes do Lync Server** para instalar as funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf561-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="bf561-163">Execute a **etapa 3: solicitar, instalar ou atribuir certificados** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="bf561-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="bf561-164">Execute a **etapa 4: Iniciar serviços** para iniciar serviços no servidor.</span><span class="sxs-lookup"><span data-stu-id="bf561-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="bf561-165">Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="bf561-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="bf561-166">Restaure os dados do usuário executando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bf561-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="bf561-167">Copie ExportedUserData. zip de $Backup\\ para um diretório local.</span><span class="sxs-lookup"><span data-stu-id="bf561-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="bf561-168">Antes de restaurar os dados do usuário, você deve parar os serviços do Lync.</span><span class="sxs-lookup"><span data-stu-id="bf561-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="bf561-169">Para fazer isso, digite:</span><span class="sxs-lookup"><span data-stu-id="bf561-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="bf561-170">Para restaurar os dados do usuário, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="bf561-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="bf561-171">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bf561-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="bf561-172">Reinicie os serviços do Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="bf561-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="bf561-173">Restaurar dados de informações de localização para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="bf561-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="bf561-174">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="bf561-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="bf561-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bf561-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="bf561-176">Se você implantou o grupo de resposta nesse pool ou no servidor Standard Edition, restaure os dados de configuração do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="bf561-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="bf561-177">Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="bf561-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="bf561-178">Se você estiver restaurando um servidor back-end que inclui o arquivamento ou o monitoramento de bancos de dados, restaure os dados de arquivamento ou monitoramento usando uma ferramenta de gerenciamento do SQL Server, como o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="bf561-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="bf561-179">Para obter detalhes, consulte [restaurando o monitoramento ou arquivando dados no Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="bf561-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

