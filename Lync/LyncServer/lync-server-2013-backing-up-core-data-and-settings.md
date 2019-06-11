---
title: 'Lync Server 2013: fazendo backup de dados e configurações principais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1737dac3369361b0937e6b870839e11e5706e41a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="9aaf6-102">Fazer backup de dados principais e configurações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9aaf6-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9aaf6-103">_**Tópico da última modificação:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="9aaf6-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="9aaf6-104">Os procedimentos a seguir usam cmdlets do Shell de gerenciamento do Lync Server para criar arquivos de backup para configurações e dados para serviços básicos.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="9aaf6-105">Para obter detalhes sobre as ferramentas usadas nesta seção, incluindo onde elas estão localizadas, consulte [requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9aaf6-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="9aaf6-106">Para obter detalhes sobre como fazer backup de dados de arquivamento e monitoramento, consulte [fazendo backup de bancos de dados de arquivamento e monitoramento no Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9aaf6-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9aaf6-107">A etapa desta seção para fazer backup do repositório de gerenciamento central inclui as configurações e a configuração de arquivamento e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="9aaf6-108">Você pode executar os cmdlets descritos nesta seção localmente ou remotamente.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="9aaf6-109">Para fazer backup de dados principais e configurações</span><span class="sxs-lookup"><span data-stu-id="9aaf6-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="9aaf6-110">Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9aaf6-111">Para armazenar os backups que você cria nas etapas a seguir, crie uma nova pasta compartilhada e atualize o caminho referenciado por **$backup** para a nova pasta compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="9aaf6-112">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="9aaf6-113">Faça backup do arquivo de configuração do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="9aaf6-114">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="9aaf6-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9aaf6-116">Esta etapa exporta a topologia, as políticas e as configurações de configuração do Lync Server para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="9aaf6-117">Nenhuma outra etapa é necessária para fazer o backup dos dados da topologia.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="9aaf6-118">Copie o arquivo de configuração do repositório de gerenciamento central de backup para\\$backup.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="9aaf6-119">Faça backup dos dados do serviço de informações de localização.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-119">Back up Location Information service data.</span></span> <span data-ttu-id="9aaf6-120">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="9aaf6-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="9aaf6-122">Copie o arquivo de configuração do serviço de informações de localização com backup\\para $backup.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="9aaf6-123">Faça backup dos dados do usuário em todos os bancos de dados back-end de um pool Front-end e em cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="9aaf6-124">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="9aaf6-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="9aaf6-126">Copie o arquivo de usuário com backup para $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="9aaf6-127">Em cada pool que executa o aplicativo de grupo de resposta, faça backup da configuração do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="9aaf6-128">Do the following:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="9aaf6-129">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="9aaf6-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="9aaf6-131">Copie o arquivo de configuração do grupo de resposta de backup\\para $backup.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

