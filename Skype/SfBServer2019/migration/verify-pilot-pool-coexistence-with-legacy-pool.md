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
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="e8899-103">Verificar coexistência de pool piloto com pool herdado</span><span class="sxs-lookup"><span data-stu-id="e8899-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="e8899-104">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="e8899-104">**In this article**</span></span>
  
[<span data-ttu-id="e8899-105">Verificar se os serviços do Skype for Business Server 2019 foram iniciados</span><span class="sxs-lookup"><span data-stu-id="e8899-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="e8899-106">Abrir o Painel de Controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e8899-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="e8899-107">Não tente abrir a topologia no Construtor de Topologias herdada</span><span class="sxs-lookup"><span data-stu-id="e8899-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="e8899-108">Depois de implantar o pool piloto, você deve verificar a coexistência de dois pools usando ferramentas administrativas para exibir as informações dos pools.</span><span class="sxs-lookup"><span data-stu-id="e8899-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="e8899-109">Para os pools e pools herdado do Skype for Business Server 2019, você deve usar o Painel de Controle do Skype for Business Server 2019 e as ferramentas do Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="e8899-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="e8899-110">Verificar se os serviços do Skype for Business Server 2019 foram iniciados</span><span class="sxs-lookup"><span data-stu-id="e8899-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="e8899-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e8899-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="e8899-112">No Servidor front-end do Skype for Business Server 2019, navegue até o applet Ferramentas Administrativas\Serviços.</span><span class="sxs-lookup"><span data-stu-id="e8899-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="e8899-113">Verifique se os serviços a seguir estão sendo executados no servidor Front End:</span><span class="sxs-lookup"><span data-stu-id="e8899-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="e8899-114">Agente de Serviço de Registro em Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="e8899-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="e8899-115">Compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="e8899-115">Application Sharing</span></span>
    - <span data-ttu-id="e8899-116">Serviço de Teste de Áudio</span><span class="sxs-lookup"><span data-stu-id="e8899-116">Audio Test Service</span></span>
    - <span data-ttu-id="e8899-117">Audioconferências/Videoconferências</span><span class="sxs-lookup"><span data-stu-id="e8899-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="e8899-118">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="e8899-118">Call Park</span></span>
    - <span data-ttu-id="e8899-119">Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="e8899-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="e8899-120">Atendente de Conferência</span><span class="sxs-lookup"><span data-stu-id="e8899-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="e8899-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="e8899-121">Front-End</span></span>
    - <span data-ttu-id="e8899-122">Conferência de IM</span><span class="sxs-lookup"><span data-stu-id="e8899-122">IM Conferencing</span></span>
    - <span data-ttu-id="e8899-123">Mediação</span><span class="sxs-lookup"><span data-stu-id="e8899-123">Mediation</span></span>
    - <span data-ttu-id="e8899-124">Agente Replicador de Réplica</span><span class="sxs-lookup"><span data-stu-id="e8899-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="e8899-125">Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="e8899-125">Response Group</span></span>
    - <span data-ttu-id="e8899-126">Conferência pela Web</span><span class="sxs-lookup"><span data-stu-id="e8899-126">Web Conferencing</span></span>
    - <span data-ttu-id="e8899-127">Gateway de tradução XMPP</span><span class="sxs-lookup"><span data-stu-id="e8899-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="e8899-128">Abrir o Painel de Controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e8899-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="e8899-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e8899-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="e8899-130">No Servidor front-end em sua implantação do Skype for Business Server 2019, abra o Painel de Controle do Skype for Business Server 2019 e selecione o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="e8899-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="e8899-131">Repita o procedimento para abrir o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e8899-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8899-132">No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8899-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="e8899-133">Essa topologia agora inclui funções de servidor herdada e do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e8899-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="e8899-134">Não tente abrir a topologia no Construtor de Topologias herdada</span><span class="sxs-lookup"><span data-stu-id="e8899-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="e8899-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e8899-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="e8899-136">A topologia só pode ser visualizada usando o Construtor de Topologias do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e8899-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="e8899-137">O Construtor de Topologias do Skype for Business Server 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e a instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="e8899-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

