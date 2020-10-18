---
title: 'Lync Server 2013: Exibindo e analisando relatórios do Monitoring Server'
description: 'Lync Server 2013: Exibindo e analisando relatórios do Monitoring Server.'
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
ms.openlocfilehash: 3f2a1812d76a49d487bea35acae3e22ea403f105
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580037"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="f3c66-103">Exibindo e analisando relatórios do Monitoring Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c66-103">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3c66-104">_**Última modificação do tópico:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="f3c66-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="f3c66-105">Os relatórios do Monitoring Server oferecem várias medidas diferentes de qualidade de voz para monitorar a QoE que está sendo entregue aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f3c66-105">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="f3c66-106">Além disso, o monitoramento do servidor inclui vários relatórios internos que sua organização pode usar para observar as tendências de uso e qualidade de mídia na rede da sua organização e solucionar problemas de qualidade de mídia que surgem.</span><span class="sxs-lookup"><span data-stu-id="f3c66-106">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="f3c66-107">Uma parte principal de manter relatórios de servidor de monitoramento interessantes para operações diárias e semanais é exibir e analisar relatórios de qualidade de mídia, em particular:</span><span class="sxs-lookup"><span data-stu-id="f3c66-107">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="f3c66-108">Relatórios de resumo/tendências de QoE</span><span class="sxs-lookup"><span data-stu-id="f3c66-108">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="f3c66-109">Relatórios de desempenho de QoE</span><span class="sxs-lookup"><span data-stu-id="f3c66-109">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="f3c66-110">Exibir relatórios do servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="f3c66-110">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="f3c66-111">Em um navegador da Web, localize os servidores que hospedam o SQL Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="f3c66-111">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="f3c66-112">Exibir os relatórios necessários na tela do navegador.</span><span class="sxs-lookup"><span data-stu-id="f3c66-112">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="f3c66-113">Opcion Exporte um relatório selecionando a opção Exportar e o formato de saída necessário.</span><span class="sxs-lookup"><span data-stu-id="f3c66-113">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="f3c66-114">Configurar o registro de detalhes das chamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="f3c66-114">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="f3c66-115">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha permissões equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3c66-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f3c66-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3c66-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f3c66-117">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="f3c66-118">Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-118">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="f3c66-119">Para ativar a limpeza, selecione **habilitar limpeza para servidores de monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-119">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="f3c66-120">Em **manter gravações de detalhes de chamada por duração máxima (dias):** selecione o número máximo de dias que as gravações de detalhes de chamada devem ser mantidas.</span><span class="sxs-lookup"><span data-stu-id="f3c66-120">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="f3c66-121">Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.</span><span class="sxs-lookup"><span data-stu-id="f3c66-121">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="f3c66-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="f3c66-123">Configurar QoE</span><span class="sxs-lookup"><span data-stu-id="f3c66-123">Configure QoE</span></span>

1.  <span data-ttu-id="f3c66-124">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f3c66-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f3c66-125">Para obter detalhes, consulte Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="f3c66-125">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="f3c66-126">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3c66-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f3c66-127">Na barra de navegação à esquerda, clique em **Monitoramento e Arquivamento** e clique em **Dados de Qualidade de Experiência**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="f3c66-128">Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-128">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="f3c66-129">Para ativar a limpeza, selecione **habilitar limpeza para servidores de monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-129">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="f3c66-130">Em **manter gravações de detalhes de chamada por duração máxima (dias):** selecione o número máximo de dias que os dados de QoE devem ser mantidos.</span><span class="sxs-lookup"><span data-stu-id="f3c66-130">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="f3c66-131">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="f3c66-131">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="f3c66-132">Alterar a política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="f3c66-132">Change the archiving policy</span></span>

1.  <span data-ttu-id="f3c66-133">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f3c66-133">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3c66-134">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3c66-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f3c66-135">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-135">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="f3c66-136">Clique em **Global** na lista de políticas, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-136">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f3c66-137">Em **Editar política de arquivamento - Global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3c66-137">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="f3c66-138">Para habilitar ou desabilitar o arquivamento interno para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações internas** .</span><span class="sxs-lookup"><span data-stu-id="f3c66-138">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="f3c66-139">Para habilitar ou desabilitar o arquivamento externo para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações externas** .</span><span class="sxs-lookup"><span data-stu-id="f3c66-139">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="f3c66-140">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-140">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="f3c66-141">Aplicar uma política de arquivamento a um usuário</span><span class="sxs-lookup"><span data-stu-id="f3c66-141">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="f3c66-142">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f3c66-142">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3c66-143">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3c66-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f3c66-144">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="f3c66-144">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="f3c66-145">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-145">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f3c66-146">Em **Editar usuário do Lync Server** em **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="f3c66-146">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="f3c66-147">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3c66-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3c66-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="f3c66-148">See Also</span></span>


[<span data-ttu-id="f3c66-149">Usando relatórios de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c66-149">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="f3c66-150">Relatório de desempenho do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c66-150">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="f3c66-151">Relatório de comparação de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c66-151">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

