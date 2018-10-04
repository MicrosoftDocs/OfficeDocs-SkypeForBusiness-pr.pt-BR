---
title: Taxa, minha chamada em Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumo: Saiba sobre o recurso de taxa de chamada Meu Skype para Business Server.'
ms.openlocfilehash: 3e4e2f63c9d61bacab73838933ef89130714f6f0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373470"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="0369f-103">Taxa, minha chamada em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0369f-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="0369f-104">**Resumo:** Saiba mais sobre o recurso de taxa de chamada Meu Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0369f-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="0369f-105">Taxa de chamada Meu era um novo recurso do Skype para 2015 de negócios e clientes de 2016 no Windows que oferece uma maneira de obter feedback de seus usuários finais de empresas.</span><span class="sxs-lookup"><span data-stu-id="0369f-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="0369f-106">A janela de taxa de chamada My oferece um sistema de classificação "star" e tokens predefinidos para as chamadas de áudio e vídeos.</span><span class="sxs-lookup"><span data-stu-id="0369f-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="0369f-107">Além disso, os administradores podem habilitar um campo personalizado fornecer comentários.</span><span class="sxs-lookup"><span data-stu-id="0369f-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="0369f-108">Atualmente, os dados coletados do recurso Rate My Call não estão incluídos em nenhum relatório de monitoramento existente, mas sim em um relatório de monitoramento separado.</span><span class="sxs-lookup"><span data-stu-id="0369f-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="0369f-109">Dados são coletados nas tabelas do SQL que podem ser acessadas executando consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="0369f-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="0369f-110">Pré-requisitos do Rate My Call</span><span class="sxs-lookup"><span data-stu-id="0369f-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="0369f-111">Antes que os usuários na sua Skype para implantação de servidor de negócios podem acessar a funcionalidade de taxa de chamada Meu, o seguinte conjunto de componentes deve ser implantado e configurado:</span><span class="sxs-lookup"><span data-stu-id="0369f-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="0369f-112">Você deve ter Skype para Business Server instalado (versão 9160 ou posterior).</span><span class="sxs-lookup"><span data-stu-id="0369f-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="0369f-113">Ter seus usuários a instalar e atualizar para a versão mais recente do Skype para negócios e também pedir que eles usem o Skype para interface de usuário de negócios.</span><span class="sxs-lookup"><span data-stu-id="0369f-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="0369f-114">Os usuários devem ser hospedados no Skype para pool de Front End do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0369f-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="0369f-115">Você deve ter um Skype para Business Server monitoramento banco de dados implantado e associado ao seu Skype para pools de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0369f-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="0369f-116">Recomendamos a implantação do Painel de Qualidade da Chamada (CQD, Call Quality Dashboard).</span><span class="sxs-lookup"><span data-stu-id="0369f-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="0369f-117">Configurar o recurso Rate my Call</span><span class="sxs-lookup"><span data-stu-id="0369f-117">Configure Rate my Call</span></span>

