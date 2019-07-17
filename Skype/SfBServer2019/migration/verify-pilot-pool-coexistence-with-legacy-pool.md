---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2019
ms.locfileid: "35758901"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="6c327-103">Verificar coexistência de pool piloto com pool herdado</span><span class="sxs-lookup"><span data-stu-id="6c327-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="6c327-104">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="6c327-104">**In this article**</span></span>
  
[<span data-ttu-id="6c327-105">Verifique se os serviços do Skype for Business Server 2019 começaram</span><span class="sxs-lookup"><span data-stu-id="6c327-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="6c327-106">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6c327-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="6c327-107">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="6c327-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="6c327-108">Depois de implantar o pool piloto, você precisa verificar a coexistência dos dois pools usando as ferramentas administrativas para exibir as informações de pool.</span><span class="sxs-lookup"><span data-stu-id="6c327-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="6c327-109">Para os pools do Skype for Business Server 2019 e pools herdados, você deve usar o painel de controle do Skype for Business Server 2019 e ferramentas do construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="6c327-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="6c327-110">Verifique se os serviços do Skype for Business Server 2019 começaram</span><span class="sxs-lookup"><span data-stu-id="6c327-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="6c327-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="6c327-111"></span></span>

1. <span data-ttu-id="6c327-112">No servidor front-end do Skype for Business Server 2019, navegue até o applet administrador do Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="6c327-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="6c327-113">Verifique se os seguintes serviços estão em execução no servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="6c327-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="6c327-114">Agente de Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="6c327-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="6c327-115">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="6c327-115">Application Sharing</span></span>
    - <span data-ttu-id="6c327-116">Serviço de teste de áudio</span><span class="sxs-lookup"><span data-stu-id="6c327-116">Audio Test Service</span></span>
    - <span data-ttu-id="6c327-117">Conferência de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="6c327-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="6c327-118">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="6c327-118">Call Park</span></span>
    - <span data-ttu-id="6c327-119">Comunicado de conferência</span><span class="sxs-lookup"><span data-stu-id="6c327-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="6c327-120">Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="6c327-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="6c327-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="6c327-121">Front-End</span></span>
    - <span data-ttu-id="6c327-122">Conferência de mensagem instantânea</span><span class="sxs-lookup"><span data-stu-id="6c327-122">IM Conferencing</span></span>
    - <span data-ttu-id="6c327-123">Mediação</span><span class="sxs-lookup"><span data-stu-id="6c327-123">Mediation</span></span>
    - <span data-ttu-id="6c327-124">Agente duplicador de réplica</span><span class="sxs-lookup"><span data-stu-id="6c327-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="6c327-125">Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="6c327-125">Response Group</span></span>
    - <span data-ttu-id="6c327-126">Webconferência</span><span class="sxs-lookup"><span data-stu-id="6c327-126">Web Conferencing</span></span>
    - <span data-ttu-id="6c327-127">XMPP traduzir o gateway</span><span class="sxs-lookup"><span data-stu-id="6c327-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="6c327-128">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6c327-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="6c327-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="6c327-129"></span></span>

<span data-ttu-id="6c327-130">A partir do servidor front-end na implantação do Skype for Business Server 2019, abra o painel de controle do Skype for Business Server 2019 e selecione o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="6c327-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="6c327-131">Repita o procedimento para abrir o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6c327-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c327-132">No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c327-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="6c327-133">Essa topologia agora inclui funções de servidor herdadas e do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6c327-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="6c327-134">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="6c327-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="6c327-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="6c327-135"></span></span>

<span data-ttu-id="6c327-136">A topologia só pode ser visualizada usando o construtor de topologias do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6c327-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="6c327-137">O construtor de topologia do Skype for Business Server 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e para a instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="6c327-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

