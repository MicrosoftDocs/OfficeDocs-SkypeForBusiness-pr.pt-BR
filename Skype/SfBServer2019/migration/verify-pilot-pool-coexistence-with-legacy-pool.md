---
title: Verificar a coexistência de pool piloto com o pool herdado
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028688"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="adcee-103">Verificar a coexistência de pool piloto com o pool herdado</span><span class="sxs-lookup"><span data-stu-id="adcee-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="adcee-104">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="adcee-104">**In this article**</span></span>
  
[<span data-ttu-id="adcee-105">Verifique se que Skype para Business Server 2019 serviços foram iniciados</span><span class="sxs-lookup"><span data-stu-id="adcee-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="adcee-106">Abra o Skype para painel de controle do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="adcee-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="adcee-107">Não tente abrir a topologia no construtor de topologia herdada</span><span class="sxs-lookup"><span data-stu-id="adcee-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="adcee-108">Depois de implantar o pool piloto, você precisará verificar a coexistência dos dois pools usando as ferramentas administrativas para exibir as informações do pool.</span><span class="sxs-lookup"><span data-stu-id="adcee-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="adcee-109">Para Skype para pools herdados e pools de negócios 2019 de servidor, você deve usar o Skype para as ferramentas do painel de controle do Business Server 2019 e o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="adcee-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="adcee-110">Verifique se que Skype para Business Server 2019 serviços foram iniciados</span><span class="sxs-lookup"><span data-stu-id="adcee-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="adcee-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="adcee-111"></span></span>

1. <span data-ttu-id="adcee-112">No Skype para Business Server 2019 servidor Front-End, navegue até o applet ferramentas administrativas \ Serviços.</span><span class="sxs-lookup"><span data-stu-id="adcee-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="adcee-113">Verifique se os seguintes serviços estão funcionando no servidor Front-End:</span><span class="sxs-lookup"><span data-stu-id="adcee-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="adcee-114">Agente de Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="adcee-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="adcee-115">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="adcee-115">Application Sharing</span></span>
    - <span data-ttu-id="adcee-116">Serviço de teste de áudio</span><span class="sxs-lookup"><span data-stu-id="adcee-116">Audio Test Service</span></span>
    - <span data-ttu-id="adcee-117">Conferência de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="adcee-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="adcee-118">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="adcee-118">Call Park</span></span>
    - <span data-ttu-id="adcee-119">Comunicado de conferência</span><span class="sxs-lookup"><span data-stu-id="adcee-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="adcee-120">Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="adcee-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="adcee-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="adcee-121">Front-End</span></span>
    - <span data-ttu-id="adcee-122">Conferência de IM</span><span class="sxs-lookup"><span data-stu-id="adcee-122">IM Conferencing</span></span>
    - <span data-ttu-id="adcee-123">Mediação</span><span class="sxs-lookup"><span data-stu-id="adcee-123">Mediation</span></span>
    - <span data-ttu-id="adcee-124">Agente replicador de réplica</span><span class="sxs-lookup"><span data-stu-id="adcee-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="adcee-125">Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="adcee-125">Response Group</span></span>
    - <span data-ttu-id="adcee-126">Webconferência</span><span class="sxs-lookup"><span data-stu-id="adcee-126">Web Conferencing</span></span>
    - <span data-ttu-id="adcee-127">Conversão de Gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="adcee-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="adcee-128">Abra o Skype para painel de controle do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="adcee-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="adcee-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="adcee-129"></span></span>

<span data-ttu-id="adcee-130">Do servidor Front-End no seu Skype para implantação Business Server 2019, abra o Skype para painel de controle do Business Server 2019 e selecione o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="adcee-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="adcee-131">Repita o procedimento para abrir o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="adcee-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="adcee-132">Em Skype para Business Server 2019, você deve atualizar Silverlight para Silverlight versão 5 antes de usar o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="adcee-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="adcee-133">Essa topologia agora inclui herdado e Skype Business Server 2019 para funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="adcee-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="adcee-134">Não tente abrir a topologia no construtor de topologia herdada</span><span class="sxs-lookup"><span data-stu-id="adcee-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="adcee-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="adcee-135"></span></span>

<span data-ttu-id="adcee-136">Se você tentar abrir a topologia usando o construtor de topologia herdada, você encontrará o erro abaixo.</span><span class="sxs-lookup"><span data-stu-id="adcee-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="adcee-137">A topologia só pode ser exibida usando Skype para o construtor de topologias do Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="adcee-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="adcee-138">O Skype para o construtor de topologias do Business Server 2019 deve ser usado para criar pools do Skype para Business Server 2019 e a instalar herdada.</span><span class="sxs-lookup"><span data-stu-id="adcee-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

