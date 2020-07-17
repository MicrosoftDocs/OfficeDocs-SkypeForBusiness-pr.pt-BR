---
title: Classificar minha chamada no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumo: Saiba mais sobre o recurso Rate My Call no Skype for Business Server.'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902211"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="e2f86-103">Classificar minha chamada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2f86-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="e2f86-104">**Resumo:** Saiba mais sobre o recurso Rate My Call no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2f86-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="e2f86-105">Rate My Call foi um novo recurso nos clientes do Skype for Business 2015 e 2016 no Windows que oferece às empresas uma maneira de obter comentários de seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="e2f86-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="e2f86-106">A janela Rate My Call oferece um sistema de classificação "estrela" e tokens predefinidos para chamadas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e2f86-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="e2f86-107">Além disso, os administradores podem habilitar um campo personalizado para fornecer comentários.</span><span class="sxs-lookup"><span data-stu-id="e2f86-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="e2f86-108">Taxa de coleta os dados de chamadas não estão incluídos atualmente em nenhum relatório de monitoramento existente, mas têm um relatório de monitoramento separado.</span><span class="sxs-lookup"><span data-stu-id="e2f86-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="e2f86-109">Os dados são coletados em tabelas SQL que podem ser acessadas executando consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="e2f86-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="e2f86-110">Pré-requisitos de taxa de chamada</span><span class="sxs-lookup"><span data-stu-id="e2f86-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="e2f86-111">Antes que os usuários em sua implantação do Skype for Business Server possam acessar a funcionalidade de Tarifa de minha chamada, o conjunto de componentes a seguir deve ser implantado e configurado:</span><span class="sxs-lookup"><span data-stu-id="e2f86-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="e2f86-112">Você deve ter o Skype for Business Server instalado (versão 9160 ou posterior).</span><span class="sxs-lookup"><span data-stu-id="e2f86-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="e2f86-113">Peça que seus usuários instalem e atualizem para a versão mais recente do Skype for Business e também solicitem o uso da interface do usuário do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e2f86-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="e2f86-114">Os usuários devem estar hospedados no pool de front-ends do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2f86-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="e2f86-115">Você deve ter um banco de dados de monitoramento do Skype for Business Server implantado e associado aos seus pools do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2f86-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="e2f86-116">Recomendamos implantar o painel de qualidade de chamada (CQD).</span><span class="sxs-lookup"><span data-stu-id="e2f86-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="e2f86-117">Configurar taxa de minha chamada</span><span class="sxs-lookup"><span data-stu-id="e2f86-117">Configure Rate my Call</span></span>

