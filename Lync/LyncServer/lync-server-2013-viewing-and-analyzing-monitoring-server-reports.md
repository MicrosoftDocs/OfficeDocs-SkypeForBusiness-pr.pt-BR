---
title: 'Lync Server 2013: Exibindo e analisando relatórios do Monitoring Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="079a8-102">Visualizando e analisando relatórios do Monitoring Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="079a8-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="079a8-103">_**Tópico da última modificação:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="079a8-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="079a8-104">Os relatórios do Monitoring Server fornecem várias medidas diferentes de qualidade de voz para monitorar a QoE que está sendo entregue aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="079a8-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="079a8-105">Além disso, o Monitoring Server inclui vários relatórios internos que a sua organização pode usar para monitorar o uso e as tendências de qualidade de mídia na rede da sua organização e solucionar problemas de qualidade de mídia que surgem.</span><span class="sxs-lookup"><span data-stu-id="079a8-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="079a8-106">Uma parte principal de manter os relatórios do servidor de monitoramento interessantes para operações semanais e semanais é exibir e analisar relatórios de qualidade de mídia, em particular:</span><span class="sxs-lookup"><span data-stu-id="079a8-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="079a8-107">Relatórios de resumo/tendências de QoE</span><span class="sxs-lookup"><span data-stu-id="079a8-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="079a8-108">Relatórios de desempenho de QoE</span><span class="sxs-lookup"><span data-stu-id="079a8-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="079a8-109">Exibir relatórios do servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="079a8-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="079a8-110">Em um navegador da Web, localize seus servidores que hospedam o SQL Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="079a8-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="079a8-111">Exiba os relatórios necessários na tela do navegador.</span><span class="sxs-lookup"><span data-stu-id="079a8-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="079a8-112">Adicionais Exporte um relatório selecionando a opção Exportar e o formato de saída necessário.</span><span class="sxs-lookup"><span data-stu-id="079a8-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="079a8-113">Configurar a registro de detalhes de chamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="079a8-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="079a8-114">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem permissões equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="079a8-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="079a8-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="079a8-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="079a8-116">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.</span><span class="sxs-lookup"><span data-stu-id="079a8-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="079a8-117">Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="079a8-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="079a8-118">Para ativar a limpeza, selecione **habilitar a limpeza para servidores de monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="079a8-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="079a8-119">Em **manter gravações de detalhes da chamada por duração máxima (dias):** selecione o número máximo de dias em que as gravações de detalhes da chamada devem ser mantidas.</span><span class="sxs-lookup"><span data-stu-id="079a8-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="079a8-120">Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.</span><span class="sxs-lookup"><span data-stu-id="079a8-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="079a8-121">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="079a8-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="079a8-122">Configurar QoE</span><span class="sxs-lookup"><span data-stu-id="079a8-122">Configure QoE</span></span>

1.  <span data-ttu-id="079a8-123">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="079a8-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="079a8-124">Para obter detalhes, consulte Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="079a8-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="079a8-125">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="079a8-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="079a8-126">Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="079a8-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="079a8-127">Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="079a8-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="079a8-128">Para ativar a limpeza, selecione **habilitar a limpeza para servidores de monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="079a8-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="079a8-129">Em **manter registros de detalhes da chamada por duração máxima (dias):** selecione o número máximo de dias pelos quais os dados de QoE devem ser mantidos.</span><span class="sxs-lookup"><span data-stu-id="079a8-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="079a8-130">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="079a8-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="079a8-131">Alterar a política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="079a8-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="079a8-132">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="079a8-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="079a8-133">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="079a8-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="079a8-134">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="079a8-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="079a8-135">Clique em **Global** na lista de políticas, clique em **Editar** e depois em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="079a8-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="079a8-136">Em **Editar Política de Arquivamento - Global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="079a8-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="079a8-137">Para habilitar ou desabilitar o arquivamento interno para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações internas** .</span><span class="sxs-lookup"><span data-stu-id="079a8-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="079a8-138">Para habilitar ou desabilitar o arquivamento externo para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações externas** .</span><span class="sxs-lookup"><span data-stu-id="079a8-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="079a8-139">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="079a8-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="079a8-140">Aplicar uma política de arquivamento a um usuário</span><span class="sxs-lookup"><span data-stu-id="079a8-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="079a8-141">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="079a8-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="079a8-142">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="079a8-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="079a8-143">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="079a8-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="079a8-144">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="079a8-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="079a8-145">Em **Editar o usuário do Lync Server** na **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="079a8-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="079a8-146">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="079a8-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="079a8-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="079a8-147">See Also</span></span>


[<span data-ttu-id="079a8-148">Usar relatórios de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="079a8-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="079a8-149">Relatório de desempenho do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="079a8-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="079a8-150">Relatório de comparação de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="079a8-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

