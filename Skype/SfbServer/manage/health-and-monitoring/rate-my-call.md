---
title: Rate My Call no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/13/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumo: Saiba sobre o recurso de taxa de chamada Meu Skype para Business Server 2015.'
ms.openlocfilehash: 1e0088c563f38be59bda0fad10dbd367ea0646e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="rate-my-call-in-skype-for-business-server-2015"></a><span data-ttu-id="0992c-103">Rate My Call no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0992c-103">Rate my Call in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0992c-104">**Resumo:** Saiba mais sobre o recurso de taxa de chamada Meu Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0992c-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0992c-105">Taxa de chamada My é um novo recurso do Skype para 2015 de negócios e clientes de 2016 no Windows que oferece uma maneira de obter feedback de seus usuários finais de empresas.</span><span class="sxs-lookup"><span data-stu-id="0992c-105">Rate My Call is a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>
  
<span data-ttu-id="0992c-106">A janela de taxa de chamada My oferece um sistema de classificação "star" e tokens predefinidos para as chamadas de áudio e vídeos.</span><span class="sxs-lookup"><span data-stu-id="0992c-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="0992c-107">Além disso, os administradores podem habilitar um campo personalizado fornecer comentários.</span><span class="sxs-lookup"><span data-stu-id="0992c-107">In addition, administrators can enable a custom field to provide feedback.</span></span>
  
<span data-ttu-id="0992c-108">Atualmente, os dados coletados do recurso Rate My Call não estão incluídos em nenhum relatório de monitoramento existente, mas sim em um relatório de monitoramento separado.</span><span class="sxs-lookup"><span data-stu-id="0992c-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="0992c-109">Dados são coletados nas tabelas do SQL que podem ser acessadas executando consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="0992c-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>
  
## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="0992c-110">Classifique os pré-requisitos minha chamada</span><span class="sxs-lookup"><span data-stu-id="0992c-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="0992c-111">Antes que os usuários na sua Skype para implantação de servidor de negócios podem acessar a funcionalidade de taxa de chamada Meu, o seguinte conjunto de componentes deve ser implantado e configurado:</span><span class="sxs-lookup"><span data-stu-id="0992c-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>
  
-  <span data-ttu-id="0992c-112">Você deve ter Skype para Business Server instalado (versão 9160 ou posterior).</span><span class="sxs-lookup"><span data-stu-id="0992c-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>
    
- <span data-ttu-id="0992c-113">Ter seus usuários a instalar e atualizar para a versão mais recente do Skype para negócios e também pedir que eles usem o Skype para interface de usuário de negócios.</span><span class="sxs-lookup"><span data-stu-id="0992c-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>
    
- <span data-ttu-id="0992c-114">Os usuários devem ser hospedados no Skype para pool de Front End do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0992c-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>
    
- <span data-ttu-id="0992c-115">Você deve ter um Skype para Business Server monitoramento banco de dados implantado e associado ao seu Skype para pools de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0992c-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>
    
- <span data-ttu-id="0992c-116">Recomendamos a implantação do Painel de Qualidade da Chamada (CQD, Call Quality Dashboard).</span><span class="sxs-lookup"><span data-stu-id="0992c-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>
    
## <a name="configure-rate-my-call"></a><span data-ttu-id="0992c-117">Configurar a taxa de minha chamada</span><span class="sxs-lookup"><span data-stu-id="0992c-117">Configure Rate my Call</span></span>

<span data-ttu-id="0992c-118">O recurso chamada de minha taxa é habilitado por padrão na política de cliente com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="0992c-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>
  
- <span data-ttu-id="0992c-119">Taxa de porcentagem de exibição minha chamada - 10%</span><span class="sxs-lookup"><span data-stu-id="0992c-119">Rate My Call Display Percentage - 10%</span></span>
    
- <span data-ttu-id="0992c-120">Classifique minha chamada permitir personalizado comentários do usuário - desabilitado</span><span class="sxs-lookup"><span data-stu-id="0992c-120">Rate My Call Allow Custom User Feedback - disabled</span></span>
    
<span data-ttu-id="0992c-121">Não há nenhuma ação é necessária para habilitar o recurso de base, no entanto, mas se desejar receber comentários personalizado, você precisará ativá-la separadamente.</span><span class="sxs-lookup"><span data-stu-id="0992c-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="0992c-122">O seguinte cmdlet do Windows PowerShell é um exemplo de comentários do usuário personalizada do final de habilitação e alterando o intervalo de 10% para 80%.</span><span class="sxs-lookup"><span data-stu-id="0992c-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 

