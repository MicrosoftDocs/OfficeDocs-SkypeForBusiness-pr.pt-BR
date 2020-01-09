---
title: Usar o painel de monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumo: Saiba mais sobre o painel de monitoramento no Skype for Business Server.'
ms.openlocfilehash: 39f5e9c2b024f73f669098c4da7eaca40ef4ea61
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992026"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="a088c-103">Usar o painel de monitoramento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a088c-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="a088c-104">**Resumo:** Saiba mais sobre o painel de monitoramento no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a088c-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="a088c-105">O painel Monitoramento fornece aos administradores uma rápida visão geral da integridade do sistema e do uso do sistema do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a088c-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="a088c-106">O Painel foi projetado para fornecer uma exibição agregada das principais métricas do sistema e para fazer isso exibindo:</span><span class="sxs-lookup"><span data-stu-id="a088c-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="a088c-107">Os totais para o dia atual.</span><span class="sxs-lookup"><span data-stu-id="a088c-107">Totals for the current day.</span></span> <span data-ttu-id="a088c-108">Observe que os valores mostrados para o dia atual representam dados que foram gravados da meia-noite até a hora atual (com base na hora local do servidor de relatório).</span><span class="sxs-lookup"><span data-stu-id="a088c-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="a088c-109">Isso significa que você geralmente estará vendo dados referentes a um dia parcial, não a um período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="a088c-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="a088c-110">Por exemplo, se a hora local do servidor for 8:00 AM, você verá a importância de oito horas de dados porque há oito horas entre a meia-noite e a hora atual do 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="a088c-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="a088c-111">Totais para a semana e totais de tendência das últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="a088c-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="a088c-112">Totais para o mês e os totais de tendência dos últimos seis meses (apenas para uso do sistema).</span><span class="sxs-lookup"><span data-stu-id="a088c-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="a088c-113">Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para retornar a URL usada para acessar os relatórios de monitoramento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a088c-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="a088c-114">Por padrão, o Painel de Monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="a088c-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="a088c-115">Métricas de uso do sistema</span><span class="sxs-lookup"><span data-stu-id="a088c-115">System Usage Metrics</span></span>

 <span data-ttu-id="a088c-116">**Registro**</span><span class="sxs-lookup"><span data-stu-id="a088c-116">**Registration**</span></span>
  
- <span data-ttu-id="a088c-117">Logons de usuário exclusivos</span><span class="sxs-lookup"><span data-stu-id="a088c-117">Unique user logons</span></span>
    
  <span data-ttu-id="a088c-118">**Ponto a ponto**</span><span class="sxs-lookup"><span data-stu-id="a088c-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="a088c-119">Total de sessões</span><span class="sxs-lookup"><span data-stu-id="a088c-119">Total sessions</span></span>
    
- <span data-ttu-id="a088c-120">Sessões de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="a088c-120">IM sessions</span></span>
    
- <span data-ttu-id="a088c-121">Sessões de áudio</span><span class="sxs-lookup"><span data-stu-id="a088c-121">Audio sessions</span></span>
    
- <span data-ttu-id="a088c-122">Sessões de vídeo</span><span class="sxs-lookup"><span data-stu-id="a088c-122">Video sessions</span></span>
    
- <span data-ttu-id="a088c-123">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a088c-123">Application sharing</span></span>
    
- <span data-ttu-id="a088c-124">Total de minutos da sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="a088c-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="a088c-125">Média de minutos da sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="a088c-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="a088c-126">**Conferência**</span><span class="sxs-lookup"><span data-stu-id="a088c-126">**Conference**</span></span>
  
- <span data-ttu-id="a088c-127">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="a088c-127">Total conferences</span></span>
    
- <span data-ttu-id="a088c-128">Conferências de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="a088c-128">IM conferences</span></span>
    
- <span data-ttu-id="a088c-129">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="a088c-129">A/V conferences</span></span>
    
- <span data-ttu-id="a088c-130">Conferências de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a088c-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="a088c-131">Webconferências</span><span class="sxs-lookup"><span data-stu-id="a088c-131">Web conferences</span></span>
    
- <span data-ttu-id="a088c-132">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="a088c-132">Total organizers</span></span>
    
