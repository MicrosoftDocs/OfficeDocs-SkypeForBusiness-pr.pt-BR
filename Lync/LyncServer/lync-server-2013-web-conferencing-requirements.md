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
ms.openlocfilehash: b75663f1e5bc51136ac0a2254944541716ad6f74
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="fc912-102">Requisitos de Webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc912-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc912-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="fc912-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="fc912-104">Se você optou por habilitar a webconferência, será necessário planejar:</span><span class="sxs-lookup"><span data-stu-id="fc912-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="fc912-105">O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.</span><span class="sxs-lookup"><span data-stu-id="fc912-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="fc912-106">Integração com o servidor do Office Web Apps, que é necessário para compartilhar arquivos do PowerPoint durante uma conferência.</span><span class="sxs-lookup"><span data-stu-id="fc912-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="fc912-107">Repositório de Arquivos</span><span class="sxs-lookup"><span data-stu-id="fc912-107">File Store</span></span>

<span data-ttu-id="fc912-108">O serviço de Webconferência do Lync Server 2013 armazena conteúdo compartilhado durante reuniões no repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc912-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="fc912-109">Como parte da implantação, você deve especificar um compartilhamento de arquivo a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de front-ends Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fc912-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="fc912-110">Você pode usar um repositório de arquivos existente ou pode especificar um novo compartilhamento de arquivos determinando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos em que o repositório estará localizado e um nome de pasta para o novo compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc912-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="fc912-111">Para mais informações, consulte Construtor de Topologias – Definir o Repositório de Arquivos para o Front End.</span><span class="sxs-lookup"><span data-stu-id="fc912-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="fc912-112">O serviço de webconferências criptografa o conteúdo antes de armazená-lo no repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc912-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="fc912-113">O Lync Server 2013 oferece suporte ao uso de compartilhamentos de arquivo em DAS (armazenamento de conexão direta) ou em uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e em uma matriz redundante de discos independentes (RAID) para repositórios de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc912-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="fc912-114">Após o assistente de implantação do Lync Server ter definido o local do compartilhamento de arquivos, o Lync Server cria uma estrutura de pastas dentro do compartilhamento de arquivos semelhante a:</span><span class="sxs-lookup"><span data-stu-id="fc912-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="fc912-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="fc912-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="fc912-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="fc912-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="fc912-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="fc912-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="fc912-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="fc912-118">CollabContent</span></span>
    
      - <span data-ttu-id="fc912-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="fc912-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="fc912-120">Dataconferência</span><span class="sxs-lookup"><span data-stu-id="fc912-120">DataConf</span></span>

<span data-ttu-id="fc912-121">O serviço de webconferências então armazena conteúdo como slides do PowerPoint, quadros de comunicações, votações e anexos nas pastas CollabContent e CollabMetadata, localizadas na pasta WebServices.</span><span class="sxs-lookup"><span data-stu-id="fc912-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="fc912-122">O administrador deve definir permissões no compartilhamento de arquivos para que grupos do RTC tenham o acesso de leitura e gravação necessário.</span><span class="sxs-lookup"><span data-stu-id="fc912-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fc912-p103">Se você encontrar erros com as permissões, abra o Construtor de Topologias, faça download e publique novamente a topologia existente. Publicar a topologia verificará as permissões do compartilhamento de arquivos e as redefinirá, se necessário.</span><span class="sxs-lookup"><span data-stu-id="fc912-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="fc912-125">Você pode usar as configurações a seguir para gerenciar como o conteúdo será armazenado para uma reunião:</span><span class="sxs-lookup"><span data-stu-id="fc912-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="fc912-126">**ContentGracePeriod**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define o quanto o conteúdo de webconferências permanecerá no servidor após o término da reunião.</span><span class="sxs-lookup"><span data-stu-id="fc912-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="fc912-127">**MaxContentStorageMb**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define a quantidade máxima de espaço de arquivo permitido para o armazenamento de conteúdo durante uma única reunião.</span><span class="sxs-lookup"><span data-stu-id="fc912-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="fc912-128">**MaxUploadFileSizeMb** não limita a configuração de carregamento de arquivo para o Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="fc912-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="fc912-129">O limite de carregamento de tamanho de arquivo para Lync Web App é definido como aproximadamente 30MB e é controlado pelo arquivo Web. config do\[IIS\]:/DataCollabWeb/int ext/Handler/Web.config. Para configurar o limite de carregamento de tamanho de arquivo do Lync Web `maxRequestLength` app `maxAllowedContentLength` , atualize e no arquivo Web. config, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="fc912-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="fc912-130">Você deve atualizar o arquivo Web. config para cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="fc912-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="fc912-131">Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="fc912-131">Office Web Apps Server</span></span>

<span data-ttu-id="fc912-132">Para usar esses novos recursos, os administradores devem instalar o Office Web Apps Server e devem configurar o Lync Server 2013 para se comunicar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="fc912-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="fc912-133">Esta documentação fornece informações sobre como configurar o Lync Server 2013 para funcionar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="fc912-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="fc912-134">O que esta documentação não fornece é informações sobre como instalar o Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="fc912-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="fc912-135">Para obter detalhes sobre a instalação, consulte o site de implantação do <https://go.microsoft.com/fwlink/p/?linkid=257525>Microsoft Office Web Apps em.</span><span class="sxs-lookup"><span data-stu-id="fc912-135">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="fc912-136">Esse guia inclui informações completas de pré-requisito para o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="fc912-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="fc912-137">Observe que o servidor do Office Web Apps deve ser instalado em um computador autônomo que não esteja executando o Lync Server, o SQL Server ou qualquer outro aplicativo de servidor.</span><span class="sxs-lookup"><span data-stu-id="fc912-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="fc912-138">(Você não deve ter nenhuma versão do Office instalada nesse computador.) Qualquer computador usado para executar o servidor do Office Web Apps também deve ter um conjunto específico de software instalado (incluindo o .NET Framework 4,5 e o Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="fc912-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="fc912-139">Esses requisitos, juntamente com as informações sobre a configuração de certificados e os serviços de informações da Internet (IIS), são discutidos em detalhes no site <https://go.microsoft.com/fwlink/p/?linkid=257525>de implantação do Microsoft Office Web Apps em.</span><span class="sxs-lookup"><span data-stu-id="fc912-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc912-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="fc912-140">See Also</span></span>


[<span data-ttu-id="fc912-141">Visão geral da webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc912-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="fc912-142">Lista de verificação de implantação para Webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc912-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

