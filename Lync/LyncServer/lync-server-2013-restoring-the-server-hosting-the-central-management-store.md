---
title: 'Lync Server 2013: restaurar o servidor que hospeda o repositório de gerenciamento central'
description: 'Lync Server 2013: restaurar o servidor que hospeda o repositório de gerenciamento central.'
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
ms.openlocfilehash: c0c07e4c6722695b2bfb4cb478a1f3eefa86b4eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575447"
---
# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="023c2-103">Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="023c2-103">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="023c2-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="023c2-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="023c2-105">Uma implantação do Lync Server tem um único repositório de gerenciamento central, uma cópia do que é replicada para cada servidor que executa uma função de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="023c2-105">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="023c2-106">Este tópico descreve como restaurar um servidor back-end ou um servidor Standard Edition que hospeda o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="023c2-106">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="023c2-107">Para localizar o pool onde o servidor de gerenciamento central está localizado, abra o construtor de topologias, clique em **Lync Server**e examine o painel direito em **servidor de gerenciamento central**.</span><span class="sxs-lookup"><span data-stu-id="023c2-107">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="023c2-108">Se o servidor back-end que hospeda o repositório de gerenciamento central estiver em uma instalação espelhada e o banco de dados de espelho ainda estiver funcional, recomendamos que você faça um backup desse espelho ainda em funcionamento e, em seguida, execute uma restauração completa no banco de dados primário e no banco de dados espelho, usando esse backup, seguindo o procedimento de restauração abaixo.</span><span class="sxs-lookup"><span data-stu-id="023c2-108">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="023c2-109">Isso é necessário porque o back-end Restore requer a modificação e publicação da topologia, e isso só pode ser feito se o banco de dados primário que hospeda o CMS estiver operacional.</span><span class="sxs-lookup"><span data-stu-id="023c2-109">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="023c2-110">Observe também que as funções de banco de dados principal e espelho não podem ser trocadas se a topologia não puder ser publicada.</span><span class="sxs-lookup"><span data-stu-id="023c2-110">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="023c2-111">Se um servidor back-end ou um servidor Standard Edition que não hospeda o repositório de gerenciamento central falhar, confira <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restaurar um servidor de back-end Enterprise Edition no Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restaurar um servidor Standard Edition no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="023c2-111">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="023c2-112">Se um servidor back-end que hospeda o repositório de gerenciamento central estiver em uma configuração espelhada e apenas o espelho falhar, confira a <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restauração de um servidor back-end do espelhamento Enterprise Edition no Lync Server 2013-Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="023c2-112">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="023c2-113">Se qualquer outro servidor falhar, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restaurando um servidor membro Enterprise Edition no Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="023c2-113">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="023c2-114">Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="023c2-114">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="023c2-115">Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="023c2-115">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="023c2-116">Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="023c2-116">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="023c2-117">Para restaurar o Repositório de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="023c2-117">To restore the Central Management store</span></span>