- <span data-ttu-id="a088c-133">Total de minutos da conferência A/V</span><span class="sxs-lookup"><span data-stu-id="a088c-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="a088c-134">Média de minutos da conferência A/V</span><span class="sxs-lookup"><span data-stu-id="a088c-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="a088c-135">Total de conferências PSTN</span><span class="sxs-lookup"><span data-stu-id="a088c-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="a088c-136">Total de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="a088c-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="a088c-137">Total de minutos dos participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="a088c-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="a088c-138">Além das métricas de Uso do Sistema, as seguintes métricas exibem o total para o dia atual e os seis dias anteriores (se você selecionar **Exibição Semanal**) ou para a semana atual e as últimas seis semanas se você selecionar **Exibição Mensal**.</span><span class="sxs-lookup"><span data-stu-id="a088c-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="a088c-139">Diagnóstico de chamada por usuário</span><span class="sxs-lookup"><span data-stu-id="a088c-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="a088c-140">**Usuários com falhas na chamada**</span><span class="sxs-lookup"><span data-stu-id="a088c-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="a088c-141">Total de usuários com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="a088c-141">Total users with call failures</span></span>
    
- <span data-ttu-id="a088c-142">Organizadores de conferência com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="a088c-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="a088c-143">**Usuários com chamadas com qualidade ruim**</span><span class="sxs-lookup"><span data-stu-id="a088c-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="a088c-144">Total de usuários com chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="a088c-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="a088c-145">Diagnóstico de Chamadas</span><span class="sxs-lookup"><span data-stu-id="a088c-145">Call Diagnostics</span></span>

<span data-ttu-id="a088c-146">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="a088c-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="a088c-147">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="a088c-147">Total failures</span></span>
    
- <span data-ttu-id="a088c-148">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="a088c-148">Overall failure rate</span></span>
    
- <span data-ttu-id="a088c-149">Taxa de falha de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="a088c-149">IM failure rate</span></span>
    
- <span data-ttu-id="a088c-150">Taxa de falha de áudio</span><span class="sxs-lookup"><span data-stu-id="a088c-150">Audio failure rate</span></span>
    
- <span data-ttu-id="a088c-151">Taxa de falha de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a088c-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="a088c-152">Conferência</span><span class="sxs-lookup"><span data-stu-id="a088c-152">Conference</span></span>
  
- <span data-ttu-id="a088c-153">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="a088c-153">Total failures</span></span>
    
- <span data-ttu-id="a088c-154">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="a088c-154">Overall failure rate</span></span>
    
- <span data-ttu-id="a088c-155">Taxa de falha de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="a088c-155">IM failure rate</span></span>
    
- <span data-ttu-id="a088c-156">Taxa de falha de A/V</span><span class="sxs-lookup"><span data-stu-id="a088c-156">A/V failure rate</span></span>
    
- <span data-ttu-id="a088c-157">Taxa de falha de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a088c-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="a088c-158">Principais cinco servidores por sessões de falha</span><span class="sxs-lookup"><span data-stu-id="a088c-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="a088c-159">Diagnóstico de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="a088c-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="a088c-160">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="a088c-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="a088c-161">Total de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="a088c-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="a088c-162">Percentual de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="a088c-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="a088c-163">Chamadas PSTN com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="a088c-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="a088c-164">Conferência</span><span class="sxs-lookup"><span data-stu-id="a088c-164">Conference</span></span>
  
- <span data-ttu-id="a088c-165">Total de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="a088c-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="a088c-166">Percentual de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="a088c-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="a088c-167">Chamadas PSTN com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="a088c-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="a088c-168">Piores servidores por percentual de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="a088c-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="a088c-169">Trabalhando com o Painel de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="a088c-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="a088c-p103">Conforme observado, os totais padrões são mostrados para a semana atual e os valores de tendência são mostrados para as últimas seis semanas. Se você prefere ver os totais para o mês atual (assim como os valores de tendência para os últimos seis meses), clique no link **Exibição Mensal** no canto superior direito do painel. Se você decidir exibir os totais mensais, o texto do link irá mudar para **Exibição Semanal**. É possível voltar para a exibição semanal clicando neste link.</span><span class="sxs-lookup"><span data-stu-id="a088c-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="a088c-p104">O Painel de Monitoramento restringe a exibição dos totais para a semana (ou mês) atual e os valores de tendência das últimas seis semanas (ou meses). Não é possível alterar essas datas e horas. Por exemplo, não é possível usar o Painel para ver os totais do relatório para o período que inicia nove meses atrás.</span><span class="sxs-lookup"><span data-stu-id="a088c-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="a088c-p105">Os valores mostrados nas colunas **Esta semana**, **Este mês** ou **Hoje** vinculam você às informações mais detalhadas sobre o item. Lembre-se de que o nome da coluna e os valores exibidos nesta coluna frequentemente são diferentes dependendo da métrica escolhida e dependendo se você selecionou exibição semanal ou mensal. Por exemplo, se você clicar nos totais exibidos para a métrica **Logons de usuário exclusivos**, você verá o **Relatório de Registro do Usuário** para o período especificado. É possível retornar para o Painel de Monitoramento a qualquer momento clicando em **Painel**.</span><span class="sxs-lookup"><span data-stu-id="a088c-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="a088c-181">Você também pode acessar a Home Page de relatórios do Monitoring Server clicando no link **relatórios** no canto superior direito do painel.</span><span class="sxs-lookup"><span data-stu-id="a088c-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="a088c-p106">A coluna **Tendência** exibe um gráfico de linha simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, os últimos seis dias ou últimos seis meses). Esses gráficos de linha simples mostram um ponto de dados não rotulado para cada período (por exemplo, um ponto de dados não rotulado para cada uma das últimas seis semanas). No entanto, é possível recuperar os valores reais desses gráficos mantendo o ponteiro do mouse sobre o gráfico. Nesse caso, uma dica de tela mostra os valores máximos e mínimo no gráfico.</span><span class="sxs-lookup"><span data-stu-id="a088c-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="a088c-186">Exportando dados do Painel de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="a088c-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="a088c-p107">O Painel de Monitoramento oferece várias formas de exportar a exibição do painel atual. Na barra de ferramentas do Painel, você verá um ícone semelhante a um disquete com uma seta verde anexada. Se você clicar nesse ícone, uma lista suspensa aparecerá oferecendo os seguintes formatos de exportação de dados:</span><span class="sxs-lookup"><span data-stu-id="a088c-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="a088c-190">Arquivo XML com dados do relatório</span><span class="sxs-lookup"><span data-stu-id="a088c-190">XML file with report data</span></span>
    