```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="0992c-123">Acessando a taxa de meus dados de chamada</span><span class="sxs-lookup"><span data-stu-id="0992c-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="0992c-124">Dados de usuários são coletados em duas tabelas do banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="0992c-124">Data from users is collected in two tables in the monitoring database.</span></span>
  
 <span data-ttu-id="0992c-125">**[QoeMetrics]. dbo. [CallQualityFeedbackToken]** -Esta tabela contém os resultados da sondagem token por usuários finais.</span><span class="sxs-lookup"><span data-stu-id="0992c-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>
  
 <span data-ttu-id="0992c-126">**[QoeMetrics]. dbo. [CallQualityFeedbackTokenDef]** -Esta tabela contém definições de tokens.</span><span class="sxs-lookup"><span data-stu-id="0992c-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>
  
<span data-ttu-id="0992c-127">Definições de tokens são codificadas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0992c-127">Token definitions are coded as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0992c-128">1</span><span class="sxs-lookup"><span data-stu-id="0992c-128">1</span></span>  <br/> |<span data-ttu-id="0992c-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="0992c-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="0992c-130">2</span><span class="sxs-lookup"><span data-stu-id="0992c-130">2</span></span>  <br/> | <span data-ttu-id="0992c-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="0992c-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="0992c-132">3</span><span class="sxs-lookup"><span data-stu-id="0992c-132">3</span></span>  <br/> | <span data-ttu-id="0992c-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="0992c-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="0992c-134">4</span><span class="sxs-lookup"><span data-stu-id="0992c-134">4</span></span>  <br/> |<span data-ttu-id="0992c-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="0992c-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="0992c-136">5</span><span class="sxs-lookup"><span data-stu-id="0992c-136">5</span></span>  <br/> |<span data-ttu-id="0992c-137">Eco</span><span class="sxs-lookup"><span data-stu-id="0992c-137">Echo</span></span>  <br/> |
|<span data-ttu-id="0992c-138">21</span><span class="sxs-lookup"><span data-stu-id="0992c-138">21</span></span>  <br/> | <span data-ttu-id="0992c-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="0992c-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="0992c-140">22</span><span class="sxs-lookup"><span data-stu-id="0992c-140">22</span></span>  <br/> | <span data-ttu-id="0992c-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="0992c-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="0992c-142">23</span><span class="sxs-lookup"><span data-stu-id="0992c-142">23</span></span>  <br/> | <span data-ttu-id="0992c-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="0992c-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="0992c-144">24</span><span class="sxs-lookup"><span data-stu-id="0992c-144">24</span></span>  <br/> | <span data-ttu-id="0992c-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="0992c-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="0992c-146">25</span><span class="sxs-lookup"><span data-stu-id="0992c-146">25</span></span>  <br/> | <span data-ttu-id="0992c-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="0992c-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="0992c-148">101</span><span class="sxs-lookup"><span data-stu-id="0992c-148">101</span></span>  <br/> |<span data-ttu-id="0992c-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="0992c-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="0992c-150">102</span><span class="sxs-lookup"><span data-stu-id="0992c-150">102</span></span>  <br/> |<span data-ttu-id="0992c-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="0992c-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="0992c-152">103</span><span class="sxs-lookup"><span data-stu-id="0992c-152">103</span></span>  <br/> |<span data-ttu-id="0992c-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="0992c-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="0992c-154">104</span><span class="sxs-lookup"><span data-stu-id="0992c-154">104</span></span>  <br/> |<span data-ttu-id="0992c-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="0992c-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="0992c-156">105</span><span class="sxs-lookup"><span data-stu-id="0992c-156">105</span></span>  <br/> |<span data-ttu-id="0992c-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="0992c-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="0992c-158">106</span><span class="sxs-lookup"><span data-stu-id="0992c-158">106</span></span>  <br/> |<span data-ttu-id="0992c-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="0992c-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="0992c-160">107</span><span class="sxs-lookup"><span data-stu-id="0992c-160">107</span></span>  <br/> |<span data-ttu-id="0992c-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="0992c-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="0992c-162">108</span><span class="sxs-lookup"><span data-stu-id="0992c-162">108</span></span>  <br/> |<span data-ttu-id="0992c-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="0992c-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="0992c-164">109</span><span class="sxs-lookup"><span data-stu-id="0992c-164">109</span></span>  <br/> |<span data-ttu-id="0992c-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="0992c-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="0992c-166">201</span><span class="sxs-lookup"><span data-stu-id="0992c-166">201</span></span>  <br/> |<span data-ttu-id="0992c-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="0992c-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="0992c-168">202</span><span class="sxs-lookup"><span data-stu-id="0992c-168">202</span></span>  <br/> |<span data-ttu-id="0992c-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="0992c-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="0992c-170">203</span><span class="sxs-lookup"><span data-stu-id="0992c-170">203</span></span>  <br/> |<span data-ttu-id="0992c-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="0992c-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="0992c-172">204</span><span class="sxs-lookup"><span data-stu-id="0992c-172">204</span></span>  <br/> |<span data-ttu-id="0992c-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="0992c-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="0992c-174">205</span><span class="sxs-lookup"><span data-stu-id="0992c-174">205</span></span>  <br/> |<span data-ttu-id="0992c-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="0992c-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="0992c-176">206</span><span class="sxs-lookup"><span data-stu-id="0992c-176">206</span></span>  <br/> |<span data-ttu-id="0992c-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="0992c-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="0992c-178">207</span><span class="sxs-lookup"><span data-stu-id="0992c-178">207</span></span>  <br/> |<span data-ttu-id="0992c-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="0992c-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="0992c-180">208</span><span class="sxs-lookup"><span data-stu-id="0992c-180">208</span></span>  <br/> |<span data-ttu-id="0992c-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="0992c-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="0992c-182">301</span><span class="sxs-lookup"><span data-stu-id="0992c-182">301</span></span>  <br/> |<span data-ttu-id="0992c-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="0992c-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="0992c-184">401</span><span class="sxs-lookup"><span data-stu-id="0992c-184">401</span></span>  <br/> |<span data-ttu-id="0992c-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="0992c-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="0992c-186">402</span><span class="sxs-lookup"><span data-stu-id="0992c-186">402</span></span>  <br/> |<span data-ttu-id="0992c-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="0992c-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="0992c-188">403</span><span class="sxs-lookup"><span data-stu-id="0992c-188">403</span></span>  <br/> |<span data-ttu-id="0992c-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="0992c-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="0992c-190">404</span><span class="sxs-lookup"><span data-stu-id="0992c-190">404</span></span>  <br/> |<span data-ttu-id="0992c-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="0992c-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="0992c-192">405</span><span class="sxs-lookup"><span data-stu-id="0992c-192">405</span></span>  <br/> |<span data-ttu-id="0992c-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="0992c-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="0992c-194">406</span><span class="sxs-lookup"><span data-stu-id="0992c-194">406</span></span>  <br/> |<span data-ttu-id="0992c-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="0992c-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="0992c-196">407</span><span class="sxs-lookup"><span data-stu-id="0992c-196">407</span></span>  <br/> |<span data-ttu-id="0992c-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="0992c-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="0992c-198">408</span><span class="sxs-lookup"><span data-stu-id="0992c-198">408</span></span>  <br/> |<span data-ttu-id="0992c-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="0992c-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="0992c-200">501</span><span class="sxs-lookup"><span data-stu-id="0992c-200">501</span></span>  <br/> |<span data-ttu-id="0992c-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="0992c-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="0992c-202">502</span><span class="sxs-lookup"><span data-stu-id="0992c-202">502</span></span>  <br/> |<span data-ttu-id="0992c-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="0992c-203">Reliabilty_Invite</span></span>  <br/> |
   
 <span data-ttu-id="0992c-204">**[QoeMetrics]. dbo. [CallQualityFeedback]** Esta tabela contém os resultados de sondagem de comentários de votação e atendimento ao cliente "Estrela" se for habilitada.</span><span class="sxs-lookup"><span data-stu-id="0992c-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>
  
<span data-ttu-id="0992c-205">Dados de tabelas podem ser chamados usando um **Selecione \* de [Table.Name]** consulta ou usando o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0992c-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>
  
<span data-ttu-id="0992c-206">As seguintes consultas SQL podem ser usadas:</span><span class="sxs-lookup"><span data-stu-id="0992c-206">The following SQL queries can be used:</span></span>
  
 <span data-ttu-id="0992c-207">**Áudio**</span><span class="sxs-lookup"><span data-stu-id="0992c-207">**Audio**</span></span>
  
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

 <span data-ttu-id="0992c-208">**Vídeo**</span><span class="sxs-lookup"><span data-stu-id="0992c-208">**Video**</span></span>
  
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

## <a name="updating-token-definitions"></a><span data-ttu-id="0992c-209">Atualizando as definições de Token</span><span class="sxs-lookup"><span data-stu-id="0992c-209">Updating Token Definitions</span></span>

<span data-ttu-id="0992c-210">O mais recente Skype para clientes corporativos relatar novo token problema IDs (\> 100) que podem não estar presentes em seu [QoeMetrics]. dbo. Tabela [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="0992c-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="0992c-211">Para atualizar a tabela de banco de dados com as definições de tokens mais recentes, o comando abaixo SQL pode ser executado no monitoramento banco de dados usando o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0992c-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="0992c-212">Esse comando irá substituir todas as entradas em [QoeMetrics]. dbo. Tabela [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="0992c-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>
  
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


