---
title: 'Lync Server 2013: tarefas necessárias'
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
ms.openlocfilehash: 67a0355d32e5e704d6609335c82f8cfe1fe7aa86
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="5752f-102">Tarefas necessárias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5752f-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5752f-103">_**Última modificação do tópico:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="5752f-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="5752f-104">Execute as seguintes tarefas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5752f-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="5752f-105">Eles também são freqüentemente cobertos por procedimentos padrão:</span><span class="sxs-lookup"><span data-stu-id="5752f-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="5752f-106">**Auditoria de segurança completa   ** Você pode executar essa auditoria regularmente, em resposta a uma atualização ou reformulação do sistema de mensagens, ou em resposta a uma falha de segurança tentada (ou bem-sucedida).</span><span class="sxs-lookup"><span data-stu-id="5752f-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="5752f-107">O procedimento pode envolver verificações de porta em servidores e firewalls, auditorias de correções de segurança e testes de penetração de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5752f-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="5752f-108">**Substituir certificados prestes a**   verificar se a validade de certificados do Lync Server é uma das tarefas semanais regulares e, como parte do procedimento, um administrador deve ter um registro de todas as datas de vencimento dos certificados.</span><span class="sxs-lookup"><span data-stu-id="5752f-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="5752f-109">Este registro permite que um administrador crie uma notificação quando um determinado certificado estiver prestes a expirar e substituído conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5752f-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="5752f-110">**Atualizando linhas de base de desempenho**   atualizar as linhas de base após uma atualização ou alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="5752f-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="5752f-111">Sua organização pode usar linhas de base para medir as alterações de desempenho e detectar problemas que afetam o desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="5752f-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="5752f-112">**Gerenciar**   a configuração inicial do pool corporativo de pools corporativos, servidores Standard Edition e quaisquer outros servidores no ambiente da sua organização foram feitos durante a implantação dos servidores individuais.</span><span class="sxs-lookup"><span data-stu-id="5752f-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="5752f-113">O gerenciamento pós-implantação de servidores e pools para servidores Standard Edition e pools corporativos inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="5752f-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="5752f-114">Gerenciando servidores front-end</span><span class="sxs-lookup"><span data-stu-id="5752f-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="5752f-115">Gerenciando Webconferência</span><span class="sxs-lookup"><span data-stu-id="5752f-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="5752f-116">Gerenciando conferência</span><span class="sxs-lookup"><span data-stu-id="5752f-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="5752f-117">Alterar credenciais da conta de serviço</span><span class="sxs-lookup"><span data-stu-id="5752f-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="5752f-118">Gerenciando bancos de dados</span><span class="sxs-lookup"><span data-stu-id="5752f-118">Managing Databases</span></span>
    
      - <span data-ttu-id="5752f-119">Iniciar e interromper serviços e desativação de funções de servidor</span><span class="sxs-lookup"><span data-stu-id="5752f-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="5752f-120">Remover servidores e funções de servidor, remover pools e encerrar servidores e pools</span><span class="sxs-lookup"><span data-stu-id="5752f-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="5752f-121">**Gerenciando o uso**   você pode configurar o Lync Server 2013 para fornecer os recursos e a funcionalidade mais apropriados para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="5752f-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="5752f-122">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="5752f-122">This includes the following:</span></span>
    
      - <span data-ttu-id="5752f-123">Gerenciando o suporte para reuniões da webconferência no local</span><span class="sxs-lookup"><span data-stu-id="5752f-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="5752f-124">Gerenciando o uso de grupos de distribuição para enviar mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="5752f-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="5752f-125">Gerenciando contatos, presença e consultas</span><span class="sxs-lookup"><span data-stu-id="5752f-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="5752f-126">Configurando a filtragem de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="5752f-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="5752f-127">Configurando a filtragem inteligente de IM</span><span class="sxs-lookup"><span data-stu-id="5752f-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="5752f-128">Configurando arquivamento, registro de detalhes das chamadas e conformidade da reunião</span><span class="sxs-lookup"><span data-stu-id="5752f-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="5752f-129">**Gerenciar a conectividade**   do servidor de borda o gerenciamento contínuo dos servidores e das configurações necessárias para fornecer conectividade externa inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5752f-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="5752f-130">Gerenciando a conectividade entre servidores internos e servidores de borda</span><span class="sxs-lookup"><span data-stu-id="5752f-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="5752f-131">Configurando interfaces e certificados internos e externos para servidores de borda</span><span class="sxs-lookup"><span data-stu-id="5752f-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="5752f-132">Gerenciando o acesso de parceiro federado</span><span class="sxs-lookup"><span data-stu-id="5752f-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="5752f-133">**A administração do catálogo**   de endereços servidores do catálogo de endereços inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5752f-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="5752f-134">Configurando a normalização de telefone do servidor do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="5752f-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="5752f-135">Gerenciando o servidor de catálogo de endereços a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="5752f-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="5752f-136">**Gerenciar contas**   de usuário o gerenciamento de contas de usuário inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5752f-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="5752f-137">Habilitar contas de usuário para o Lync Server</span><span class="sxs-lookup"><span data-stu-id="5752f-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="5752f-138">Configurando usuários do Lync Server usando o assistente</span><span class="sxs-lookup"><span data-stu-id="5752f-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="5752f-139">Configurando propriedades individuais de contas de usuário do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5752f-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="5752f-140">Pesquisando usuários do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5752f-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="5752f-141">Movendo usuários do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5752f-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="5752f-142">Excluir usuários do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5752f-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="5752f-143">**Analisando arquivos**   de log do Lync Server 2013 uma ferramenta muito útil, geralmente usada para solução de problemas, é a ferramenta de registro em log do Lync Server 2013 descrita em detalhes sobre como [usar a ferramenta de registro em log do Lync Server 2013](http://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="5752f-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="5752f-144">Como a ferramenta de registro em log gera arquivos de log (em uma base por servidor), esses arquivos de log podem ser visualizados e analisados usando a ferramenta Snooper, se as ferramentas do Microsoft Office Server 12 Resource Kit estiverem instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="5752f-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="5752f-145">Caso contrário, os logs também podem ser analisados usando um editor de texto, que é muito menos transparente e mais complexo do que o uso do utilitário Snooper.</span><span class="sxs-lookup"><span data-stu-id="5752f-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="5752f-146">Para exibir e analisar mensagens de protocolo</span><span class="sxs-lookup"><span data-stu-id="5752f-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="5752f-147">Na ferramenta de log, depois de finalizar a sessão de depuração, clique em analisar arquivos de log para exibir os arquivos de log usando a ferramenta Snooper.</span><span class="sxs-lookup"><span data-stu-id="5752f-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="5752f-148">Você pode analisar os logs de protocolo para os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="5752f-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="5752f-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="5752f-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="5752f-150">S4 (SIP) do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5752f-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="5752f-151">C3P (tráfego de sinalização de conferência do Lync Server), incluindo MCU-C3P e foco C3P</span><span class="sxs-lookup"><span data-stu-id="5752f-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="5752f-152">Tráfego de Webconferência do Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="5752f-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="5752f-153">Cliente de plataforma de comunicação unificada do Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="5752f-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="5752f-154">Relatórios de erro do banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="5752f-154">Error reports from the archiving database</span></span>

