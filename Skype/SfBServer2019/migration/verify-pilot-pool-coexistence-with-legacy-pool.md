---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: ed3809bdde3109bdbd341c42eed0dc1d8cecd11f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231340"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="f6b12-103">Verificar coexistência de pool piloto com pool herdado</span><span class="sxs-lookup"><span data-stu-id="f6b12-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="f6b12-104">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="f6b12-104">**In this article**</span></span>
  
[<span data-ttu-id="f6b12-105">Verifique se que Skype para Business Server 2019 serviços foram iniciados</span><span class="sxs-lookup"><span data-stu-id="f6b12-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="f6b12-106">Abra o Skype para painel de controle do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f6b12-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="f6b12-107">Não tente abrir a topologia no construtor de topologia herdada</span><span class="sxs-lookup"><span data-stu-id="f6b12-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="f6b12-108">Depois de implantar o pool piloto, você precisará verificar a coexistência dos dois pools usando as ferramentas administrativas para exibir as informações do pool.</span><span class="sxs-lookup"><span data-stu-id="f6b12-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="f6b12-109">Para Skype para pools herdados e pools de negócios 2019 de servidor, você deve usar o Skype para as ferramentas do painel de controle do Business Server 2019 e o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="f6b12-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="f6b12-110">Verifique se que Skype para Business Server 2019 serviços foram iniciados</span><span class="sxs-lookup"><span data-stu-id="f6b12-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="f6b12-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b12-111"></span></span>

1. <span data-ttu-id="f6b12-112">No Skype para Business Server 2019 servidor Front-End, navegue até o applet ferramentas administrativas \ Serviços.</span><span class="sxs-lookup"><span data-stu-id="f6b12-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="f6b12-113">Verifique se os seguintes serviços estão funcionando no servidor Front-End:</span><span class="sxs-lookup"><span data-stu-id="f6b12-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="f6b12-114">Agente de Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="f6b12-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="f6b12-115">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="f6b12-115">Application Sharing</span></span>
    - <span data-ttu-id="f6b12-116">Serviço de teste de áudio</span><span class="sxs-lookup"><span data-stu-id="f6b12-116">Audio Test Service</span></span>
    - <span data-ttu-id="f6b12-117">Conferência de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="f6b12-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="f6b12-118">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="f6b12-118">Call Park</span></span>
    - <span data-ttu-id="f6b12-119">Comunicado de conferência</span><span class="sxs-lookup"><span data-stu-id="f6b12-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="f6b12-120">Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="f6b12-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="f6b12-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="f6b12-121">Front-End</span></span>
    - <span data-ttu-id="f6b12-122">Conferência de IM</span><span class="sxs-lookup"><span data-stu-id="f6b12-122">IM Conferencing</span></span>
    - <span data-ttu-id="f6b12-123">Mediação</span><span class="sxs-lookup"><span data-stu-id="f6b12-123">Mediation</span></span>
    - <span data-ttu-id="f6b12-124">Agente replicador de réplica</span><span class="sxs-lookup"><span data-stu-id="f6b12-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="f6b12-125">Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="f6b12-125">Response Group</span></span>
    - <span data-ttu-id="f6b12-126">Webconferência</span><span class="sxs-lookup"><span data-stu-id="f6b12-126">Web Conferencing</span></span>
    - <span data-ttu-id="f6b12-127">Conversão de Gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="f6b12-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="f6b12-128">Abra o Skype para painel de controle do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f6b12-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="f6b12-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b12-129"></span></span>

<span data-ttu-id="f6b12-130">Do servidor Front-End no seu Skype para implantação Business Server 2019, abra o Skype para painel de controle do Business Server 2019 e selecione o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="f6b12-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="f6b12-131">Repita o procedimento para abrir o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="f6b12-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f6b12-132">Em Skype para Business Server 2019, você deve atualizar Silverlight para Silverlight versão 5 antes de usar o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f6b12-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="f6b12-133">Essa topologia agora inclui herdado e Skype Business Server 2019 para funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="f6b12-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="f6b12-134">Não tente abrir a topologia no construtor de topologia herdada</span><span class="sxs-lookup"><span data-stu-id="f6b12-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="f6b12-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b12-135"></span></span>

<span data-ttu-id="f6b12-136">Se você tentar abrir a topologia usando o construtor de topologia herdada, você encontrará o erro abaixo.</span><span class="sxs-lookup"><span data-stu-id="f6b12-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="f6b12-137">A topologia só pode ser exibida usando Skype para o construtor de topologias do Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6b12-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="f6b12-138">O Skype para o construtor de topologias do Business Server 2019 deve ser usado para criar pools do Skype para Business Server 2019 e a instalar herdada.</span><span class="sxs-lookup"><span data-stu-id="f6b12-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

