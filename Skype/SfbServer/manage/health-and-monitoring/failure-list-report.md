---
title: Relatório de lista de falhas no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumo: Saiba mais sobre o Failure List Report no Skype para Business Server 2015.'
ms.openlocfilehash: 7cb146569958908e79700e725d473bc246295c9d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569317"
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a><span data-ttu-id="e2ad3-103">Relatório de lista de falhas no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e2ad3-103">Failure List Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2ad3-104">**Resumo:** Saiba mais sobre o Failure List Report no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-104">**Summary:** Learn about the Failure List Report in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e2ad3-p101">O Relatório da lista de falhas fornece informações sobre os participantes individuais de uma sessão de conferência ou ponto a ponto com falha. Essas informações incluem o URI do usuário que teve o problema, bem como o código de resposta SIP e o ID de diagnóstico associado à falha.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="e2ad3-107">Acessando o Relatório da lista de falhas</span><span class="sxs-lookup"><span data-stu-id="e2ad3-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="e2ad3-108">O Failure List Report é acessado clicando em qualquer uma das seguintes métricas do [Relatório de falha de distribuição no Skype para Business Server 2015](failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="e2ad3-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server 2015](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="e2ad3-109">Principais motivos diagnósticos (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="e2ad3-110">Principais modalidades (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="e2ad3-111">Principais pools (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="e2ad3-112">Principais fontes (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="e2ad3-113">Principais componentes (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="e2ad3-114">Principais usuários "De" (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="e2ad3-115">Principais usuários "Para" (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="e2ad3-116">Principais agentes do usuários "De" (sessões)</span><span class="sxs-lookup"><span data-stu-id="e2ad3-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="e2ad3-117">Do Failure List Report, você pode acessar o [relatório de detalhes de sessão ponto a ponto no Skype para Business Server 2015](peer-to-peer-session-detail-report.md) clicando na métrica detalhe de sessão para uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server 2015](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="e2ad3-118">Você também pode acessar o Relatório de detalhes da conferência clicando na métrica Conferência de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="e2ad3-119">Aprimorando o uso do Relatório da lista de falhas</span><span class="sxs-lookup"><span data-stu-id="e2ad3-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="e2ad3-p103">No Relatório da lista de falhas, é possível visualizar uma descrição para cada código de resposta ou cada ID de diagnóstico simplesmente passando o mouse sobre o valor em questão. Por exemplo, se você passar o mouse sobre o ID de diagnóstico 7025, verá a seguinte mensagem em uma dica de ferramenta:</span><span class="sxs-lookup"><span data-stu-id="e2ad3-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="e2ad3-122">Internal server error creating media for user.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="e2ad3-123">É importante notar que o Relatório da lista de falhas não fornece uma maneira simples de recuperar diretamente uma lista de todos os usuários que participaram de pelo menos uma sessão com falha, nem fornece uma maneira de determinar quais usuários geralmente estavam envolvidos em uma sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="e2ad3-124">(Primeiro, o Failure List Report não terá nenhuma recursos de filtragem.) No entanto, se você exporta os dados e então o converta para um arquivo de valores separados por vírgulas, você pode usar o Windows PowerShell para encontrar as respostas a perguntas como essas.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="e2ad3-125">Por exemplo, suponha que você salve os dados em um arquivo .CSV chamado C:\Data\Failure_List.csv.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="e2ad3-126">Com base nos dados salvos nesse arquivo, esse comando lista os usuários que estavam envolvidos em pelo menos uma sessão com falha:</span><span class="sxs-lookup"><span data-stu-id="e2ad3-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="e2ad3-127">Esse comando retornará uma lista semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="e2ad3-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="e2ad3-128">Esses dois comandos relatam o número total de sessões com falha em que cada usuário estava envolvido:</span><span class="sxs-lookup"><span data-stu-id="e2ad3-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="e2ad3-129">Serão retornados dados semelhantes a estes:</span><span class="sxs-lookup"><span data-stu-id="e2ad3-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="e2ad3-130">Filtros</span><span class="sxs-lookup"><span data-stu-id="e2ad3-130">Filters</span></span>

<span data-ttu-id="e2ad3-p105">Nenhum. Não é possível filtrar o Relatório de Lista de Falhas.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="e2ad3-133">Métricas</span><span class="sxs-lookup"><span data-stu-id="e2ad3-133">Metrics</span></span>

<span data-ttu-id="e2ad3-134">A tabela a seguir lista as informações fornecidas no Relatório de Lista de Falhas para cada chamada mal-sucedida.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="e2ad3-135">**Métricas do relatório de lista de falha**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="e2ad3-136">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-136">**Name**</span></span>|<span data-ttu-id="e2ad3-137">**Você pode classificar este item?**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="e2ad3-138">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2ad3-139">**Hora de relatório**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-139">**Reported time**</span></span> <br/> |<span data-ttu-id="e2ad3-140">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-140">No</span></span>  <br/> |<span data-ttu-id="e2ad3-141">Data e hora do registro do relatório.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="e2ad3-142">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-142">**Request**</span></span> <br/> |<span data-ttu-id="e2ad3-143">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-143">No</span></span>  <br/> |<span data-ttu-id="e2ad3-p106">Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR ou ATÉ LOGO.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="e2ad3-146">**Código da resposta**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-146">**Response code**</span></span> <br/> |<span data-ttu-id="e2ad3-147">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-147">No</span></span>  <br/> |<span data-ttu-id="e2ad3-148">Código da resposta SIP enviado quando a conferência falhou.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="e2ad3-149">**ID do Diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="e2ad3-150">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-150">No</span></span>  <br/> |<span data-ttu-id="e2ad3-151">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="e2ad3-152">**Join cost time (ms)**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="e2ad3-153">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-153">No</span></span>  <br/> |<span data-ttu-id="e2ad3-154">Tempo (em milissegundos) necessário para o usuário participar da conferência.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="e2ad3-155">**Usuário "De"**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-155">**From user**</span></span> <br/> |<span data-ttu-id="e2ad3-156">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-156">No</span></span>  <br/> |<span data-ttu-id="e2ad3-157">Endereço SIP do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="e2ad3-158">**Agente do usuário de origem**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-158">**From user agent**</span></span> <br/> |<span data-ttu-id="e2ad3-159">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-159">No</span></span>  <br/> |<span data-ttu-id="e2ad3-160">Software usado pelo ponto de extremidade do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="e2ad3-161">**Usuário "Para"**</span><span class="sxs-lookup"><span data-stu-id="e2ad3-161">**To user**</span></span> <br/> |<span data-ttu-id="e2ad3-162">Não</span><span class="sxs-lookup"><span data-stu-id="e2ad3-162">No</span></span>  <br/> |<span data-ttu-id="e2ad3-163">Endereço SIP do usuário que estava recebendo a chamada.</span><span class="sxs-lookup"><span data-stu-id="e2ad3-163">SIP address of the user who was being called.</span></span>  <br/> |
   

