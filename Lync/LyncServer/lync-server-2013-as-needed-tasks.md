---
title: 'Lync Server 2013: tarefas necessárias'
description: 'Lync Server 2013: tarefas necessárias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91fe249d9615bb619426c58b22606c3ef182f9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559997"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="74c5c-103">Tarefas necessárias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74c5c-103">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74c5c-104">_**Última modificação do tópico:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="74c5c-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="74c5c-105">Execute as seguintes tarefas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="74c5c-105">Perform the following tasks as necessary.</span></span> <span data-ttu-id="74c5c-106">Eles também são freqüentemente cobertos por procedimentos padrão:</span><span class="sxs-lookup"><span data-stu-id="74c5c-106">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="74c5c-107">**Auditoria de segurança completa   ** Você pode executar essa auditoria regularmente, em resposta a uma atualização ou reformulação do sistema de mensagens, ou em resposta a uma falha de segurança tentada (ou bem-sucedida).</span><span class="sxs-lookup"><span data-stu-id="74c5c-107">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="74c5c-108">O procedimento pode envolver verificações de porta em servidores e firewalls, auditorias de correções de segurança e testes de penetração de terceiros.</span><span class="sxs-lookup"><span data-stu-id="74c5c-108">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="74c5c-109">**Substituir certificados prestes a expirar**     A verificação de certificados do Lync Server é uma das tarefas periódicas regulares e, como parte do procedimento, um administrador deve ter um registro de todas as datas de vencimento dos certificados.</span><span class="sxs-lookup"><span data-stu-id="74c5c-109">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="74c5c-110">Este registro permite que um administrador crie uma notificação quando um determinado certificado estiver prestes a expirar e substituído conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="74c5c-110">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="74c5c-111">**Atualizando linhas de base**     de desempenho Atualize as linhas de base de desempenho após uma atualização ou alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="74c5c-111">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="74c5c-112">Sua organização pode usar linhas de base para medir as alterações de desempenho e detectar problemas que afetam o desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="74c5c-112">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="74c5c-113">**Gerenciando o pool corporativo**     A configuração inicial dos pools corporativos, dos servidores Standard Edition e de qualquer outro servidor no ambiente da organização foi feita durante a implantação dos servidores individuais.</span><span class="sxs-lookup"><span data-stu-id="74c5c-113">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="74c5c-114">O gerenciamento pós-implantação de servidores e pools para servidores Standard Edition e pools corporativos inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="74c5c-114">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="74c5c-115">Gerenciando servidores front-end</span><span class="sxs-lookup"><span data-stu-id="74c5c-115">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="74c5c-116">Gerenciando Webconferência</span><span class="sxs-lookup"><span data-stu-id="74c5c-116">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="74c5c-117">Gerenciando conferência</span><span class="sxs-lookup"><span data-stu-id="74c5c-117">Managing Conferencing</span></span>
    
      - <span data-ttu-id="74c5c-118">Alterar credenciais da conta de serviço</span><span class="sxs-lookup"><span data-stu-id="74c5c-118">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="74c5c-119">Gerenciando bancos de dados</span><span class="sxs-lookup"><span data-stu-id="74c5c-119">Managing Databases</span></span>
    
      - <span data-ttu-id="74c5c-120">Iniciar e interromper serviços e desativação de funções de servidor</span><span class="sxs-lookup"><span data-stu-id="74c5c-120">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="74c5c-121">Remover servidores e funções de servidor, remover pools e encerrar servidores e pools</span><span class="sxs-lookup"><span data-stu-id="74c5c-121">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="74c5c-122">**Gerenciando o uso**     Você pode configurar o Lync Server 2013 para fornecer os recursos e a funcionalidade mais adequados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="74c5c-122">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="74c5c-123">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="74c5c-123">This includes the following:</span></span>
    
      - <span data-ttu-id="74c5c-124">Gerenciando o suporte para reuniões da webconferência no local</span><span class="sxs-lookup"><span data-stu-id="74c5c-124">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="74c5c-125">Gerenciando o uso de grupos de distribuição para enviar mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="74c5c-125">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="74c5c-126">Gerenciando contatos, presença e consultas</span><span class="sxs-lookup"><span data-stu-id="74c5c-126">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="74c5c-127">Configurando a filtragem de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="74c5c-127">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="74c5c-128">Configurando a filtragem inteligente de IM</span><span class="sxs-lookup"><span data-stu-id="74c5c-128">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="74c5c-129">Configurando arquivamento, registro de detalhes das chamadas e conformidade da reunião</span><span class="sxs-lookup"><span data-stu-id="74c5c-129">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="74c5c-130">**Gerenciando a conectividade**     do servidor de borda O gerenciamento contínuo dos servidores e das configurações necessárias para fornecer conectividade externa inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74c5c-130">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="74c5c-131">Gerenciando a conectividade entre servidores internos e servidores de borda</span><span class="sxs-lookup"><span data-stu-id="74c5c-131">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="74c5c-132">Configurando interfaces e certificados internos e externos para servidores de borda</span><span class="sxs-lookup"><span data-stu-id="74c5c-132">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="74c5c-133">Gerenciando o acesso de parceiro federado</span><span class="sxs-lookup"><span data-stu-id="74c5c-133">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="74c5c-134">**Administrar o catálogo**     de endereços Administrar servidores de catálogo de endereços inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74c5c-134">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="74c5c-135">Configurando a normalização de telefone do servidor do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="74c5c-135">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="74c5c-136">Gerenciando o servidor de catálogo de endereços a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="74c5c-136">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="74c5c-137">**Gerenciando contas**     de usuário O gerenciamento de contas de usuário inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74c5c-137">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="74c5c-138">Habilitar contas de usuário para o Lync Server</span><span class="sxs-lookup"><span data-stu-id="74c5c-138">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="74c5c-139">Configurando usuários do Lync Server usando o assistente</span><span class="sxs-lookup"><span data-stu-id="74c5c-139">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="74c5c-140">Configurando propriedades individuais de contas de usuário do Lync Server</span><span class="sxs-lookup"><span data-stu-id="74c5c-140">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="74c5c-141">Pesquisando usuários do Lync Server</span><span class="sxs-lookup"><span data-stu-id="74c5c-141">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="74c5c-142">Movendo usuários do Lync Server</span><span class="sxs-lookup"><span data-stu-id="74c5c-142">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="74c5c-143">Excluir usuários do Lync Server</span><span class="sxs-lookup"><span data-stu-id="74c5c-143">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="74c5c-144">**Analisando arquivos**     de log do Lync Server 2013 Uma ferramenta muito útil, geralmente usada para solução de problemas, é a ferramenta de registro em log do Lync Server 2013 descrita em detalhes em [using Lync server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="74c5c-144">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="74c5c-145">Como a ferramenta de registro em log gera arquivos de log (em uma base por servidor), esses arquivos de log podem ser visualizados e analisados usando a ferramenta Snooper, se as ferramentas do Microsoft Office Server 12 Resource Kit estiverem instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="74c5c-145">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="74c5c-146">Caso contrário, os logs também podem ser analisados usando um editor de texto, que é muito menos transparente e mais complexo do que o uso do utilitário Snooper.</span><span class="sxs-lookup"><span data-stu-id="74c5c-146">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="74c5c-147">Para exibir e analisar mensagens de protocolo</span><span class="sxs-lookup"><span data-stu-id="74c5c-147">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="74c5c-148">Na ferramenta de log, depois de finalizar a sessão de depuração, clique em analisar arquivos de log para exibir os arquivos de log usando a ferramenta Snooper.</span><span class="sxs-lookup"><span data-stu-id="74c5c-148">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="74c5c-149">Você pode analisar os logs de protocolo para os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="74c5c-149">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="74c5c-150">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="74c5c-150">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="74c5c-151">S4 (SIP) do Lync Server</span><span class="sxs-lookup"><span data-stu-id="74c5c-151">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="74c5c-152">C3P (tráfego de sinalização de conferência do Lync Server), incluindo MCU-C3P e foco C3P</span><span class="sxs-lookup"><span data-stu-id="74c5c-152">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="74c5c-153">Tráfego de Webconferência do Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="74c5c-153">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="74c5c-154">Cliente de plataforma de comunicação unificada do Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="74c5c-154">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="74c5c-155">Relatórios de erro do banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="74c5c-155">Error reports from the archiving database</span></span>