<span data-ttu-id="5752f-155">Para ajudar a organizar o desempenho das tarefas necessárias, confira lista de verificação de operações necessárias.</span><span class="sxs-lookup"><span data-stu-id="5752f-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5752f-156">Para obter procedimentos detalhados de administração e gerenciamento, consulte o guia de administração do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5752f-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="5752f-157">Políticas de backup (e restauração) ou definições de configuração</span><span class="sxs-lookup"><span data-stu-id="5752f-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="5752f-158">O Lync Server 2013 permite fazer backup e restaurar todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="5752f-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="5752f-159">IIf que você deseja fazer backup (e, em seguida, pode ser uma restauração de algum dia) uma única política ou uma única coleção de definições de configuração, recuperar a política apropriada e, em seguida, canalizar o objeto para o cmdlet Export-Clixml, que salva as informações da política como um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="5752f-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="5752f-160">Agora você pode experimentar o RedmondClientPolicy e alterar muitas das configurações.</span><span class="sxs-lookup"><span data-stu-id="5752f-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="5752f-161">Se decidir em vez de restaurar a política antiga, digite:</span><span class="sxs-lookup"><span data-stu-id="5752f-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="5752f-162">Observe que essa abordagem funcionará para a maioria das políticas e configurações, mas não funcionará com alguns dos itens mais complexos, os itens que contêm vários subobjetos (como configurações de roteamento, que contêm muitas rotas de voz separadas).</span><span class="sxs-lookup"><span data-stu-id="5752f-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