1.  <span data-ttu-id="023c2-118">Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="023c2-118">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="023c2-119">Siga os procedimentos de implantação de servidor de sua organização para executar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="023c2-119">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="023c2-120">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins e do grupo Administradores local, faça logon no servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="023c2-120">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="023c2-121">Se você estiver restaurando um servidor Standard Edition, restaure o repositório de arquivos copiando o repositório de arquivos apropriado de $Backup para o local do repositório de arquivos no servidor e, em seguida, compartilhe a pasta.</span><span class="sxs-lookup"><span data-stu-id="023c2-121">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="023c2-122">O caminho e o nome de arquivo para o repositório de arquivos restaurados devem ser exatamente os mesmos do repositório de arquivos de backup para que os componentes que usam os arquivos possam acessá-los.</span><span class="sxs-lookup"><span data-stu-id="023c2-122">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="023c2-123">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="023c2-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="023c2-124">Se você estiver instalando um servidor Standard Edition, navegue até a pasta ou a mídia de instalação do Lync Server e inicie o assistente de implantação do Lync Server localizado no \\ arquivo de instalação \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="023c2-124">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="023c2-125">No assistente de implantação, clique em **preparar primeiro servidor Standard Edition** e siga o assistente para instalar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="023c2-125">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="023c2-126">Se você estiver instalando um servidor back-end corporativo, instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes de instância iguais aos anteriores à falha.</span><span class="sxs-lookup"><span data-stu-id="023c2-126">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="023c2-127">Dependendo do servidor que você está restaurando e em sua implantação, o servidor pode incluir vários bancos de dados posicionados ou separados.</span><span class="sxs-lookup"><span data-stu-id="023c2-127">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="023c2-128">Siga o mesmo procedimento para instalar o SQL Server que você usou originalmente para implantar o servidor, incluindo logons e permissões do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="023c2-128">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="023c2-129">Em um servidor front-end, inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="023c2-129">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="023c2-130">Recrie o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="023c2-130">Re-create the Central Management store.</span></span> <span data-ttu-id="023c2-131">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="023c2-131">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="023c2-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="023c2-132">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="023c2-133">Defina o ponto de controle dos serviços de domínio do Active Directory para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="023c2-133">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="023c2-134">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="023c2-134">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="023c2-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="023c2-135">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="023c2-136">Se você perder o ponto de conexão, poderá executar esse cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="023c2-136">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="023c2-137">Importe os dados do repositório de gerenciamento central a partir do $Backup.</span><span class="sxs-lookup"><span data-stu-id="023c2-137">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="023c2-138">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="023c2-138">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="023c2-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="023c2-139">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="023c2-p110">Habilite as alterações feitas por você. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="023c2-p110">Enable the changes you have just made. At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="023c2-142">Após habilitar a topologia, você pode encontrar o documento da topologia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="023c2-142">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="023c2-143">Se você estiver restaurando um servidor back-end Enterprise Edition que também hospedava o CMS, ou se precisar recriar um espelho do CMS, siga esta etapa.</span><span class="sxs-lookup"><span data-stu-id="023c2-143">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="023c2-144">Caso contrário, pule para a etapa 11.</span><span class="sxs-lookup"><span data-stu-id="023c2-144">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="023c2-145">Instale os bancos de dados autônomos fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="023c2-145">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="023c2-146">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="023c2-146">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="023c2-147">Clique em **Baixar Topologia da implantação existente** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="023c2-147">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="023c2-p112">Selecione a topologia e clique em **Salvar**. Clique em **Sim** para confirmar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="023c2-p112">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="023c2-150">Clique com o botão direito do mouse no nó **Lync Server 2013** e clique em **instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="023c2-150">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="023c2-151">Siga o assistente de **instalação de banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="023c2-151">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="023c2-152">Se você estiver restaurando um banco de dados diferente do repositório de gerenciamento central neste servidor, na página **criar bancos** de dados, selecione os bancos de dados que deseja recriar.</span><span class="sxs-lookup"><span data-stu-id="023c2-152">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="023c2-153">Somente os bancos de dados autônomos são exibidos na página <STRONG>Criar bancos de dados</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="023c2-153">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="023c2-154">Os bancos de dados colocados são criados quando você executa o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="023c2-154">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="023c2-155">Se você estiver restaurando um servidor back-end espelhado, continue a seguir o restante do assistente até chegar a uma solicitação de criar banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="023c2-155">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="023c2-156">Selecione o banco de dados que você deseja instalar e conclua o processo.</span><span class="sxs-lookup"><span data-stu-id="023c2-156">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="023c2-157">Siga o restante do assistente e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="023c2-157">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="023c2-158">Em vez de executar o construtor de topologias, você pode usar o cmdlet <STRONG>install-CsDatabase</STRONG> para criar cada banco de dados e o cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="023c2-158">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="023c2-159">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="023c2-159">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="023c2-160">Se você estiver restaurando um servidor Standard Edition, navegue até a pasta ou a mídia de instalação do Lync Server e inicie o assistente de implantação do Lync Server localizado no \\ arquivo de instalação \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="023c2-160">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="023c2-161">Use o assistente de implantação do Lync Server para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="023c2-161">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="023c2-162">Execute **Etapa 1: Instalar Repositório de Configuração Local** para instalar os arquivos de configuração locais.</span><span class="sxs-lookup"><span data-stu-id="023c2-162">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="023c2-163">Execute **etapa 2: instalar ou remover componentes do Lync Server** para instalar as funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="023c2-163">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="023c2-164">Execute **Etapa 3: Solicitar, Instalar ou Ceder Certificados** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="023c2-164">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="023c2-165">Execute **Etapa 4: Iniciar os Serviços** para iniciar os serviços no servidor.</span><span class="sxs-lookup"><span data-stu-id="023c2-165">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="023c2-166">Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="023c2-166">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="023c2-167">Restaure os dados do usuário executando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="023c2-167">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="023c2-168">Copie ExportedUserData.zip de $Backup \\ para um diretório local.</span><span class="sxs-lookup"><span data-stu-id="023c2-168">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="023c2-169">Antes de restaurar os dados do usuário, você deve interromper os serviços do Lync.</span><span class="sxs-lookup"><span data-stu-id="023c2-169">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="023c2-170">Para fazer isso, digite:</span><span class="sxs-lookup"><span data-stu-id="023c2-170">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="023c2-171">Para restaurar os dados do usuário, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="023c2-171">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="023c2-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="023c2-172">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="023c2-173">Reinicie os serviços do Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="023c2-173">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="023c2-174">Restaure os dados de informações do local para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="023c2-174">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="023c2-175">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="023c2-175">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="023c2-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="023c2-176">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="023c2-177">Se você implantou o grupo de resposta nesse pool ou no servidor Standard Edition, restaure os dados de configuração do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="023c2-177">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="023c2-178">Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="023c2-178">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="023c2-179">Se você estiver restaurando um servidor back-end que inclui bancos de dados de arquivamento ou monitoramento, restaure os dados de arquivamento ou monitoramento usando uma ferramenta de gerenciamento do SQL Server, como o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="023c2-179">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="023c2-180">Para obter detalhes, consulte [restaurando o monitoramento ou arquivando dados no Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="023c2-180">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

