---
title: 'Lync Server 2013: lista de verificação de implantação para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2df74bda74f1b9af01e1c4e73fa2f21b7119363f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="fb76f-102">Lista de verificação de implantação para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb76f-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb76f-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fb76f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fb76f-104">O arquivamento é instalado automaticamente em cada servidor de front-end em sua implantação do Lync Server 2013, mas você ainda precisa configurá-lo antes de usá-lo.</span><span class="sxs-lookup"><span data-stu-id="fb76f-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="fb76f-105">As etapas necessário para configurá-lo (resumidas nesta seção) constituem a implantação do Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="fb76f-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="fb76f-106">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="fb76f-106">Deployment Sequence</span></span>

<span data-ttu-id="fb76f-107">O modo de configuração do Arquivamento depende da opção de armazenamento escolhida:</span><span class="sxs-lookup"><span data-stu-id="fb76f-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="fb76f-108">Se você usar a integração do Microsoft Exchange para todos os usuários em sua implantação, não será necessário configurar as políticas de arquivamento do Lync Server 2013 para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="fb76f-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="fb76f-109">Em vez disso, configure suas políticas de bloqueio in-loco do Exchange para dar suporte ao arquivamento para usuários hospedados no Exchange 2013, com suas caixas de correio colocadas em bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="fb76f-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="fb76f-110">Para obter detalhes sobre como configurar essas políticas, consulte a documentação do produto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="fb76f-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="fb76f-111">Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, será necessário adicionar bancos de dados de arquivamento do Lync Server (bancos de dados do SQL Server) à sua topologia e publicá-lo, além de configurar políticas e configurações para seus usuários, antes de poder arquivar dados para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="fb76f-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="fb76f-112">Você pode implantar os bancos de dados de Arquivamento ao mesmo tempo em que implanta a topologia inicial ou após implantar pelo menos um pool front-end ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fb76f-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="fb76f-113">Este documento descreve como implantar os bancos de dados de Arquivamento adicionando-os a uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="fb76f-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="fb76f-p104">Se você habilitar o arquivamento em um pool de Front-Ends ou em um servidor Standard Edition, você deve habilitá-lo em todos os pools e servidores de mesmo tipo na sua implantação. Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados a um grupo de conversação de IM ou a reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada. Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivados, menos para arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.</span><span class="sxs-lookup"><span data-stu-id="fb76f-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fb76f-118">Se o arquivamento for crucial na sua organização por motivos de conformidade, certifique-se de implantar o arquivamento, configurar políticas e outras opções no nível apropriado e habilitá-lo para todos os usuários apropriados antes de habilitar esses usuários para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb76f-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="fb76f-119">Processo de implantação do Arquivamento</span><span class="sxs-lookup"><span data-stu-id="fb76f-119">Archiving Deployment Process</span></span>

