---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751653"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="04f20-103">Verificar coexistência de pool piloto com pool herdado</span><span class="sxs-lookup"><span data-stu-id="04f20-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="04f20-104">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="04f20-104">**In this article**</span></span>
  
[<span data-ttu-id="04f20-105">Verificar se os serviços do Skype for Business Server 2019 foram iniciados</span><span class="sxs-lookup"><span data-stu-id="04f20-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="04f20-106">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="04f20-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="04f20-107">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="04f20-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="04f20-108">Depois de implantar o pool piloto, você deve verificar a coexistência de dois pools usando ferramentas administrativas para exibir as informações dos pools.</span><span class="sxs-lookup"><span data-stu-id="04f20-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="04f20-109">Para os pools do Skype for Business Server 2019 e pools herdados, você deve usar o painel de controle do Skype for Business Server 2019 e as ferramentas do construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="04f20-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="04f20-110">Verificar se os serviços do Skype for Business Server 2019 foram iniciados</span><span class="sxs-lookup"><span data-stu-id="04f20-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="04f20-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="04f20-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="04f20-112">No servidor front-end do Skype for Business Server 2019, navegue até o mini-aplicativo applet administrativo.</span><span class="sxs-lookup"><span data-stu-id="04f20-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="04f20-113">Verifique se os serviços a seguir estão sendo executados no servidor Front End:</span><span class="sxs-lookup"><span data-stu-id="04f20-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="04f20-114">Agente de serviço de registro em log centralizado</span><span class="sxs-lookup"><span data-stu-id="04f20-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="04f20-115">Compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="04f20-115">Application Sharing</span></span>
    - <span data-ttu-id="04f20-116">Serviço de teste de áudio</span><span class="sxs-lookup"><span data-stu-id="04f20-116">Audio Test Service</span></span>
    - <span data-ttu-id="04f20-117">Audioconferências/Videoconferências</span><span class="sxs-lookup"><span data-stu-id="04f20-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="04f20-118">Estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="04f20-118">Call Park</span></span>
    - <span data-ttu-id="04f20-119">Comunicado de conferência</span><span class="sxs-lookup"><span data-stu-id="04f20-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="04f20-120">Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="04f20-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="04f20-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="04f20-121">Front-End</span></span>
    - <span data-ttu-id="04f20-122">Conferência de IM</span><span class="sxs-lookup"><span data-stu-id="04f20-122">IM Conferencing</span></span>
    - <span data-ttu-id="04f20-123">Mediação</span><span class="sxs-lookup"><span data-stu-id="04f20-123">Mediation</span></span>
    - <span data-ttu-id="04f20-124">Agente replicador de réplica</span><span class="sxs-lookup"><span data-stu-id="04f20-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="04f20-125">Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="04f20-125">Response Group</span></span>
    - <span data-ttu-id="04f20-126">Webconferência</span><span class="sxs-lookup"><span data-stu-id="04f20-126">Web Conferencing</span></span>
    - <span data-ttu-id="04f20-127">Gateway de conversão XMPP</span><span class="sxs-lookup"><span data-stu-id="04f20-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="04f20-128">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="04f20-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="04f20-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="04f20-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="04f20-130">A partir do servidor front-end na sua implantação do Skype for Business Server 2019, abra o painel de controle do Skype for Business Server 2019 e selecione o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="04f20-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="04f20-131">Repita o procedimento para abrir o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04f20-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="04f20-132">No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="04f20-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="04f20-133">Essa topologia agora inclui funções de servidor herdadas e do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04f20-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="04f20-134">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="04f20-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="04f20-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="04f20-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="04f20-136">A topologia só pode ser exibida usando o construtor de topologias do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04f20-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="04f20-137">O construtor de topologias do Skype for Business Server 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e a instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="04f20-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

