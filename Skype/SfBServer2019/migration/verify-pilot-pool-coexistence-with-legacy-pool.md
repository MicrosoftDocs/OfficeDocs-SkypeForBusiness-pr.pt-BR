---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: 386ea4a7857fcdef7d45e5d8029ff4bf31293819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812669"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="8b6c1-103">Verificar coexistência de pool piloto com pool herdado</span><span class="sxs-lookup"><span data-stu-id="8b6c1-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="8b6c1-104">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="8b6c1-104">**In this article**</span></span>
  
[<span data-ttu-id="8b6c1-105">Verifique se os serviços do Skype for Business Server 2019 começaram</span><span class="sxs-lookup"><span data-stu-id="8b6c1-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="8b6c1-106">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8b6c1-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="8b6c1-107">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="8b6c1-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="8b6c1-108">Depois de implantar o pool piloto, você precisa verificar a coexistência dos dois pools usando as ferramentas administrativas para exibir as informações de pool.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="8b6c1-109">Para os pools do Skype for Business Server 2019 e pools herdados, você deve usar o painel de controle do Skype for Business Server 2019 e ferramentas do construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="8b6c1-110">Verifique se os serviços do Skype for Business Server 2019 começaram</span><span class="sxs-lookup"><span data-stu-id="8b6c1-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="8b6c1-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="8b6c1-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="8b6c1-112">No servidor front-end do Skype for Business Server 2019, navegue até o applet administrador do Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="8b6c1-113">Verifique se os seguintes serviços estão em execução no servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="8b6c1-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="8b6c1-114">Agente de Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="8b6c1-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="8b6c1-115">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="8b6c1-115">Application Sharing</span></span>
    - <span data-ttu-id="8b6c1-116">Serviço de teste de áudio</span><span class="sxs-lookup"><span data-stu-id="8b6c1-116">Audio Test Service</span></span>
    - <span data-ttu-id="8b6c1-117">Conferência de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="8b6c1-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="8b6c1-118">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="8b6c1-118">Call Park</span></span>
    - <span data-ttu-id="8b6c1-119">Comunicado de conferência</span><span class="sxs-lookup"><span data-stu-id="8b6c1-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="8b6c1-120">Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="8b6c1-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="8b6c1-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="8b6c1-121">Front-End</span></span>
    - <span data-ttu-id="8b6c1-122">Conferência de mensagem instantânea</span><span class="sxs-lookup"><span data-stu-id="8b6c1-122">IM Conferencing</span></span>
    - <span data-ttu-id="8b6c1-123">Mediação</span><span class="sxs-lookup"><span data-stu-id="8b6c1-123">Mediation</span></span>
    - <span data-ttu-id="8b6c1-124">Agente duplicador de réplica</span><span class="sxs-lookup"><span data-stu-id="8b6c1-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="8b6c1-125">Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="8b6c1-125">Response Group</span></span>
    - <span data-ttu-id="8b6c1-126">Webconferência</span><span class="sxs-lookup"><span data-stu-id="8b6c1-126">Web Conferencing</span></span>
    - <span data-ttu-id="8b6c1-127">XMPP traduzir o gateway</span><span class="sxs-lookup"><span data-stu-id="8b6c1-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="8b6c1-128">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8b6c1-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="8b6c1-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="8b6c1-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="8b6c1-130">A partir do servidor front-end na implantação do Skype for Business Server 2019, abra o painel de controle do Skype for Business Server 2019 e selecione o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="8b6c1-131">Repita o procedimento para abrir o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8b6c1-132">No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="8b6c1-133">Essa topologia agora inclui funções de servidor herdadas e do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="8b6c1-134">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="8b6c1-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="8b6c1-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="8b6c1-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="8b6c1-136">A topologia só pode ser visualizada usando o construtor de topologias do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="8b6c1-137">O construtor de topologia do Skype for Business Server 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e para a instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="8b6c1-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

