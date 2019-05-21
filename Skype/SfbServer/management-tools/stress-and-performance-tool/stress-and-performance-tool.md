---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: A ferramenta de stress e desempenho do Skype for Business Server 2015 é usada durante o planejamento da capacidade e o ajuste de desempenho em ambientes que não sejam de produção ou de teste.
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299513"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="da910-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="da910-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="da910-104">A ferramenta de stress e desempenho do Skype for Business Server 2015 é usada durante o planejamento da capacidade e o ajuste de desempenho em ambientes que não sejam de produção ou de teste.</span><span class="sxs-lookup"><span data-stu-id="da910-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="da910-105">A ferramenta de stress e desempenho do Skype for Business Server 2015 inclui ferramentas que simplificarão o planejamento de capacidade para o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="da910-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="da910-106">A ferramenta de stress e desempenho do Skype for Business Server 2015 ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="da910-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="da910-107">Simplifique seu planejamento de hardware para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="da910-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="da910-108">Fornecer conhecimento e práticas recomendadas para ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="da910-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="da910-109">Medir o desempenho de suas implantações do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="da910-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="da910-110">Normalmente, você usaria essa ferramenta depois de usar a [ferramenta de planejamento do Skype for Business server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinar a topologia com a [calculadora do planejamento de capacidade do 2015 do Skype for Business Server](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="da910-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="da910-111">Esta ferramenta não será atualizada para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="da910-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="da910-112">Testes</span><span class="sxs-lookup"><span data-stu-id="da910-112">Tests</span></span>

<span data-ttu-id="da910-113">A ferramenta stress and Performance pode simular esses tipos de carga de usuário:</span><span class="sxs-lookup"><span data-stu-id="da910-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="da910-114">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="da910-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="da910-115">Conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="da910-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="da910-116">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="da910-116">Application sharing</span></span>  <br/> |<span data-ttu-id="da910-117">Voz sobre IP (VoIP), incluindo simulação de rede telefônica pública comutada (PTSN)</span><span class="sxs-lookup"><span data-stu-id="da910-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="da910-118">Conferência de cliente de acesso Web</span><span class="sxs-lookup"><span data-stu-id="da910-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="da910-119">Atendedor automático da conferência</span><span class="sxs-lookup"><span data-stu-id="da910-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="da910-120">Grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="da910-120">Response Groups</span></span>  <br/> |<span data-ttu-id="da910-121">Expansão da lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="da910-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="da910-122">Consulta de download e catálogo de endereços do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="da910-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="da910-123">Chamadas avançadas de 911 (E911) e perfil de local (plano de discagem)</span><span class="sxs-lookup"><span data-stu-id="da910-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="da910-124">Múltipla</span><span class="sxs-lookup"><span data-stu-id="da910-124">MultiView</span></span>  <br/> |<span data-ttu-id="da910-125">Colaboração de dados</span><span class="sxs-lookup"><span data-stu-id="da910-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="da910-126">Mobilidade</span><span class="sxs-lookup"><span data-stu-id="da910-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="da910-127">Aplicativos e arquivos incluídos na ferramenta de stress e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="da910-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="da910-128">Esses aplicativos fazem parte da ferramenta de stress e desempenho do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="da910-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="da910-129">**Ferramentas**</span><span class="sxs-lookup"><span data-stu-id="da910-129">**Tool**</span></span>|<span data-ttu-id="da910-130">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="da910-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da910-131">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="da910-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="da910-132">Esta ferramenta é usada para criar usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="da910-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="da910-133">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="da910-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="da910-134">Usado para configurar as características da carga de usuário que você está simulando.</span><span class="sxs-lookup"><span data-stu-id="da910-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="da910-135">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="da910-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="da910-136">A ferramenta que simula a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="da910-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="da910-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="da910-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="da910-138">Obrigatório para usar a ferramenta de log do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="da910-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="da910-139">Exemplos de script de provisionamento</span><span class="sxs-lookup"><span data-stu-id="da910-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="da910-140">Usado para configurar a topologia para executar testes de carga com base em cenários específicos.</span><span class="sxs-lookup"><span data-stu-id="da910-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="da910-141">Você provavelmente precisará modificá-los para torná-los relevantes para o seu ambiente específico.</span><span class="sxs-lookup"><span data-stu-id="da910-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="da910-142">Tópicos desta seção</span><span class="sxs-lookup"><span data-stu-id="da910-142">Topics in this section</span></span>

<span data-ttu-id="da910-143">Você deve revisar os artigos a seguir se precisar saber mais:</span><span class="sxs-lookup"><span data-stu-id="da910-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="da910-144">Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="da910-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="da910-145">Cenários de desempenho da ferramenta de stress e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="da910-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="da910-146">Provisionando a topologia para executar carga em cenários de carga e desempenho</span><span class="sxs-lookup"><span data-stu-id="da910-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="da910-147">Configurando políticas para a ferramenta de stress e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="da910-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="da910-148">Usando a ferramenta de stress e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="da910-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="da910-149">Perguntas frequentes sobre a ferramenta de stress e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="da910-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

