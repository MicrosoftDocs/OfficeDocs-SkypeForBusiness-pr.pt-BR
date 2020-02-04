---
title: 'Lync Server 2013: requisitos da webconferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 186f597c4328c8cee5085e7e599228b60c300a96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="87c0c-102">Requisitos da webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87c0c-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87c0c-103">_**Tópico da última modificação:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="87c0c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="87c0c-104">Se você optou por habilitar a webconferência, será necessário planejar:</span><span class="sxs-lookup"><span data-stu-id="87c0c-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="87c0c-105">O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.</span><span class="sxs-lookup"><span data-stu-id="87c0c-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="87c0c-106">Integração com o Servidor do Office Web Apps, necessária para compartilhar arquivos do PowerPoint durante uma conferência.</span><span class="sxs-lookup"><span data-stu-id="87c0c-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="87c0c-107">Repositório de Arquivos</span><span class="sxs-lookup"><span data-stu-id="87c0c-107">File Store</span></span>

<span data-ttu-id="87c0c-108">O serviço de Webconferência do Lync Server 2013 armazena conteúdo compartilhado durante reuniões no repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="87c0c-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="87c0c-109">Como parte da implantação, você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de front-end da edição Enterprise.</span><span class="sxs-lookup"><span data-stu-id="87c0c-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="87c0c-110">É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="87c0c-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="87c0c-111">Para obter mais informações, consulte Construtor de topologias – defina o repositório de arquivos do front-end.</span><span class="sxs-lookup"><span data-stu-id="87c0c-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="87c0c-112">O serviço de webconferências criptografa o conteúdo antes de armazená-lo no repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="87c0c-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="87c0c-113">O Lync Server 2013 oferece suporte ao uso de compartilhamentos de arquivos em DAS (armazenamento de conexão direta) ou de uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e um conjunto redundante de discos independentes (RAID) para armazenamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="87c0c-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="87c0c-114">Depois que o assistente de implantação do Lync Server tiver definido o local do compartilhamento de arquivos, o Lync Server criará uma estrutura de pastas dentro do compartilhamento de arquivos semelhante a:</span><span class="sxs-lookup"><span data-stu-id="87c0c-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="87c0c-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="87c0c-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="87c0c-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="87c0c-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="87c0c-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="87c0c-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="87c0c-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="87c0c-118">CollabContent</span></span>
    
      - <span data-ttu-id="87c0c-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="87c0c-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="87c0c-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="87c0c-120">DataConf</span></span>

<span data-ttu-id="87c0c-121">O serviço de webconferências então armazena conteúdo como slides do PowerPoint, quadros de comunicações, votações e anexos nas pastas CollabContent e CollabMetadata, localizadas na pasta WebServices.</span><span class="sxs-lookup"><span data-stu-id="87c0c-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="87c0c-122">O administrador deve definir permissões no compartilhamento de arquivos para que os grupos RTC tenham o acesso de leitura e gravação necessário.</span><span class="sxs-lookup"><span data-stu-id="87c0c-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="87c0c-123">Se você encontrar erros com as permissões, abra o construtor de topologias, baixe e Republique novamente a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="87c0c-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="87c0c-124">A publicação da topologia verificará as permissões de compartilhamento de arquivos e as redefinirá, se necessário.</span><span class="sxs-lookup"><span data-stu-id="87c0c-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="87c0c-125">Você pode usar as configurações a seguir para gerenciar como o conteúdo é armazenado para uma reunião:</span><span class="sxs-lookup"><span data-stu-id="87c0c-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="87c0c-126">**ContentGracePeriod**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define o tempo que o conteúdo da webconferência permanecerá no servidor após o término da reunião.</span><span class="sxs-lookup"><span data-stu-id="87c0c-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="87c0c-127">**MaxContentStorageMb**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define o valor máximo de espaço de arquivo permitido para o armazenamento de conteúdo durante uma única reunião.</span><span class="sxs-lookup"><span data-stu-id="87c0c-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="87c0c-128">**MaxUploadFileSizeMb** não limita a configuração de carregamento de arquivo do Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="87c0c-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="87c0c-129">O limite de carregamento do tamanho do arquivo do Lync Web App é definido como aproximadamente 30MB e é controlado pelo arquivo Web. config do\[IIS\]:/DataCollabWeb/int ext/Handler/Web.config. Para configurar o limite de carregamento de tamanho do arquivo para o Lync `maxRequestLength` Web `maxAllowedContentLength` app, atualize e no arquivo Web. config, como mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="87c0c-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="87c0c-130">Você deve atualizar o arquivo Web. config para cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="87c0c-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="87c0c-131">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="87c0c-131">Office Web Apps Server</span></span>

<span data-ttu-id="87c0c-132">Para usar esses novos recursos, os administradores devem instalar o Office Web Apps Server e devem configurar o Lync Server 2013 para se comunicar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="87c0c-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="87c0c-133">Esta documentação fornece informações sobre como configurar o Lync Server 2013 para trabalhar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="87c0c-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="87c0c-134">O que essa documentação não fornece é informações sobre como instalar o Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="87c0c-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="87c0c-135">Para obter detalhes sobre a instalação, consulte o site de implantação do <http://go.microsoft.com/fwlink/p/?linkid=257525>Microsoft Office Web Apps em.</span><span class="sxs-lookup"><span data-stu-id="87c0c-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="87c0c-136">Esse guia inclui informações completas de pré-requisito para o Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="87c0c-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="87c0c-137">Observe que o Office Web Apps Server deve ser instalado em um computador autônomo que não esteja executando o Lync Server, o SQL Server ou qualquer outro aplicativo de servidor.</span><span class="sxs-lookup"><span data-stu-id="87c0c-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="87c0c-138">(Você não deve ter qualquer versão do Office instalada nesse computador.) Qualquer computador usado para executar o Office Web Apps Server também deve ter um conjunto específico de softwares instalado (incluindo .NET Framework 4,5 e Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="87c0c-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="87c0c-139">Esses requisitos, juntamente com informações sobre a configuração de certificados e serviços de informações da Internet (IIS), são discutidos em detalhes no site de implantação <http://go.microsoft.com/fwlink/p/?linkid=257525>do Microsoft Office Web Apps em.</span><span class="sxs-lookup"><span data-stu-id="87c0c-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87c0c-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="87c0c-140">See Also</span></span>


[<span data-ttu-id="87c0c-141">Visão geral da Web conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87c0c-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="87c0c-142">Lista de verificação da implantação para Webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87c0c-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

