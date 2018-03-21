---
title: "Qualidade de chamada de análise de uso chamada solucionar ruim Skype para negócios"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "Use os detalhes de chamada análise sobre dispositivos, redes e conectividade para solucionar problemas de usuário com o Skype para reuniões e chamadas comerciais."
ms.openlocfilehash: 4f43c517beba318889e12fca8b09a488f6da5916
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="2fef5-103">Qualidade de chamada de análise de uso chamada solucionar ruim Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="2fef5-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="2fef5-104">Análise de chamada ajuda você a solucionar problemas de chamada ou a conexão com o Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="2fef5-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="2fef5-105">Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade para as chamadas e reuniões de cada usuário na sua Skype para a conta de negócios.</span><span class="sxs-lookup"><span data-stu-id="2fef5-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="2fef5-106">Se criando, site e de inquilinos informações foram adicionadas para análise de chamada, ele também será mostrado para cada chamada e a sessão.</span><span class="sxs-lookup"><span data-stu-id="2fef5-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="2fef5-107">Informações disponíveis por meio da análise de chamada podem ajudá-lo a descobrir por que um usuário teve uma chamada de baixa ou experiência da reunião.</span><span class="sxs-lookup"><span data-stu-id="2fef5-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="2fef5-108">Solucionar problemas de qualidade de chamada usando a análise de chamada</span><span class="sxs-lookup"><span data-stu-id="2fef5-108">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="2fef5-109">O nível de permissões atribuído a você determina qual tipo de informação que você tem acesso na análise de chamada:</span><span class="sxs-lookup"><span data-stu-id="2fef5-109">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="2fef5-110">**Skype para Business admin**: você tem acesso a todas as informações na análise de chamadas e no Skype para Business Admin center.</span><span class="sxs-lookup"><span data-stu-id="2fef5-110">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="2fef5-111">**Agente de assistência técnica com permissões de nível 1**: você ver um conjunto limitado de dados na análise de chamada.</span><span class="sxs-lookup"><span data-stu-id="2fef5-111">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="2fef5-112">Você pode solucionar problemas de chamadas, mas você entregar problemas com reuniões para um agente de nível 2.</span><span class="sxs-lookup"><span data-stu-id="2fef5-112">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="2fef5-113">Você não tem acesso ao restante do Skype para Business Admin center.</span><span class="sxs-lookup"><span data-stu-id="2fef5-113">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="2fef5-114">**Agente de assistência técnica com permissões de nível 2**: ver todos os dados disponíveis na análise de chamada e pode ajudar a solucionar problemas com chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="2fef5-114">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="2fef5-115">Você não tem acesso ao restante do Skype para Business Admin center.</span><span class="sxs-lookup"><span data-stu-id="2fef5-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="2fef5-116">Se você precisa de ajuda com permissões, consulte sua Skype para administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="2fef5-116">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="2fef5-117">**Abra o Analytics chamada como um agente de assistência técnica da camada 1 ou camada 2**</span><span class="sxs-lookup"><span data-stu-id="2fef5-117">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="2fef5-118">Vá para o Centro de administração do Office 365 e entrar usando sua conta do trabalho ou da escola.</span><span class="sxs-lookup"><span data-stu-id="2fef5-118">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="2fef5-119">Em seguida, no seu navegador da web vá para *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="2fef5-119">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="2fef5-120">Em **Pesquisa de usuário**, comece a digitar um endereço sip ou o nome do usuário cujas chamadas que você deseja resolver e, em seguida, selecione o usuário na lista.</span><span class="sxs-lookup"><span data-stu-id="2fef5-120">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Captura de tela da caixa de pesquisa de usuário do Analytics chamada no Skype para Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="2fef5-122">No **histórico de chamadas**, selecione a chamada ou reunião que você deseja resolver.</span><span class="sxs-lookup"><span data-stu-id="2fef5-122">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Captura de tela mostra a página do histórico de chamada para um usuário com informações como detalhes de contato do usuário, um resumo da qualidade de 7 dias e atividade para reuniões e chamadas e uma visão geral das datas e horas, destinatários e qualidade de áudio](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="2fef5-124">Selecione a guia **Avançado** e, em seguida, procure por itens amarelos e vermelhos que indicam problemas de chamada de baixa qualidade ou conexão.</span><span class="sxs-lookup"><span data-stu-id="2fef5-124">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="2fef5-125">Nos detalhes da sessão para cada chamada ou reunião, pequenos problemas serão exibidas em amarelo.</span><span class="sxs-lookup"><span data-stu-id="2fef5-125">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="2fef5-126">(Por exemplo, a seguinte captura de tela, os valores são em amarelo para variação média, tremulação máxima e taxa de perda de pacote média.) Se algo é amarelo, ele estiver fora do intervalo normal e ele pode estar contribuindo para o problema, mas é improvável de ser a causa principal do problema.</span><span class="sxs-lookup"><span data-stu-id="2fef5-126">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="2fef5-127">Se algo é vermelho, é um problema significativo e provavelmente é o principal motivo da qualidade da chamada ruim para esta sessão.</span><span class="sxs-lookup"><span data-stu-id="2fef5-127">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Captura de tela mostra a guia Avançado da chamada histórico de um usuário com a seção de rede de entrada expandida para revelar que os dados de variação média, máxima tremulação e taxa de perda de pacote média são mostrados com uma cor amarela, que significa que eles são pequenos problemas.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="2fef5-129">Em casos raros, dados qualidade da experiência não for recebida para sessões de áudio.</span><span class="sxs-lookup"><span data-stu-id="2fef5-129">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="2fef5-130">Geralmente, isso é causado pela chamada eliminando e conexão com o cliente abortar.</span><span class="sxs-lookup"><span data-stu-id="2fef5-130">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="2fef5-131">Quando isso acontecer, a classificação de sessão é "não disponível".</span><span class="sxs-lookup"><span data-stu-id="2fef5-131">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="2fef5-132">Para sessões de áudio que tenham dados qualidade da experiência (QoE), a tabela a seguir descreve os principais problemas que qualificar uma sessão como "ruim".</span><span class="sxs-lookup"><span data-stu-id="2fef5-132">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="2fef5-133">**Problema**</span><span class="sxs-lookup"><span data-stu-id="2fef5-133">**Issue**</span></span>|<span data-ttu-id="2fef5-134">**Área**</span><span class="sxs-lookup"><span data-stu-id="2fef5-134">**Area**</span></span>|<span data-ttu-id="2fef5-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2fef5-135">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2fef5-136">Configuração da chamada</span><span class="sxs-lookup"><span data-stu-id="2fef5-136">Call setup</span></span>  <br/> |<span data-ttu-id="2fef5-137">Sessão</span><span class="sxs-lookup"><span data-stu-id="2fef5-137">Session</span></span>  <br/> |<span data-ttu-id="2fef5-138">O código de erro 20-29 Ms-diagnóstico indica que a instalação chamada falhou.</span><span class="sxs-lookup"><span data-stu-id="2fef5-138">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="2fef5-139">O usuário não pôde ingressar na chamada ou a reunião.</span><span class="sxs-lookup"><span data-stu-id="2fef5-139">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="2fef5-140">Rede de áudio classificadas chamadas ruins</span><span class="sxs-lookup"><span data-stu-id="2fef5-140">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="2fef5-141">Sessão</span><span class="sxs-lookup"><span data-stu-id="2fef5-141">Session</span></span>  <br/> |<span data-ttu-id="2fef5-142">Problemas de qualidade de rede foram encontrados em áreas como perda de pacotes, tremulação, degradação NMOS, tempo de resposta, ou oculta a proporção.</span><span class="sxs-lookup"><span data-stu-id="2fef5-142">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="2fef5-143">Para obter mais informações sobre as condições usado para classificar as chamadas de baixa, consulte esta [postagem de blog da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="2fef5-143">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="2fef5-144">Dispositivo não funcionando</span><span class="sxs-lookup"><span data-stu-id="2fef5-144">Device not functioning</span></span>  <br/> |<span data-ttu-id="2fef5-145">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="2fef5-145">Device</span></span>  <br/> | <span data-ttu-id="2fef5-146">Um dispositivo não está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="2fef5-146">A device isn't functioning correctly.</span></span> <span data-ttu-id="2fef5-147">Dispositivo não funcionando taxas é:</span><span class="sxs-lookup"><span data-stu-id="2fef5-147">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="2fef5-148">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="2fef5-148">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="2fef5-149">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="2fef5-149">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="2fef5-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2fef5-150">Related topics</span></span>
[<span data-ttu-id="2fef5-151">Configurar a Análise de Chamada do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2fef5-151">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="2fef5-152">Qual é a diferença entre a Análise de Chamada e o Painel de Qualidade de Chamadas?</span><span class="sxs-lookup"><span data-stu-id="2fef5-152">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