- <span data-ttu-id="a088c-191">CSV (delimitado por vírgula)</span><span class="sxs-lookup"><span data-stu-id="a088c-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="a088c-192">PDF</span><span class="sxs-lookup"><span data-stu-id="a088c-192">PDF</span></span>
    
- <span data-ttu-id="a088c-193">MHTML (arquivo Web)</span><span class="sxs-lookup"><span data-stu-id="a088c-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="a088c-194">Excel</span><span class="sxs-lookup"><span data-stu-id="a088c-194">Excel</span></span>
    
- <span data-ttu-id="a088c-195">Arquivo TIFF</span><span class="sxs-lookup"><span data-stu-id="a088c-195">TIFF file</span></span>
    
- <span data-ttu-id="a088c-196">Word</span><span class="sxs-lookup"><span data-stu-id="a088c-196">Word</span></span>
    
<span data-ttu-id="a088c-197">Para exportar a exibição do painel atual (e seus valores), clique na opção de exportação desejada.</span><span class="sxs-lookup"><span data-stu-id="a088c-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="a088c-198">O Skype for Business Server gera um relatório no formato especificado e oferece a opção de abrir esse relatório ou salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="a088c-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="a088c-199">Observe que, por padrão, o Skype for Business Server títulos o **painel Monitoramento** de relatório e salva-o na pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="a088c-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="a088c-200">Para dar um nome diferente ou armazená-lo em uma pasta diferente, clique na seta ao lado do botão **Salvar** e clique em **Salvar Como**.</span><span class="sxs-lookup"><span data-stu-id="a088c-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="a088c-201">Se você concorda com o nome **Painel de Monitoramento** e em salvar na pasta Downloads, basta clicar no botão **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a088c-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="a088c-p109">É possível que, ao tentar exportar os dados do painel, uma caixa de diálogo **Alerta de Segurança** seja exibida junto com a mensagem "Suas configurações atuais não permitem que este arquivo seja baixado". Se isso ocorrer, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a088c-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="a088c-204">No Internet Explorer, selecione **Opções de Internet**.</span><span class="sxs-lookup"><span data-stu-id="a088c-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="a088c-205">Na caixa de diálogo **Opções de Internet**, na guia **Segurança**, clique em **Sites confiáveis** e em **Sites**.</span><span class="sxs-lookup"><span data-stu-id="a088c-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="a088c-206">Na caixa de diálogo **sites confiáveis** , clique em **Adicionar** para adicionar o Skype for Business Server que está executando os relatórios do Skype for Business Server às coleções de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="a088c-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="a088c-207">Clique em **Fechar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a088c-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="a088c-p110">Você precisará atualizar o Painel de Monitoramento para que as alterações tenham efeito. Para fazer isso, pressione F5 ou clique no ícone **Atualizar** na barra de ferramentas do Painel. (O ícone **Atualizar** é um círculo com um par de setas verdes.)</span><span class="sxs-lookup"><span data-stu-id="a088c-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="a088c-p111">Também é possível criar uma planilha do Excel que inclui feeds de dados ao vivo, incluindo links para os dados do Painel de Monitoramento. Para criar um arquivo de feed de dados ao vivo, clique no ícone laranja **Exportar para Feed de Dados** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="a088c-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="a088c-213">Se você prefere imprimir o Painel atual, clique no ícone da impressora na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="a088c-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

