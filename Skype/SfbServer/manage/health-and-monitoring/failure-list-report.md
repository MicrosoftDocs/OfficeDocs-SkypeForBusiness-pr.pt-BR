---
title: Relatório de lista de falhas no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumo: saiba mais sobre o Relatório de Lista de Falhas no Skype for Business Server.'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816841"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="a52af-103">Relatório de lista de falhas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a52af-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="a52af-104">**Resumo:** Saiba mais sobre o Relatório de Lista de Falhas no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a52af-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="a52af-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span><span class="sxs-lookup"><span data-stu-id="a52af-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="a52af-107">Accessing the Failure List Report</span><span class="sxs-lookup"><span data-stu-id="a52af-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="a52af-108">O Relatório de Lista de Falhas é acessado clicando em qualquer uma das seguintes métricas no Relatório de Distribuição de [Falhas no Skype for Business Server:](failure-distribution-report.md)</span><span class="sxs-lookup"><span data-stu-id="a52af-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="a52af-109">Principais motivos diagnósticos (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="a52af-110">Principais modalidades (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="a52af-111">Principais pools (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="a52af-112">Principais fontes (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="a52af-113">Principais componentes (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="a52af-114">Principais usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="a52af-115">Principais usuários de destino (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="a52af-116">Principais agentes de usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="a52af-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="a52af-117">No Relatório de Lista de Falhas, você pode acessar o Relatório Detalhado de Sessão Ponto a Ponto no [Skype for Business Server](peer-to-peer-session-detail-report.md) clicando na métrica De detalhe da sessão para uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="a52af-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="a52af-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span><span class="sxs-lookup"><span data-stu-id="a52af-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="a52af-119">Making the Best Use of the Failure List Report</span><span class="sxs-lookup"><span data-stu-id="a52af-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="a52af-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span><span class="sxs-lookup"><span data-stu-id="a52af-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="a52af-122">Internal server error creating media for user.</span><span class="sxs-lookup"><span data-stu-id="a52af-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="a52af-p104">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session. (For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those. For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv. Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span><span class="sxs-lookup"><span data-stu-id="a52af-p104">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session. (For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those. For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv. Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="a52af-127">That command will return a list similar to this:</span><span class="sxs-lookup"><span data-stu-id="a52af-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="a52af-128">These two commands report back the total number of failed sessions that each user was involved in:</span><span class="sxs-lookup"><span data-stu-id="a52af-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="a52af-129">That will return data similar to this:</span><span class="sxs-lookup"><span data-stu-id="a52af-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="a52af-130">Filtros</span><span class="sxs-lookup"><span data-stu-id="a52af-130">Filters</span></span>

<span data-ttu-id="a52af-p105">Nenhum. Não é possível filtrar o Relatório de Lista de Falhas.</span><span class="sxs-lookup"><span data-stu-id="a52af-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="a52af-133">Métrica</span><span class="sxs-lookup"><span data-stu-id="a52af-133">Metrics</span></span>

<span data-ttu-id="a52af-134">A tabela a seguir lista as informações fornecidas no Relatório de Lista de Falhas para cada chamada mal-sucedida.</span><span class="sxs-lookup"><span data-stu-id="a52af-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="a52af-135">**Métricas do Relatório de Lista de Falhas**</span><span class="sxs-lookup"><span data-stu-id="a52af-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="a52af-136">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a52af-136">**Name**</span></span>|<span data-ttu-id="a52af-137">**É possível classificar este item?**</span><span class="sxs-lookup"><span data-stu-id="a52af-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="a52af-138">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a52af-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a52af-139">**Hora de relatório**</span><span class="sxs-lookup"><span data-stu-id="a52af-139">**Reported time**</span></span> <br/> |<span data-ttu-id="a52af-140">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-140">No</span></span>  <br/> |<span data-ttu-id="a52af-141">Data e hora em que o relatório foi gravado.</span><span class="sxs-lookup"><span data-stu-id="a52af-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="a52af-142">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="a52af-142">**Request**</span></span> <br/> |<span data-ttu-id="a52af-143">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-143">No</span></span>  <br/> |<span data-ttu-id="a52af-p106">Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR ou ATÉ LOGO.</span><span class="sxs-lookup"><span data-stu-id="a52af-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="a52af-146">**Código da resposta**</span><span class="sxs-lookup"><span data-stu-id="a52af-146">**Response code**</span></span> <br/> |<span data-ttu-id="a52af-147">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-147">No</span></span>  <br/> |<span data-ttu-id="a52af-148">Código da resposta SIP enviado quando a conferência falhou.</span><span class="sxs-lookup"><span data-stu-id="a52af-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="a52af-149">**ID do Diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="a52af-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="a52af-150">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-150">No</span></span>  <br/> |<span data-ttu-id="a52af-151">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros.</span><span class="sxs-lookup"><span data-stu-id="a52af-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="a52af-152">**Join cost time (ms)**</span><span class="sxs-lookup"><span data-stu-id="a52af-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="a52af-153">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-153">No</span></span>  <br/> |<span data-ttu-id="a52af-154">Amount of time (in milliseconds) required for the user to join the conference.</span><span class="sxs-lookup"><span data-stu-id="a52af-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="a52af-155">**Do usuário**</span><span class="sxs-lookup"><span data-stu-id="a52af-155">**From user**</span></span> <br/> |<span data-ttu-id="a52af-156">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-156">No</span></span>  <br/> |<span data-ttu-id="a52af-157">Endereço SIP do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="a52af-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a52af-158">**Representante do usuário de origem**</span><span class="sxs-lookup"><span data-stu-id="a52af-158">**From user agent**</span></span> <br/> |<span data-ttu-id="a52af-159">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-159">No</span></span>  <br/> |<span data-ttu-id="a52af-160">Software usado pelo ponto de extremidade do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="a52af-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a52af-161">**Para usuário**</span><span class="sxs-lookup"><span data-stu-id="a52af-161">**To user**</span></span> <br/> |<span data-ttu-id="a52af-162">Não</span><span class="sxs-lookup"><span data-stu-id="a52af-162">No</span></span>  <br/> |<span data-ttu-id="a52af-163">Endereço SIP do usuário que estava recebendo a chamada.</span><span class="sxs-lookup"><span data-stu-id="a52af-163">SIP address of the user who was being called.</span></span>  <br/> |
   