<span data-ttu-id="0369f-118">O recurso chamada de minha taxa é habilitado por padrão na política de cliente com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="0369f-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="0369f-119">Taxa de porcentagem de exibição minha chamada - 10%</span><span class="sxs-lookup"><span data-stu-id="0369f-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="0369f-120">Classifique minha chamada permitir personalizado comentários do usuário - desabilitado</span><span class="sxs-lookup"><span data-stu-id="0369f-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="0369f-121">Não há nenhuma ação é necessária para habilitar o recurso de base, no entanto, mas se desejar receber comentários personalizado, você precisará ativá-la separadamente.</span><span class="sxs-lookup"><span data-stu-id="0369f-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="0369f-122">O seguinte cmdlet do Windows PowerShell é um exemplo de comentários do usuário personalizada do final de habilitação e alterando o intervalo de 10% para 80%.</span><span class="sxs-lookup"><span data-stu-id="0369f-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="0369f-123">Acessando os dados de Rate My Call</span><span class="sxs-lookup"><span data-stu-id="0369f-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="0369f-124">Dados de usuários são coletados em duas tabelas do banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="0369f-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="0369f-125">**[QoeMetrics]. dbo. [CallQualityFeedbackToken]** -Esta tabela contém os resultados da sondagem token por usuários finais.</span><span class="sxs-lookup"><span data-stu-id="0369f-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="0369f-126">**[QoeMetrics]. dbo. [CallQualityFeedbackTokenDef]** -Esta tabela contém definições de tokens.</span><span class="sxs-lookup"><span data-stu-id="0369f-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="0369f-127">As definições do token são codificadas da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0369f-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0369f-128">1</span><span class="sxs-lookup"><span data-stu-id="0369f-128">1</span></span>  <br/> |<span data-ttu-id="0369f-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="0369f-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="0369f-130">2</span><span class="sxs-lookup"><span data-stu-id="0369f-130">2</span></span>  <br/> | <span data-ttu-id="0369f-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="0369f-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="0369f-132">3</span><span class="sxs-lookup"><span data-stu-id="0369f-132">3</span></span>  <br/> | <span data-ttu-id="0369f-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="0369f-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="0369f-134">4</span><span class="sxs-lookup"><span data-stu-id="0369f-134">4</span></span>  <br/> |<span data-ttu-id="0369f-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="0369f-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="0369f-136">5</span><span class="sxs-lookup"><span data-stu-id="0369f-136">5</span></span>  <br/> |<span data-ttu-id="0369f-137">Eco</span><span class="sxs-lookup"><span data-stu-id="0369f-137">Echo</span></span>  <br/> |
|<span data-ttu-id="0369f-138">21</span><span class="sxs-lookup"><span data-stu-id="0369f-138">21</span></span>  <br/> | <span data-ttu-id="0369f-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="0369f-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="0369f-140">22</span><span class="sxs-lookup"><span data-stu-id="0369f-140">22</span></span>  <br/> | <span data-ttu-id="0369f-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="0369f-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="0369f-142">23</span><span class="sxs-lookup"><span data-stu-id="0369f-142">23</span></span>  <br/> | <span data-ttu-id="0369f-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="0369f-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="0369f-144">24</span><span class="sxs-lookup"><span data-stu-id="0369f-144">24</span></span>  <br/> | <span data-ttu-id="0369f-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="0369f-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="0369f-146">25</span><span class="sxs-lookup"><span data-stu-id="0369f-146">25</span></span>  <br/> | <span data-ttu-id="0369f-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="0369f-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="0369f-148">101</span><span class="sxs-lookup"><span data-stu-id="0369f-148">101</span></span>  <br/> |<span data-ttu-id="0369f-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="0369f-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="0369f-150">102</span><span class="sxs-lookup"><span data-stu-id="0369f-150">102</span></span>  <br/> |<span data-ttu-id="0369f-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="0369f-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="0369f-152">103</span><span class="sxs-lookup"><span data-stu-id="0369f-152">103</span></span>  <br/> |<span data-ttu-id="0369f-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="0369f-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="0369f-154">104</span><span class="sxs-lookup"><span data-stu-id="0369f-154">104</span></span>  <br/> |<span data-ttu-id="0369f-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="0369f-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="0369f-156">105</span><span class="sxs-lookup"><span data-stu-id="0369f-156">105</span></span>  <br/> |<span data-ttu-id="0369f-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="0369f-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="0369f-158">106</span><span class="sxs-lookup"><span data-stu-id="0369f-158">106</span></span>  <br/> |<span data-ttu-id="0369f-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="0369f-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="0369f-160">107</span><span class="sxs-lookup"><span data-stu-id="0369f-160">107</span></span>  <br/> |<span data-ttu-id="0369f-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="0369f-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="0369f-162">108</span><span class="sxs-lookup"><span data-stu-id="0369f-162">108</span></span>  <br/> |<span data-ttu-id="0369f-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="0369f-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="0369f-164">109</span><span class="sxs-lookup"><span data-stu-id="0369f-164">109</span></span>  <br/> |<span data-ttu-id="0369f-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="0369f-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="0369f-166">201</span><span class="sxs-lookup"><span data-stu-id="0369f-166">201</span></span>  <br/> |<span data-ttu-id="0369f-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="0369f-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="0369f-168">202</span><span class="sxs-lookup"><span data-stu-id="0369f-168">202</span></span>  <br/> |<span data-ttu-id="0369f-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="0369f-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="0369f-170">203</span><span class="sxs-lookup"><span data-stu-id="0369f-170">203</span></span>  <br/> |<span data-ttu-id="0369f-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="0369f-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="0369f-172">204</span><span class="sxs-lookup"><span data-stu-id="0369f-172">204</span></span>  <br/> |<span data-ttu-id="0369f-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="0369f-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="0369f-174">205</span><span class="sxs-lookup"><span data-stu-id="0369f-174">205</span></span>  <br/> |<span data-ttu-id="0369f-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="0369f-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="0369f-176">206</span><span class="sxs-lookup"><span data-stu-id="0369f-176">206</span></span>  <br/> |<span data-ttu-id="0369f-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="0369f-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="0369f-178">207</span><span class="sxs-lookup"><span data-stu-id="0369f-178">207</span></span>  <br/> |<span data-ttu-id="0369f-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="0369f-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="0369f-180">208</span><span class="sxs-lookup"><span data-stu-id="0369f-180">208</span></span>  <br/> |<span data-ttu-id="0369f-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="0369f-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="0369f-182">301</span><span class="sxs-lookup"><span data-stu-id="0369f-182">301</span></span>  <br/> |<span data-ttu-id="0369f-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="0369f-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="0369f-184">401</span><span class="sxs-lookup"><span data-stu-id="0369f-184">401</span></span>  <br/> |<span data-ttu-id="0369f-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="0369f-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="0369f-186">402</span><span class="sxs-lookup"><span data-stu-id="0369f-186">402</span></span>  <br/> |<span data-ttu-id="0369f-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="0369f-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="0369f-188">403</span><span class="sxs-lookup"><span data-stu-id="0369f-188">403</span></span>  <br/> |<span data-ttu-id="0369f-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="0369f-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="0369f-190">404</span><span class="sxs-lookup"><span data-stu-id="0369f-190">404</span></span>  <br/> |<span data-ttu-id="0369f-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="0369f-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="0369f-192">405</span><span class="sxs-lookup"><span data-stu-id="0369f-192">405</span></span>  <br/> |<span data-ttu-id="0369f-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="0369f-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="0369f-194">406</span><span class="sxs-lookup"><span data-stu-id="0369f-194">406</span></span>  <br/> |<span data-ttu-id="0369f-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="0369f-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="0369f-196">407</span><span class="sxs-lookup"><span data-stu-id="0369f-196">407</span></span>  <br/> |<span data-ttu-id="0369f-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="0369f-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="0369f-198">408</span><span class="sxs-lookup"><span data-stu-id="0369f-198">408</span></span>  <br/> |<span data-ttu-id="0369f-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="0369f-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="0369f-200">501</span><span class="sxs-lookup"><span data-stu-id="0369f-200">501</span></span>  <br/> |<span data-ttu-id="0369f-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="0369f-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="0369f-202">502</span><span class="sxs-lookup"><span data-stu-id="0369f-202">502</span></span>  <br/> |<span data-ttu-id="0369f-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="0369f-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="0369f-204">**[QoeMetrics]. dbo. [CallQualityFeedback]** Esta tabela contém os resultados de sondagem de comentários de votação e atendimento ao cliente "Estrela" se for habilitada.</span><span class="sxs-lookup"><span data-stu-id="0369f-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="0369f-205">Dados de tabelas podem ser chamados usando um **Selecione \* de [Table.Name]** consulta ou usando o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0369f-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="0369f-206">Podem ser usadas as seguintes consultas em SQL:</span><span class="sxs-lookup"><span data-stu-id="0369f-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="0369f-207">**Áudio**</span><span class="sxs-lookup"><span data-stu-id="0369f-207">**Audio**</span></span>

```
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

 <span data-ttu-id="0369f-208">**Vídeo**</span><span class="sxs-lookup"><span data-stu-id="0369f-208">**Video**</span></span>

```
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

## <a name="updating-token-definitions"></a><span data-ttu-id="0369f-209">Atualizando as definições de Token</span><span class="sxs-lookup"><span data-stu-id="0369f-209">Updating Token Definitions</span></span>

<span data-ttu-id="0369f-210">O mais recente Skype para clientes corporativos relatar novo token problema IDs (\> 100) que podem não estar presentes em seu [QoeMetrics]. dbo. Tabela [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="0369f-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="0369f-211">Para atualizar a tabela de banco de dados com as definições de tokens mais recentes, o comando abaixo SQL pode ser executado no monitoramento banco de dados usando o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0369f-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="0369f-212">Esse comando irá substituir todas as entradas em [QoeMetrics]. dbo. Tabela [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="0369f-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```
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


