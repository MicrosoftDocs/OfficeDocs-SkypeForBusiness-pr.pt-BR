---
title: 'Lync Server 2013: Lista de verificação da implantação para Arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="6bb33-102">Lista de verificação da implantação para Arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bb33-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bb33-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6bb33-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6bb33-104">O arquivamento é instalado automaticamente em cada servidor front-end na implantação do Lync Server 2013, mas você ainda precisa configurá-lo para poder usá-lo.</span><span class="sxs-lookup"><span data-stu-id="6bb33-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="6bb33-105">As etapas necessárias para configurá-lo, conforme resumido nesta seção, constituem a implantação do arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6bb33-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="6bb33-106">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="6bb33-106">Deployment Sequence</span></span>

<span data-ttu-id="6bb33-107">A forma de configurar o arquivamento depende da opção de armazenamento que você escolher:</span><span class="sxs-lookup"><span data-stu-id="6bb33-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="6bb33-108">Se você usa a integração do Microsoft Exchange para todos os usuários na sua implantação, não é necessário configurar as políticas de arquivamento do Lync Server 2013 para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="6bb33-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="6bb33-109">Em vez disso, configure suas políticas de bloqueio in-loco do Exchange para dar suporte ao arquivamento para usuários hospedados no Exchange 2013, com as caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="6bb33-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="6bb33-110">Para obter detalhes sobre como configurar essas políticas, consulte a documentação do produto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6bb33-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="6bb33-111">Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, será necessário adicionar bancos de dados de arquivamento do Lync Server (bancos de dados do SQL Server) à sua topologia e publicá-la, além de definir políticas e configurações para seus usuários, antes que você possa arquivar dados para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="6bb33-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="6bb33-112">Você pode implantar bancos de dados de arquivamento ao mesmo tempo em que implanta sua topologia inicial ou depois de implantar pelo menos um pool de front-end ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6bb33-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="6bb33-113">Este documento descreve como implantar bancos de dados de arquivamento adicionando-os a uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="6bb33-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="6bb33-114">Se você habilitar o arquivamento em um pool de front-end ou em um servidor Standard Edition, habilite-o para todos os outros pools front-ends e servidores Standard Edition na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="6bb33-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="6bb33-115">Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados para grupos de conversa via IM ou reuniões hospedadas em um pool diferente.</span><span class="sxs-lookup"><span data-stu-id="6bb33-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="6bb33-116">Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada.</span><span class="sxs-lookup"><span data-stu-id="6bb33-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="6bb33-117">Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivadas, mas não arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.</span><span class="sxs-lookup"><span data-stu-id="6bb33-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6bb33-118">Se o arquivamento for fundamental para a sua organização por motivos de conformidade, certifique-se de implantar o arquivamento, configurar políticas e outras opções no nível apropriado e habilitá-la para todos os usuários apropriados antes de habilitar esses usuários para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6bb33-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="6bb33-119">Processo de implantação de arquivamento</span><span class="sxs-lookup"><span data-stu-id="6bb33-119">Archiving Deployment Process</span></span>

