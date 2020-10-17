---
title: Lync Server 2013 lista de verificação de implantação para Webconferência
description: Lync Server 2013 lista de verificação de implantação para Webconferência.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6194cb71af268a45dc5c142c1814d8c1ef15c09e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562177"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="670b4-103">Lista de verificação de implantação para Webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="670b4-103">Deployment checklist for web conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="670b4-104">_**Última modificação do tópico:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="670b4-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="670b4-105">Assim como a implantação de outros componentes do Lync Server 2013, a implantação de Webconferência requer que você use o construtor de topologias para criar e publicar uma topologia que incorpore a conferência.</span><span class="sxs-lookup"><span data-stu-id="670b4-105">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="670b4-106">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="670b4-106">Deployment Sequence</span></span>

<span data-ttu-id="670b4-107">Você pode implantar a conferência ao mesmo tempo em que implanta a topologia inicial ou após implantar pelo menos um pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="670b4-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="670b4-108">Processo de implantação de conferências</span><span class="sxs-lookup"><span data-stu-id="670b4-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="670b4-109">A tabela a seguir fornece uma visão geral das etapas necessárias para implantar conferências em uma topologia existente.</span><span class="sxs-lookup"><span data-stu-id="670b4-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="670b4-110">Fase</span><span class="sxs-lookup"><span data-stu-id="670b4-110">Phase</span></span></th>
<th><span data-ttu-id="670b4-111">Etapas</span><span class="sxs-lookup"><span data-stu-id="670b4-111">Steps</span></span></th>
<th><span data-ttu-id="670b4-112">Associações a grupos e funções</span><span class="sxs-lookup"><span data-stu-id="670b4-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="670b4-113">Documentação</span><span class="sxs-lookup"><span data-stu-id="670b4-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="670b4-114"><strong>Instalar pré-requisitos de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="670b4-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="670b4-115">A conferência é executada em servidores front-end em um pool de front-ends e servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="670b4-115">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="670b4-116">Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.</span><span class="sxs-lookup"><span data-stu-id="670b4-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="670b4-117">O Lync Server 2013 usa o Office Web Apps e o servidor do Office Web Apps para lidar com o compartilhamento e a renderização de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="670b4-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="670b4-118">Para obter informações sobre como instalar e configurar o servidor do Office Web Apps, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="670b4-118">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="670b4-119">Usuário do domínio que é membro do grupo local de Administradores</span><span class="sxs-lookup"><span data-stu-id="670b4-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="670b4-120"><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="670b4-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="670b4-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="670b4-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="670b4-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determinando os requisitos do sistema para o Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="670b4-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="670b4-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="670b4-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="670b4-124"><strong>Crie a topologia interna apropriada para dar suporte a conferências</strong></span><span class="sxs-lookup"><span data-stu-id="670b4-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="670b4-125">Execute o construtor de topologias para adicionar a conferência à topologia e, em seguida, publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="670b4-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="670b4-126">Para definir a topologia, uma conta que é membro do grupo local de Usuários</span><span class="sxs-lookup"><span data-stu-id="670b4-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="670b4-127">Para publicar a topologia, uma conta que é membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivo a ser usado para o repositório de arquivos do Lync Server 2013 (de modo que o construtor de topologias possa configurar as DACLs necessárias)</span><span class="sxs-lookup"><span data-stu-id="670b4-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="670b4-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definir e configurar uma topologia no construtor de topologias para o Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="670b4-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="670b4-129"><strong>Configurar políticas e suporte de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="670b4-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="670b4-130">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de conferência.</span><span class="sxs-lookup"><span data-stu-id="670b4-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="670b4-131">Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribuir usuários à função [] ou CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="670b4-131">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="670b4-132"><a href="lync-server-2013-conferencing-policies.md">Políticas de conferência no Lync Server 2013</a> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="670b4-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="670b4-133">O Lync Server 2013 agora inclui a configuração **MaxUploadFileSizeMb** , que limita o tamanho dos arquivos que podem ser carregados durante uma reunião.</span><span class="sxs-lookup"><span data-stu-id="670b4-133">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="670b4-134">O valor padrão para essa configuração é 500 MB.</span><span class="sxs-lookup"><span data-stu-id="670b4-134">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="670b4-135">Você pode ajustar **MaxUploadFileSizeMb** usando o cmdlet **set-CsConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="670b4-135">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="670b4-136">**MaxUploadFileSizeMb** não limita a configuração de carregamento de arquivo para o Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="670b4-136">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="670b4-137">O limite de carregamento de tamanho de arquivo para Lync Web App é definido como aproximadamente 30MB e é controlado pelo arquivo de web.config do IIS:/DataCollabWeb/Int \[ ext \] /Handler/web.config. Para configurar o limite de carregamento de tamanho de arquivo do Lync Web App, atualize `maxRequestLength` e `maxAllowedContentLength` no arquivo web.config conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="670b4-137">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="670b4-138">Você deve atualizar o arquivo de web.config para cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="670b4-138">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

