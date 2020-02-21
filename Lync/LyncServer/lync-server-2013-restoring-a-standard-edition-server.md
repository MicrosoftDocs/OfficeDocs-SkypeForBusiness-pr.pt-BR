---
title: 'Lync Server 2013: restaurar um servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77c49b7d1b02fc2d1cb41efd3fd68213fa8a0dfb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="a60f0-102">Restaurando um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a60f0-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a60f0-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a60f0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a60f0-104">Se um servidor Standard Edition que não hospeda o repositório de gerenciamento central falhar, siga os procedimentos desta seção.</span><span class="sxs-lookup"><span data-stu-id="a60f0-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="a60f0-105">Se o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="a60f0-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="a60f0-106">Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="a60f0-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="a60f0-107">Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="a60f0-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="a60f0-108">Convém usar a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="a60f0-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="a60f0-109">Para restaurar um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a60f0-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="a60f0-110">Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o computador com falha, instale o sistema operacional e restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="a60f0-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a60f0-111">Siga os procedimentos de implantação de servidor de sua organização para executar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="a60f0-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="a60f0-112">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins e do grupo Administradores local, faça logon no servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="a60f0-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="a60f0-113">Restaure o repositório de arquivos copiando o repositório de arquivos apropriado de $Backup para o local do repositório de arquivos no servidor e compartilhe a pasta.</span><span class="sxs-lookup"><span data-stu-id="a60f0-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a60f0-114">O caminho e o nome de arquivo para o repositório de arquivos restaurados devem ser exatamente os mesmos do repositório de arquivos de backup para que os componentes que usam os arquivos possam acessá-los.</span><span class="sxs-lookup"><span data-stu-id="a60f0-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="a60f0-115">Execute o construtor de topologia:</span><span class="sxs-lookup"><span data-stu-id="a60f0-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="a60f0-116">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a60f0-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="a60f0-117">Clique em **Baixar Topologia da implantação existente** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a60f0-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="a60f0-p103">Selecione a topologia e clique em **Salvar**. Clique em **Sim** para confirmar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="a60f0-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="a60f0-120">Navegue até a pasta de instalação ou mídia do Lync Server e, em seguida, inicie o assistente de \\implantação\\do\\Lync Server localizado em setup AMD64. exe.</span><span class="sxs-lookup"><span data-stu-id="a60f0-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="a60f0-121">Use o assistente de implantação do Lync Server para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a60f0-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="a60f0-122">Execute **Etapa 1: Instalar Repositório de Configuração Local** para instalar os arquivos de configuração locais.</span><span class="sxs-lookup"><span data-stu-id="a60f0-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="a60f0-123">Execute **etapa 2: instalar ou remover componentes do Lync Server** para instalar as funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a60f0-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="a60f0-124">Execute **Etapa 3: Solicitar, Instalar ou Ceder Certificados** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="a60f0-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="a60f0-125">Execute **Etapa 4: Iniciar os Serviços** para iniciar os serviços no servidor.</span><span class="sxs-lookup"><span data-stu-id="a60f0-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="a60f0-126">Para obter detalhes sobre como executar o Assistente de Implantação, consulte a documentação Implantação para a função de servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="a60f0-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="a60f0-127">Restaure os dados do usuário executando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a60f0-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="a60f0-128">Copie ExportedUserData. zip de $Backup\\ para um diretório local.</span><span class="sxs-lookup"><span data-stu-id="a60f0-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="a60f0-129">Antes de restaurar os dados do usuário, você deve interromper os serviços do Lync.</span><span class="sxs-lookup"><span data-stu-id="a60f0-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="a60f0-130">Para fazer isso, digite:</span><span class="sxs-lookup"><span data-stu-id="a60f0-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="a60f0-131">Para restaurar os dados do usuário, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="a60f0-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="a60f0-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a60f0-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="a60f0-133">Reinicie os serviços do Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="a60f0-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="a60f0-134">Se você implantou o grupo de resposta neste servidor Standard Edition, restaure os dados de configuração do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="a60f0-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="a60f0-135">Para obter detalhes, consulte [restaurando as configurações do grupo de resposta no Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a60f0-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="a60f0-136">Se você implantou o chat persistente neste servidor Standard Edition, restaure o banco de dados de chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="a60f0-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="a60f0-137">Se você usou o backup do SQL Server para fazer o backup do banco de dados de chat persistente, use os procedimentos de restauração do SQL Server para restaurá-lo.</span><span class="sxs-lookup"><span data-stu-id="a60f0-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="a60f0-138">Se você usou o cmdlet Export-CsPersistentChatData para fazer o backup, use o Import-CsPersistentChatData para restaurá-lo.</span><span class="sxs-lookup"><span data-stu-id="a60f0-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

