---
title: Lista de verificação de implantação do Lync Server 2013 para conferência A/V
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
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="eae46-102">Lista de verificação de implantação para conferência A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae46-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae46-103">_**Tópico da última modificação:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="eae46-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="eae46-104">Assim como com a implantação de outros componentes do Lync Server 2013, A implantação de uma conferência A/V requer que você use o construtor de topologias para criar e publicar uma topologia que incorpora conferências.</span><span class="sxs-lookup"><span data-stu-id="eae46-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="eae46-105">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="eae46-105">Deployment Sequence</span></span>

<span data-ttu-id="eae46-106">Você pode implantar conferências ao mesmo tempo em que implantar a sua topologia inicial ou depois de implantar pelo menos um pool de front-end ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="eae46-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="eae46-107">Processo de implantação de conferência</span><span class="sxs-lookup"><span data-stu-id="eae46-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="eae46-108">A tabela a seguir fornece uma visão geral das etapas necessárias para implantar a conferência em uma topologia existente.</span><span class="sxs-lookup"><span data-stu-id="eae46-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eae46-109">Fase</span><span class="sxs-lookup"><span data-stu-id="eae46-109">Phase</span></span></th>
<th><span data-ttu-id="eae46-110">Etapas</span><span class="sxs-lookup"><span data-stu-id="eae46-110">Steps</span></span></th>
<th><span data-ttu-id="eae46-111">Funções e associações de grupo</span><span class="sxs-lookup"><span data-stu-id="eae46-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="eae46-112">Documentação</span><span class="sxs-lookup"><span data-stu-id="eae46-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eae46-113"><strong>Instalar pré-requisitos de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="eae46-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="eae46-114">A conferência é executada em servidores front-end de um pool de front-end e servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="eae46-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="eae46-115">Não há requisitos adicionais de hardware ou software além daqueles necessários para instalar esses servidores.</span><span class="sxs-lookup"><span data-stu-id="eae46-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="eae46-116">O Lync Server 2013 usa o Office Web Apps e o Office Web Apps Server para lidar com o compartilhamento e a renderização de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="eae46-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="eae46-117">Para obter detalhes sobre como instalar e configurar o Office Web Apps Server, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o Office Web Apps Server e o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eae46-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="eae46-118">Domínio do usuário que é membro do grupo local de Administradores</span><span class="sxs-lookup"><span data-stu-id="eae46-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="eae46-119"><a href="lync-server-2013-supported-hardware.md">Hardware com suporte para o Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="eae46-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="eae46-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte de software e infraestrutura do servidor no Lync Server 2013</a> na documentação de suporte</span><span class="sxs-lookup"><span data-stu-id="eae46-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="eae46-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determinação dos requisitos do sistema para o Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="eae46-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="eae46-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="eae46-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae46-123"><strong>Crie a topologia interna apropriada para dar suporte à conferência</strong></span><span class="sxs-lookup"><span data-stu-id="eae46-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="eae46-124">Execute o construtor de topologias para adicionar conferências à topologia e, em seguida, publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="eae46-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="eae46-125">Para definir a topologia, uma conta que é membro do grupo local de Usuários</span><span class="sxs-lookup"><span data-stu-id="eae46-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="eae46-126">Para publicar a topologia, uma conta que é membro do grupo Domain admins e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivos a ser usado para o repositório de arquivos do Lync Server 2013 (para que o construtor de topologias possa configurar as DACLs necessárias)</span><span class="sxs-lookup"><span data-stu-id="eae46-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="eae46-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Defina e configure uma topologia no construtor de topologias para o Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="eae46-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae46-128"><strong>Configurar políticas de conferência e suporte</strong></span><span class="sxs-lookup"><span data-stu-id="eae46-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="eae46-129">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de conferência.</span><span class="sxs-lookup"><span data-stu-id="eae46-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="eae46-130">Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribuir usuários à função [] ou CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="eae46-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="eae46-131"><a href="lync-server-2013-conferencing-policies.md">Políticas de conferência no Lync Server 2013</a> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="eae46-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eae46-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="eae46-132">See Also</span></span>


[<span data-ttu-id="eae46-133">Visão geral de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae46-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="eae46-134">Definindo seus requisitos para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae46-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

