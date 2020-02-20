---
title: Lync Server 2013 lista de verificação de implantação para conferência A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e65aa993dcfaf27a04e870330300f2fc0cbf8113
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="3d1f8-102">Lista de verificação de implantação para conferência A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1f8-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d1f8-103">_**Última modificação do tópico:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="3d1f8-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="3d1f8-104">Assim como a implantação de outros componentes do Lync Server 2013, A implantação de conferência A/V requer que você use o construtor de topologias para criar e publicar uma topologia que incorpore a conferência.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="3d1f8-105">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="3d1f8-105">Deployment Sequence</span></span>

<span data-ttu-id="3d1f8-106">Você pode implantar a conferência ao mesmo tempo em que implanta a topologia inicial ou após implantar pelo menos um pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="3d1f8-107">Processo de implantação de conferências</span><span class="sxs-lookup"><span data-stu-id="3d1f8-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="3d1f8-108">A tabela a seguir fornece uma visão geral das etapas necessárias para implantar conferências em uma topologia existente.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d1f8-109">Fase</span><span class="sxs-lookup"><span data-stu-id="3d1f8-109">Phase</span></span></th>
<th><span data-ttu-id="3d1f8-110">Etapas</span><span class="sxs-lookup"><span data-stu-id="3d1f8-110">Steps</span></span></th>
<th><span data-ttu-id="3d1f8-111">Associações a grupos e funções</span><span class="sxs-lookup"><span data-stu-id="3d1f8-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="3d1f8-112">Documentação</span><span class="sxs-lookup"><span data-stu-id="3d1f8-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d1f8-113"><strong>Instalar pré-requisitos de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="3d1f8-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="3d1f8-114">A conferência é executada em servidores front-end de um pool de front-ends e servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="3d1f8-115">Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3d1f8-116">O Lync Server 2013 usa o Office Web Apps e o servidor do Office Web Apps para lidar com o compartilhamento e a renderização de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="3d1f8-117">Para obter detalhes sobre como instalar e configurar o servidor do Office Web Apps, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="3d1f8-118">Usuário do domínio que é membro do grupo local de Administradores</span><span class="sxs-lookup"><span data-stu-id="3d1f8-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="3d1f8-119"><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="3d1f8-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="3d1f8-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="3d1f8-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="3d1f8-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determinando os requisitos do sistema para o Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="3d1f8-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d1f8-123"><strong>Crie a topologia interna apropriada para dar suporte a conferências</strong></span><span class="sxs-lookup"><span data-stu-id="3d1f8-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="3d1f8-124">Execute o construtor de topologias para adicionar a conferência à topologia e, em seguida, publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="3d1f8-125">Para definir a topologia, uma conta que é membro do grupo local de Usuários</span><span class="sxs-lookup"><span data-stu-id="3d1f8-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="3d1f8-126">Para publicar a topologia, uma conta que é membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivo a ser usado para o repositório de arquivos do Lync Server 2013 (de modo que o construtor de topologias possa configurar as DACLs necessárias)</span><span class="sxs-lookup"><span data-stu-id="3d1f8-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="3d1f8-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definir e configurar uma topologia no construtor de topologias para o Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d1f8-128"><strong>Configurar políticas e suporte de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="3d1f8-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="3d1f8-129">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de conferência.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="3d1f8-130">Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribuir usuários à função [] ou CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d1f8-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="3d1f8-131"><a href="lync-server-2013-conferencing-policies.md">Políticas de conferência no Lync Server 2013</a> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d1f8-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="3d1f8-132">See Also</span></span>


[<span data-ttu-id="3d1f8-133">Visão geral da conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1f8-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="3d1f8-134">Definindo seus requisitos de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1f8-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