<span data-ttu-id="6bb33-120">A tabela a seguir fornece uma visão geral das etapas necessárias para implantar o arquivamento em uma topologia existente.</span><span class="sxs-lookup"><span data-stu-id="6bb33-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bb33-121">Fase</span><span class="sxs-lookup"><span data-stu-id="6bb33-121">Phase</span></span></th>
<th><span data-ttu-id="6bb33-122">Etapas</span><span class="sxs-lookup"><span data-stu-id="6bb33-122">Steps</span></span></th>
<th><span data-ttu-id="6bb33-123">Funções e associações de grupo</span><span class="sxs-lookup"><span data-stu-id="6bb33-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="6bb33-124">Documentação</span><span class="sxs-lookup"><span data-stu-id="6bb33-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bb33-125"><strong>Instalar pré-requisitos de hardware e software</strong></span><span class="sxs-lookup"><span data-stu-id="6bb33-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6bb33-126">Para usar a integração do Microsoft Exchange (usando o Exchange 2013 para arquivar o armazenamento para alguns ou todos os usuários), você precisa de uma implantação existente do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6bb33-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="6bb33-127">Para usar bancos de dados de arquivamento separados (usando bancos de dados do SQL Server) para arquivar o armazenamento para alguns ou todos os usuários, SQL Server no servidor que armazenará os dados do arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6bb33-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="6bb33-128">O arquivamento é executado em servidores front-end de um pool corporativo e servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6bb33-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="6bb33-129">Não há requisitos adicionais de hardware ou software além daqueles necessários para instalar esses servidores.</span><span class="sxs-lookup"><span data-stu-id="6bb33-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="6bb33-130">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="6bb33-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="6bb33-131"><a href="lync-server-2013-supported-hardware.md">Hardware com suporte para o Lync Server 2013</a> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="6bb33-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="6bb33-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte de software e infraestrutura do servidor no Lync Server 2013</a> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="6bb33-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="6bb33-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="6bb33-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="6bb33-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar sistemas e infraestrutura para arquivamento no Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6bb33-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="6bb33-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Suporte à integração do Exchange Server e do SharePoint no Lync server 2013</a> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="6bb33-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb33-136"><strong>Criar a topologia interna apropriada para dar suporte ao arquivamento (apenas se não estiver usando a integração do Microsoft Exchange para todos os usuários em sua implantação)</strong></span><span class="sxs-lookup"><span data-stu-id="6bb33-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb33-137">Execute o construtor de topologias para adicionar bancos de dados de arquivamento do Lync Server 2013 (bancos de dados do SQL Server) à topologia e, em seguida, publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="6bb33-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="6bb33-138">Para definir uma topologia para incorporar bancos de dados de arquivamento, uma conta que seja membro do grupo usuários local.</span><span class="sxs-lookup"><span data-stu-id="6bb33-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="6bb33-139">Para publicar a topologia, uma conta que é membro do grupo Domain admins e do grupo RTCUniversalServerAdmins, e que tem permissões de controle total (leitura/gravação/modificação) no compartilhamento de arquivos a ser usado para o repositório de arquivos do Lync Server 2013 (para que o construtor de topologias possa configurar as DACLs obrigatórias).</span><span class="sxs-lookup"><span data-stu-id="6bb33-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="6bb33-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adicionar bancos de dados de arquivamento a uma implantação existente do Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6bb33-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb33-141"><strong>Configurar a autenticação do servidor para o servidor (somente se estiver usando a integração do Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="6bb33-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb33-142">Configurar servidores para habilitar a autenticação entre o Lync Server 2013 e o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6bb33-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="6bb33-143">Recomendamos executar <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – diretório dumpster</strong> para validar a conectividade do armazenamento do Exchange Archiving antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6bb33-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="6bb33-144">Uma conta com permissões adequadas para gerenciar certificados nos servidores.</span><span class="sxs-lookup"><span data-stu-id="6bb33-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="6bb33-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gerenciamento de autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013</a> na documentação de implantação ou na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="6bb33-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb33-146"><strong>Configurar políticas e configurações de arquivamento</strong></span><span class="sxs-lookup"><span data-stu-id="6bb33-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb33-147">Configurar o arquivamento, incluindo se a integração do Microsoft Exchange, a política global e as políticas de usuário e de qualquer site (quando não estão sendo usadas na integração do Microsoft Exchange para todos os dados) e opções de arquivamento específicas, como dados e modo crítico exportar e descartar.</span><span class="sxs-lookup"><span data-stu-id="6bb33-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="6bb33-148">Se estiver usando a integração do Microsoft Exchange, configure as políticas de bloqueio do Exchange in-loco conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="6bb33-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="6bb33-149">Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6bb33-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="6bb33-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuração do suporte para arquivamento no Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6bb33-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="6bb33-151">Documentação do produto Exchange (se estiver usando a integração do Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="6bb33-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="6bb33-152">Implantar o Lync Server e o Microsoft Exchange em florestas diferentes</span><span class="sxs-lookup"><span data-stu-id="6bb33-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="6bb33-153">Se o Microsoft Exchange Server não for implantado na mesma floresta do Lync Server, você deve verificar se os seguintes atributos do Active Directory do Exchange estão sincronizados com a floresta onde o Lync Server está implantado:</span><span class="sxs-lookup"><span data-stu-id="6bb33-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="6bb33-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6bb33-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="6bb33-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6bb33-155">proxyAddresses</span></span>

<span data-ttu-id="6bb33-p107">Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.</span><span class="sxs-lookup"><span data-stu-id="6bb33-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

