---
title: Relatório de detalhes de conferência no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumo: Saiba mais sobre o relatório de detalhes de conferência usado no Skype para Business Server.'
ms.openlocfilehash: 122cd3b8bdc69342b4d0f55c9fe5168fdc44757d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225332"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="8a05d-103">Relatório de detalhes de conferência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8a05d-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="8a05d-104">**Resumo:** Saiba mais sobre o relatório de detalhes de conferência usado no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8a05d-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="8a05d-p101">O Relatório de Detalhe da Conferência fornece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="8a05d-109">Acessar o Relatório de Detalhe da Conferência</span><span class="sxs-lookup"><span data-stu-id="8a05d-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="8a05d-110">O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="8a05d-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="8a05d-111">O [Call Admission Control Report](call-admission-control-report.md) (clicando na métrica Detalhe de uma conferência)</span><span class="sxs-lookup"><span data-stu-id="8a05d-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="8a05d-112">O [Failure List Report](failure-list-report.md) (clicando na métrica Conferência)</span><span class="sxs-lookup"><span data-stu-id="8a05d-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="8a05d-113">O [User Activity Report](call-diagnostic-reports-per-user.md) (clicando na métrica URI da conferência)</span><span class="sxs-lookup"><span data-stu-id="8a05d-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="8a05d-114">Do relatório de detalhes de conferência, você pode acessar o [Relatório de diagnóstico](diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhe).</span><span class="sxs-lookup"><span data-stu-id="8a05d-114">From the Conference Detail Report you can access the [Diagnostic Repor](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="8a05d-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="8a05d-115">Filters</span></span>

<span data-ttu-id="8a05d-p102">Nenhum. Você não pode filtrar o Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="8a05d-118">Métricas</span><span class="sxs-lookup"><span data-stu-id="8a05d-118">Metrics</span></span>

<span data-ttu-id="8a05d-119">A tabela a seguir lista as informações fornecidas na seção Informação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="8a05d-120">**Métricas de Informação da Conferência**</span><span class="sxs-lookup"><span data-stu-id="8a05d-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="8a05d-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8a05d-121">**Name**</span></span>                 | <span data-ttu-id="8a05d-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8a05d-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8a05d-123">**URI de conferência**</span><span class="sxs-lookup"><span data-stu-id="8a05d-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="8a05d-p103">URI atribuído à conferência. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8a05d-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="8a05d-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="8a05d-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="8a05d-127">**FQDN do pool**</span><span class="sxs-lookup"><span data-stu-id="8a05d-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="8a05d-128">Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="8a05d-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="8a05d-129">**Hora inicial**</span><span class="sxs-lookup"><span data-stu-id="8a05d-129">**Start time**</span></span> <br/>     | <span data-ttu-id="8a05d-130">Data e hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="8a05d-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="8a05d-131">**Organizador**</span><span class="sxs-lookup"><span data-stu-id="8a05d-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="8a05d-132">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="8a05d-133">**Hora final**</span><span class="sxs-lookup"><span data-stu-id="8a05d-133">**End time**</span></span> <br/>       | <span data-ttu-id="8a05d-134">Data e hora em que a conferência terminou.</span><span class="sxs-lookup"><span data-stu-id="8a05d-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="8a05d-135">A tabela a seguir lista as informações oferecidas na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="8a05d-136">**Métricas de Participação da Conferência**</span><span class="sxs-lookup"><span data-stu-id="8a05d-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="8a05d-137">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8a05d-137">**Name**</span></span>|<span data-ttu-id="8a05d-138">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8a05d-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a05d-139">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="8a05d-139">**User**</span></span> <br/> |<span data-ttu-id="8a05d-140">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="8a05d-141">**Função**</span><span class="sxs-lookup"><span data-stu-id="8a05d-141">**Role**</span></span> <br/> |<span data-ttu-id="8a05d-142">Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="8a05d-143">**Conectividade**</span><span class="sxs-lookup"><span data-stu-id="8a05d-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="8a05d-144">Conectividade de rede (normalmente Interna ou Externa) para o participante.</span><span class="sxs-lookup"><span data-stu-id="8a05d-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="8a05d-145">**Hora da ingresso**</span><span class="sxs-lookup"><span data-stu-id="8a05d-145">**Join time**</span></span> <br/> |<span data-ttu-id="8a05d-146">Data e hora de ingresso do participante na conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="8a05d-147">**Hora da saída**</span><span class="sxs-lookup"><span data-stu-id="8a05d-147">**Leave time**</span></span> <br/> |<span data-ttu-id="8a05d-148">Data e hora de saída do participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="8a05d-149">**Agente do usuário**</span><span class="sxs-lookup"><span data-stu-id="8a05d-149">**User agent**</span></span> <br/> |<span data-ttu-id="8a05d-150">Identificador do software usado pelo ponto de extremidade do participante.</span><span class="sxs-lookup"><span data-stu-id="8a05d-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="8a05d-151">**Relatórios de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="8a05d-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="8a05d-p104">Fornece informações de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de ingresso na conferência e IDs de diagnósticos para sessões com falha.</span><span class="sxs-lookup"><span data-stu-id="8a05d-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="8a05d-154">A tabela a seguir lista as informações fornecidas na seção modalidades de conferência do relatório de detalhes de conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="8a05d-155">**Métricas das Modalidades da Conferência**</span><span class="sxs-lookup"><span data-stu-id="8a05d-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="8a05d-156">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8a05d-156">**Name**</span></span>|<span data-ttu-id="8a05d-157">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8a05d-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a05d-158">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="8a05d-158">**User**</span></span> <br/> |<span data-ttu-id="8a05d-159">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="8a05d-160">**Hora da ingresso**</span><span class="sxs-lookup"><span data-stu-id="8a05d-160">**Join time**</span></span> <br/> |<span data-ttu-id="8a05d-161">Data e hora de ingresso do participante na conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="8a05d-162">**Hora da saída**</span><span class="sxs-lookup"><span data-stu-id="8a05d-162">**Leave time**</span></span> <br/> |<span data-ttu-id="8a05d-163">Data e hora que um participante deixou a conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="8a05d-164">**URI do servidor de conferência**</span><span class="sxs-lookup"><span data-stu-id="8a05d-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="8a05d-165">URI para o servidor de Conferência usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="8a05d-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="8a05d-166">**Relatórios de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="8a05d-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="8a05d-p105">Fornece informações de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de ingresso na conferência e IDs de diagnósticos para sessões com falha.</span><span class="sxs-lookup"><span data-stu-id="8a05d-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


