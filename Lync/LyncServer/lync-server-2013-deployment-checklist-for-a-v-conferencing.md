---
title: Lync Server 2013 lista de verificação de implantação para conferência A/V
description: Lync Server 2013 lista de verificação de implantação para conferência A/V.
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
ms.openlocfilehash: d9a4584172ed4c01eb163ea51aa4f62c2ce75185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557767"
---
# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="fcda8-103">Lista de verificação de implantação para conferência A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcda8-103">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcda8-104">_**Última modificação do tópico:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="fcda8-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="fcda8-105">Assim como a implantação de outros componentes do Lync Server 2013, A implantação de conferência A/V requer que você use o construtor de topologias para criar e publicar uma topologia que incorpore a conferência.</span><span class="sxs-lookup"><span data-stu-id="fcda8-105">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="fcda8-106">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="fcda8-106">Deployment Sequence</span></span>

<span data-ttu-id="fcda8-107">Você pode implantar a conferência ao mesmo tempo em que implanta a topologia inicial ou após implantar pelo menos um pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fcda8-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="fcda8-108">Processo de implantação de conferências</span><span class="sxs-lookup"><span data-stu-id="fcda8-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="fcda8-109">A tabela a seguir fornece uma visão geral das etapas necessárias para implantar conferências em uma topologia existente.</span><span class="sxs-lookup"><span data-stu-id="fcda8-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcda8-110">Fase</span><span class="sxs-lookup"><span data-stu-id="fcda8-110">Phase</span></span></th>
<th><span data-ttu-id="fcda8-111">Etapas</span><span class="sxs-lookup"><span data-stu-id="fcda8-111">Steps</span></span></th>
<th><span data-ttu-id="fcda8-112">Associações a grupos e funções</span><span class="sxs-lookup"><span data-stu-id="fcda8-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="fcda8-113">Documentação</span><span class="sxs-lookup"><span data-stu-id="fcda8-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcda8-114"><strong>Instalar pré-requisitos de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="fcda8-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="fcda8-115">A conferência é executada em servidores front-end de um pool de front-ends e servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fcda8-115">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="fcda8-116">Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.</span><span class="sxs-lookup"><span data-stu-id="fcda8-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fcda8-117">O Lync Server 2013 usa o Office Web Apps e o servidor do Office Web Apps para lidar com o compartilhamento e a renderização de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="fcda8-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="fcda8-118">Para obter detalhes sobre como instalar e configurar o servidor do Office Web Apps, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fcda8-118">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="fcda8-119">Usuário do domínio que é membro do grupo local de Administradores</span><span class="sxs-lookup"><span data-stu-id="fcda8-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="fcda8-120"><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="fcda8-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="fcda8-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="fcda8-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="fcda8-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determinando os requisitos do sistema para o Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fcda8-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="fcda8-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fcda8-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcda8-124"><strong>Crie a topologia interna apropriada para dar suporte a conferências</strong></span><span class="sxs-lookup"><span data-stu-id="fcda8-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="fcda8-125">Execute o construtor de topologias para adicionar a conferência à topologia e, em seguida, publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="fcda8-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="fcda8-126">Para definir a topologia, uma conta que é membro do grupo local de Usuários</span><span class="sxs-lookup"><span data-stu-id="fcda8-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="fcda8-127">Para publicar a topologia, uma conta que é membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivo a ser usado para o repositório de arquivos do Lync Server 2013 (de modo que o construtor de topologias possa configurar as DACLs necessárias)</span><span class="sxs-lookup"><span data-stu-id="fcda8-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="fcda8-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definir e configurar uma topologia no construtor de topologias para o Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fcda8-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcda8-129"><strong>Configurar políticas e suporte de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="fcda8-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="fcda8-130">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de conferência.</span><span class="sxs-lookup"><span data-stu-id="fcda8-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="fcda8-131">Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribuir usuários à função [] ou CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="fcda8-131">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="fcda8-132"><a href="lync-server-2013-conferencing-policies.md">Políticas de conferência no Lync Server 2013</a> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="fcda8-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fcda8-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="fcda8-133">See Also</span></span>


[<span data-ttu-id="fcda8-134">Visão geral da conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcda8-134">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="fcda8-135">Definindo seus requisitos de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcda8-135">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

