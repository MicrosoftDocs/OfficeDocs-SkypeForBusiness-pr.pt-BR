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
ms.openlocfilehash: dd2edd2e6ecef26b22ba9bf5c093c631866110ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280650"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="7f93b-103">Verificar coexistência de pool piloto com pool herdado</span><span class="sxs-lookup"><span data-stu-id="7f93b-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="7f93b-104">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="7f93b-104">**In this article**</span></span>
  
[<span data-ttu-id="7f93b-105">Verifique se os serviços do Skype for Business Server 2019 começaram</span><span class="sxs-lookup"><span data-stu-id="7f93b-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="7f93b-106">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7f93b-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="7f93b-107">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="7f93b-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="7f93b-108">Depois de implantar o pool piloto, você precisa verificar a coexistência dos dois pools usando as ferramentas administrativas para exibir as informações de pool.</span><span class="sxs-lookup"><span data-stu-id="7f93b-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="7f93b-109">Para os pools do Skype for Business Server 2019 e pools herdados, você deve usar o painel de controle do Skype for Business Server 2019 e ferramentas do construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="7f93b-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="7f93b-110">Verifique se os serviços do Skype for Business Server 2019 começaram</span><span class="sxs-lookup"><span data-stu-id="7f93b-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="7f93b-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7f93b-111"></span></span>

1. <span data-ttu-id="7f93b-112">No servidor front-end do Skype for Business Server 2019, navegue até o applet administrador do Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="7f93b-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="7f93b-113">Verifique se os seguintes serviços estão em execução no servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="7f93b-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="7f93b-114">Agente de Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="7f93b-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="7f93b-115">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="7f93b-115">Application Sharing</span></span>
    - <span data-ttu-id="7f93b-116">Serviço de teste de áudio</span><span class="sxs-lookup"><span data-stu-id="7f93b-116">Audio Test Service</span></span>
    - <span data-ttu-id="7f93b-117">Conferência de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="7f93b-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="7f93b-118">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="7f93b-118">Call Park</span></span>
    - <span data-ttu-id="7f93b-119">Comunicado de conferência</span><span class="sxs-lookup"><span data-stu-id="7f93b-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="7f93b-120">Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="7f93b-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="7f93b-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="7f93b-121">Front-End</span></span>
    - <span data-ttu-id="7f93b-122">Conferência de mensagem instantânea</span><span class="sxs-lookup"><span data-stu-id="7f93b-122">IM Conferencing</span></span>
    - <span data-ttu-id="7f93b-123">Mediação</span><span class="sxs-lookup"><span data-stu-id="7f93b-123">Mediation</span></span>
    - <span data-ttu-id="7f93b-124">Agente duplicador de réplica</span><span class="sxs-lookup"><span data-stu-id="7f93b-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="7f93b-125">Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="7f93b-125">Response Group</span></span>
    - <span data-ttu-id="7f93b-126">Webconferência</span><span class="sxs-lookup"><span data-stu-id="7f93b-126">Web Conferencing</span></span>
    - <span data-ttu-id="7f93b-127">XMPP traduzir o gateway</span><span class="sxs-lookup"><span data-stu-id="7f93b-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="7f93b-128">Abrir o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7f93b-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="7f93b-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7f93b-129"></span></span>

<span data-ttu-id="7f93b-130">A partir do servidor front-end na implantação do Skype for Business Server 2019, abra o painel de controle do Skype for Business Server 2019 e selecione o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="7f93b-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="7f93b-131">Repita o procedimento para abrir o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f93b-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7f93b-132">No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7f93b-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="7f93b-133">Essa topologia agora inclui funções de servidor herdadas e do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f93b-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="7f93b-134">Não tente abrir a topologia no construtor de topologias herdadas</span><span class="sxs-lookup"><span data-stu-id="7f93b-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="7f93b-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7f93b-135"></span></span>

<span data-ttu-id="7f93b-136">Se você tentar abrir a topologia usando o construtor de topologias herdado, o erro será encontrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="7f93b-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="7f93b-137">A topologia só pode ser visualizada usando o construtor de topologias do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f93b-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="7f93b-138">O construtor de topologia do Skype for Business Server 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e para a instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="7f93b-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