<span data-ttu-id="fb76f-120">A tabela a seguir fornece uma visão geral das etapas necessárias para implantar o arquivamento em uma topologia existente.</span><span class="sxs-lookup"><span data-stu-id="fb76f-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb76f-121">Fase</span><span class="sxs-lookup"><span data-stu-id="fb76f-121">Phase</span></span></th>
<th><span data-ttu-id="fb76f-122">Etapas</span><span class="sxs-lookup"><span data-stu-id="fb76f-122">Steps</span></span></th>
<th><span data-ttu-id="fb76f-123">Associações a grupos e funções</span><span class="sxs-lookup"><span data-stu-id="fb76f-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="fb76f-124">Documentação</span><span class="sxs-lookup"><span data-stu-id="fb76f-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb76f-125"><strong>Instalar pré-requisitos de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="fb76f-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fb76f-126">Para usar a integração do Microsoft Exchange (usando o Exchange 2013 para armazenamento de arquivamento para alguns ou todos os usuários), você precisa de uma implantação existente do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="fb76f-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="fb76f-127">Para usar bancos de dados de Arquivamento separados (usando bancos de dados do SQL Server) para armazenamento de arquivamento para alguns ou todos os usuários, SQL Server no servidor que armazenará os dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="fb76f-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="fb76f-p105">O Arquivamento é executado nos servidores front-end de um pool Enterprise e servidores Standard Edition. Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.</span><span class="sxs-lookup"><span data-stu-id="fb76f-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="fb76f-130">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="fb76f-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="fb76f-131"><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="fb76f-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="fb76f-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="fb76f-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="fb76f-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fb76f-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="fb76f-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar sistemas e infraestrutura para arquivamento no Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fb76f-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="fb76f-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Suporte à integração do Exchange Server e do SharePoint no Lync Server 2013</a> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="fb76f-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb76f-136"><strong>Crie a topologia interna apropriada para oferecer suporte ao arquivamento (apenas se não estiver usando a integração do Microsoft Exchange para todos os usuários em sua implantação)</strong></span><span class="sxs-lookup"><span data-stu-id="fb76f-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="fb76f-137">Execute o construtor de topologias para adicionar bancos de dados de arquivamento do Lync Server 2013 (bancos de dados do SQL Server) à topologia e, em seguida, publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="fb76f-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="fb76f-138">Para definir a topologia a fim de incorporar bancos de dados de Arquivamento, uma conta que é membro do grupo local de usuários.</span><span class="sxs-lookup"><span data-stu-id="fb76f-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="fb76f-139">Para publicar a topologia, uma conta que é membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivo a ser usado para o repositório de arquivos do Lync Server 2013 (de modo que o construtor de topologias possa configurar as DACLs necessárias).</span><span class="sxs-lookup"><span data-stu-id="fb76f-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="fb76f-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adicionar bancos de dados de arquivamento a uma implantação existente do Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fb76f-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb76f-141"><strong>Configurar a autenticação de servidor para servidor (somente se estiver usando a integração com o Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="fb76f-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="fb76f-142">Configure os servidores para habilitar a autenticação entre o Lync Server 2013 e o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="fb76f-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="fb76f-143">Recomendamos executar <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – Folder dumpster</strong> para validar a conectividade de armazenamento de arquivamento do Exchange antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="fb76f-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="fb76f-144">Uma conta com permissões adequadas para gerenciar certificados nos servidores.</span><span class="sxs-lookup"><span data-stu-id="fb76f-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="fb76f-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gerenciamento de autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013</a> na documentação de implantação ou na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="fb76f-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb76f-146"><strong>Definir políticas e configurações de arquivamento</strong></span><span class="sxs-lookup"><span data-stu-id="fb76f-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="fb76f-147">Configure o arquivamento, incluindo se deve usar a integração do Microsoft Exchange, a política global e as políticas de site e de usuário (quando não estiver usando a integração do Microsoft Exchange para todos os armazenamentos de dados) e opções de arquivamento específicas, como o modo crítico e os dados exportação e limpeza.</span><span class="sxs-lookup"><span data-stu-id="fb76f-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="fb76f-148">Se estiver usando a integração com o Microsoft Exchange, configure as políticas de bloqueio in-loco do Exchange conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="fb76f-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="fb76f-149">Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fb76f-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="fb76f-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configurando o suporte para arquivamento no Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fb76f-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="fb76f-151">Documentação do produto Exchange (se estiver usando a integração com o Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="fb76f-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="fb76f-152">Implantando o Lync Server e o Microsoft Exchange em diferentes florestas</span><span class="sxs-lookup"><span data-stu-id="fb76f-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="fb76f-153">Se o Microsoft Exchange Server não estiver implantado na mesma floresta do Lync Server, você deverá verificar se os seguintes atributos do Active Directory do Exchange estão sincronizados com a floresta onde o Lync Server está implantado:</span><span class="sxs-lookup"><span data-stu-id="fb76f-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="fb76f-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="fb76f-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="fb76f-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="fb76f-155">proxyAddresses</span></span>

<span data-ttu-id="fb76f-p107">Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.</span><span class="sxs-lookup"><span data-stu-id="fb76f-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

