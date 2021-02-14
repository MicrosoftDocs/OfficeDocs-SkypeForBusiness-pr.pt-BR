---
title: Relatório detalhado de conferências no Skype for Business Server
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
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumo: saiba mais sobre o Relatório detalhado de conferências usado no Skype for Business Server.'
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816901"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="1b767-103">Relatório detalhado de conferências no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1b767-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="1b767-104">**Resumo:** Saiba mais sobre o Relatório detalhado de conferências usado no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1b767-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="1b767-p101">O Relatório de Detalhe da Conferência oferece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="1b767-109">Acessar o Relatório de Detalhe da Conferência</span><span class="sxs-lookup"><span data-stu-id="1b767-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="1b767-110">O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="1b767-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="1b767-111">O [Call Admission Control Report](call-admission-control-report.md) (clicando na métrica Detalhe de uma conferência)</span><span class="sxs-lookup"><span data-stu-id="1b767-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="1b767-112">O [Failure List Report](failure-list-report.md) (clicando na métrica Conferência)</span><span class="sxs-lookup"><span data-stu-id="1b767-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="1b767-113">O [User Activity Report](call-diagnostic-reports-per-user.md) (clicando na métrica URI da conferência)</span><span class="sxs-lookup"><span data-stu-id="1b767-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="1b767-114">Do Relatório de Detalhe da Conferência, é possível acessar o [Diagnostic Report](diagnostic-report.md) clicando na métrica Relatório de Diagnóstico (Detalhe).</span><span class="sxs-lookup"><span data-stu-id="1b767-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="1b767-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="1b767-115">Filters</span></span>

<span data-ttu-id="1b767-p102">Nenhum. Você não pode filtrar o Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="1b767-118">Métrica</span><span class="sxs-lookup"><span data-stu-id="1b767-118">Metrics</span></span>

<span data-ttu-id="1b767-119">A tabela a seguir lista as informações fornecidas na seção Informação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="1b767-120">**Métricas de Informação da Conferência**</span><span class="sxs-lookup"><span data-stu-id="1b767-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="1b767-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1b767-121">**Name**</span></span>                 | <span data-ttu-id="1b767-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1b767-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1b767-123">**URI de Conferência**</span><span class="sxs-lookup"><span data-stu-id="1b767-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="1b767-p103">URI atribuído à conferência. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b767-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="1b767-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="1b767-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="1b767-127">**FQDN do Pool**</span><span class="sxs-lookup"><span data-stu-id="1b767-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="1b767-128">Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1b767-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="1b767-129">**Hora inicial**</span><span class="sxs-lookup"><span data-stu-id="1b767-129">**Start time**</span></span> <br/>     | <span data-ttu-id="1b767-130">Data e hora que a conferência iniciou.</span><span class="sxs-lookup"><span data-stu-id="1b767-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="1b767-131">**Organizador**</span><span class="sxs-lookup"><span data-stu-id="1b767-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="1b767-132">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="1b767-133">**Hora final**</span><span class="sxs-lookup"><span data-stu-id="1b767-133">**End time**</span></span> <br/>       | <span data-ttu-id="1b767-134">Data e hora que a conferência terminou.</span><span class="sxs-lookup"><span data-stu-id="1b767-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="1b767-135">A tabela a seguir lista a informação oferecida na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="1b767-136">**Métricas de Participação da Conferência**</span><span class="sxs-lookup"><span data-stu-id="1b767-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="1b767-137">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1b767-137">**Name**</span></span>|<span data-ttu-id="1b767-138">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1b767-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b767-139">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="1b767-139">**User**</span></span> <br/> |<span data-ttu-id="1b767-140">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="1b767-141">**Função**</span><span class="sxs-lookup"><span data-stu-id="1b767-141">**Role**</span></span> <br/> |<span data-ttu-id="1b767-142">Função (por exemplo, Apresentador) do participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="1b767-143">**Conectividade**</span><span class="sxs-lookup"><span data-stu-id="1b767-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="1b767-144">Conectividade de rede (geralmente Externa ou Interna) do participante.</span><span class="sxs-lookup"><span data-stu-id="1b767-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="1b767-145">**Hora de participação**</span><span class="sxs-lookup"><span data-stu-id="1b767-145">**Join time**</span></span> <br/> |<span data-ttu-id="1b767-146">Data e hora que o participante entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="1b767-147">**Hora de saída**</span><span class="sxs-lookup"><span data-stu-id="1b767-147">**Leave time**</span></span> <br/> |<span data-ttu-id="1b767-148">Data e hora que o participante saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="1b767-149">**Agente do usuário**</span><span class="sxs-lookup"><span data-stu-id="1b767-149">**User agent**</span></span> <br/> |<span data-ttu-id="1b767-150">Identificador do software usado pelo ponto de extremidade do participante.</span><span class="sxs-lookup"><span data-stu-id="1b767-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="1b767-151">**Relatórios de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="1b767-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="1b767-p104">Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</span><span class="sxs-lookup"><span data-stu-id="1b767-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="1b767-154">A tabela a seguir lista as informações fornecidas na seção Modalidades de Conferência do Relatório de Detalhes da Conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="1b767-155">**Métricas das Modalidades da Conferência**</span><span class="sxs-lookup"><span data-stu-id="1b767-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="1b767-156">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1b767-156">**Name**</span></span>|<span data-ttu-id="1b767-157">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1b767-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b767-158">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="1b767-158">**User**</span></span> <br/> |<span data-ttu-id="1b767-159">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="1b767-160">**Hora de participação**</span><span class="sxs-lookup"><span data-stu-id="1b767-160">**Join time**</span></span> <br/> |<span data-ttu-id="1b767-161">Data e hora que o participante entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="1b767-162">**Hora de saída**</span><span class="sxs-lookup"><span data-stu-id="1b767-162">**Leave time**</span></span> <br/> |<span data-ttu-id="1b767-163">Data e hora que um participante deixou a conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="1b767-164">**URI do servidor de conferência**</span><span class="sxs-lookup"><span data-stu-id="1b767-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="1b767-165">URI para o servidor de Conferência usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="1b767-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="1b767-166">**Relatórios de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="1b767-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="1b767-p105">Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</span><span class="sxs-lookup"><span data-stu-id="1b767-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