<span data-ttu-id="e2f86-118">O recurso Rate My Call é habilitado por padrão na política de cliente com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e2f86-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="e2f86-119">Porcentagem de exibição da minha chamada em taxa de 10%</span><span class="sxs-lookup"><span data-stu-id="e2f86-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="e2f86-120">Taxa de minha chamada permitir comentários do usuário personalizado-desabilitado</span><span class="sxs-lookup"><span data-stu-id="e2f86-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="e2f86-121">No entanto, não há nenhuma ação necessária para habilitar o recurso base, mas se você quiser comentários personalizados, será necessário habilitá-lo separadamente.</span><span class="sxs-lookup"><span data-stu-id="e2f86-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="e2f86-122">O cmdlet do Windows PowerShell a seguir é um exemplo de habilitar o feedback personalizado do usuário final e alterar o intervalo de 10% para 80%.</span><span class="sxs-lookup"><span data-stu-id="e2f86-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="e2f86-123">Acessar dados da taxa de chamada My</span><span class="sxs-lookup"><span data-stu-id="e2f86-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="e2f86-124">Dados de usuários são coletados em duas tabelas no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="e2f86-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="e2f86-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Esta tabela contém resultados de sondagem de token por usuários finais.</span><span class="sxs-lookup"><span data-stu-id="e2f86-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="e2f86-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Esta tabela contém definições de token.</span><span class="sxs-lookup"><span data-stu-id="e2f86-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="e2f86-127">As definições de token são codificadas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e2f86-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e2f86-128">1 </span><span class="sxs-lookup"><span data-stu-id="e2f86-128">1</span></span>  <br/> |<span data-ttu-id="e2f86-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="e2f86-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="e2f86-130">2 </span><span class="sxs-lookup"><span data-stu-id="e2f86-130">2</span></span>  <br/> | <span data-ttu-id="e2f86-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="e2f86-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="e2f86-132">3 </span><span class="sxs-lookup"><span data-stu-id="e2f86-132">3</span></span>  <br/> | <span data-ttu-id="e2f86-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="e2f86-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="e2f86-134">4 </span><span class="sxs-lookup"><span data-stu-id="e2f86-134">4</span></span>  <br/> |<span data-ttu-id="e2f86-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="e2f86-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="e2f86-136">5 </span><span class="sxs-lookup"><span data-stu-id="e2f86-136">5</span></span>  <br/> |<span data-ttu-id="e2f86-137">Eco</span><span class="sxs-lookup"><span data-stu-id="e2f86-137">Echo</span></span>  <br/> |
|<span data-ttu-id="e2f86-138"> 21 </span><span class="sxs-lookup"><span data-stu-id="e2f86-138">21</span></span>  <br/> | <span data-ttu-id="e2f86-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="e2f86-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="e2f86-140">22</span><span class="sxs-lookup"><span data-stu-id="e2f86-140">22</span></span>  <br/> | <span data-ttu-id="e2f86-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="e2f86-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="e2f86-142">23</span><span class="sxs-lookup"><span data-stu-id="e2f86-142">23</span></span>  <br/> | <span data-ttu-id="e2f86-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="e2f86-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="e2f86-144">dia</span><span class="sxs-lookup"><span data-stu-id="e2f86-144">24</span></span>  <br/> | <span data-ttu-id="e2f86-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="e2f86-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="e2f86-146">25</span><span class="sxs-lookup"><span data-stu-id="e2f86-146">25</span></span>  <br/> | <span data-ttu-id="e2f86-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="e2f86-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="e2f86-148">101</span><span class="sxs-lookup"><span data-stu-id="e2f86-148">101</span></span>  <br/> |<span data-ttu-id="e2f86-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="e2f86-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="e2f86-150">102</span><span class="sxs-lookup"><span data-stu-id="e2f86-150">102</span></span>  <br/> |<span data-ttu-id="e2f86-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="e2f86-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="e2f86-152">103</span><span class="sxs-lookup"><span data-stu-id="e2f86-152">103</span></span>  <br/> |<span data-ttu-id="e2f86-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="e2f86-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="e2f86-154">104</span><span class="sxs-lookup"><span data-stu-id="e2f86-154">104</span></span>  <br/> |<span data-ttu-id="e2f86-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="e2f86-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="e2f86-156">105</span><span class="sxs-lookup"><span data-stu-id="e2f86-156">105</span></span>  <br/> |<span data-ttu-id="e2f86-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="e2f86-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="e2f86-158">106</span><span class="sxs-lookup"><span data-stu-id="e2f86-158">106</span></span>  <br/> |<span data-ttu-id="e2f86-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="e2f86-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="e2f86-160">107</span><span class="sxs-lookup"><span data-stu-id="e2f86-160">107</span></span>  <br/> |<span data-ttu-id="e2f86-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="e2f86-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="e2f86-162">108</span><span class="sxs-lookup"><span data-stu-id="e2f86-162">108</span></span>  <br/> |<span data-ttu-id="e2f86-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="e2f86-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="e2f86-164">109</span><span class="sxs-lookup"><span data-stu-id="e2f86-164">109</span></span>  <br/> |<span data-ttu-id="e2f86-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="e2f86-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="e2f86-166">201</span><span class="sxs-lookup"><span data-stu-id="e2f86-166">201</span></span>  <br/> |<span data-ttu-id="e2f86-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="e2f86-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="e2f86-168">202</span><span class="sxs-lookup"><span data-stu-id="e2f86-168">202</span></span>  <br/> |<span data-ttu-id="e2f86-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="e2f86-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="e2f86-170">203</span><span class="sxs-lookup"><span data-stu-id="e2f86-170">203</span></span>  <br/> |<span data-ttu-id="e2f86-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="e2f86-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="e2f86-172">204</span><span class="sxs-lookup"><span data-stu-id="e2f86-172">204</span></span>  <br/> |<span data-ttu-id="e2f86-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="e2f86-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="e2f86-174">205</span><span class="sxs-lookup"><span data-stu-id="e2f86-174">205</span></span>  <br/> |<span data-ttu-id="e2f86-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="e2f86-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="e2f86-176">206</span><span class="sxs-lookup"><span data-stu-id="e2f86-176">206</span></span>  <br/> |<span data-ttu-id="e2f86-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="e2f86-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="e2f86-178">207</span><span class="sxs-lookup"><span data-stu-id="e2f86-178">207</span></span>  <br/> |<span data-ttu-id="e2f86-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="e2f86-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="e2f86-180">208</span><span class="sxs-lookup"><span data-stu-id="e2f86-180">208</span></span>  <br/> |<span data-ttu-id="e2f86-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="e2f86-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="e2f86-182">301</span><span class="sxs-lookup"><span data-stu-id="e2f86-182">301</span></span>  <br/> |<span data-ttu-id="e2f86-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="e2f86-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="e2f86-184">401</span><span class="sxs-lookup"><span data-stu-id="e2f86-184">401</span></span>  <br/> |<span data-ttu-id="e2f86-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="e2f86-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="e2f86-186">402</span><span class="sxs-lookup"><span data-stu-id="e2f86-186">402</span></span>  <br/> |<span data-ttu-id="e2f86-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="e2f86-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="e2f86-188">403</span><span class="sxs-lookup"><span data-stu-id="e2f86-188">403</span></span>  <br/> |<span data-ttu-id="e2f86-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="e2f86-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="e2f86-190">404</span><span class="sxs-lookup"><span data-stu-id="e2f86-190">404</span></span>  <br/> |<span data-ttu-id="e2f86-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="e2f86-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="e2f86-192">405</span><span class="sxs-lookup"><span data-stu-id="e2f86-192">405</span></span>  <br/> |<span data-ttu-id="e2f86-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="e2f86-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="e2f86-194">406</span><span class="sxs-lookup"><span data-stu-id="e2f86-194">406</span></span>  <br/> |<span data-ttu-id="e2f86-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="e2f86-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="e2f86-196">407</span><span class="sxs-lookup"><span data-stu-id="e2f86-196">407</span></span>  <br/> |<span data-ttu-id="e2f86-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="e2f86-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="e2f86-198">408</span><span class="sxs-lookup"><span data-stu-id="e2f86-198">408</span></span>  <br/> |<span data-ttu-id="e2f86-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="e2f86-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="e2f86-200">501</span><span class="sxs-lookup"><span data-stu-id="e2f86-200">501</span></span>  <br/> |<span data-ttu-id="e2f86-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="e2f86-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="e2f86-202">502</span><span class="sxs-lookup"><span data-stu-id="e2f86-202">502</span></span>  <br/> |<span data-ttu-id="e2f86-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="e2f86-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="e2f86-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Esta tabela contém resultados de pesquisa de votação de "estrela" e comentários do cliente, se habilitado.</span><span class="sxs-lookup"><span data-stu-id="e2f86-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="e2f86-205">Os dados de tabelas podem ser chamados usando uma consulta **Select \* from [Table.Name]** ou usando o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e2f86-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="e2f86-206">As seguintes consultas SQL podem ser usadas:</span><span class="sxs-lookup"><span data-stu-id="e2f86-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="e2f86-207">**Áudio**</span><span class="sxs-lookup"><span data-stu-id="e2f86-207">**Audio**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="e2f86-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="e2f86-208">**Video**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="e2f86-209">Atualizando definições de token</span><span class="sxs-lookup"><span data-stu-id="e2f86-209">Updating Token Definitions</span></span>

<span data-ttu-id="e2f86-210">Os clientes mais recentes do Skype for Business relatam novas IDs de token de problema ( \> 100) que podem não estar presentes em seu [QoeMetrics]. [ dbo]. Tabela [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="e2f86-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="e2f86-211">Para atualizar a tabela de banco de dados com as definições de token mais recentes, o comando SQL abaixo pode ser executado no banco de dados de monitoramento usando o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e2f86-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="e2f86-212">Este comando substituirá todas as entradas no [QoeMetrics]. [dbo]. Tabela [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="e2f86-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