<span data-ttu-id="74c5c-156">Para ajudar a organizar o desempenho das tarefas necessárias, confira As-Needed lista de verificação de operações.</span><span class="sxs-lookup"><span data-stu-id="74c5c-156">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74c5c-157">Para obter procedimentos detalhados de administração e gerenciamento, consulte o guia de administração do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74c5c-157">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="74c5c-158">Políticas de backup (e restauração) ou definições de configuração</span><span class="sxs-lookup"><span data-stu-id="74c5c-158">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="74c5c-159">O Lync Server 2013 permite fazer backup e restaurar todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="74c5c-159">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="74c5c-160">IIf que você deseja fazer backup (e, em seguida, pode ser uma restauração de algum dia) uma única política ou uma única coleção de definições de configuração, recuperar a política apropriada e, em seguida, canalizar esse objeto para o cmdlet Export-Clixml, que salva as informações de política como um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="74c5c-160">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="74c5c-161">Agora você pode experimentar o RedmondClientPolicy e alterar muitas das configurações.</span><span class="sxs-lookup"><span data-stu-id="74c5c-161">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="74c5c-162">Se decidir em vez de restaurar a política antiga, digite:</span><span class="sxs-lookup"><span data-stu-id="74c5c-162">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="74c5c-163">Observe que essa abordagem funcionará para a maioria das políticas e configurações, mas não funcionará com alguns dos itens mais complexos, os itens que contêm vários subobjetos (como configurações de roteamento, que contêm muitas rotas de voz separadas).</span><span class="sxs-lookup"><span data-stu-id="74c5c-163">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

