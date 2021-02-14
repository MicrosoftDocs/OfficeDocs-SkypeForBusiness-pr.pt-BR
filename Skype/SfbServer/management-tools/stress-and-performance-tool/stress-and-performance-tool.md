---
title: Ferramenta de Stress and Performance do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: A Ferramenta de Stress and Performance do Skype for Business Server 2015 é usada durante o planejamento de capacidade e ajuste de desempenho em ambientes de não produção ou teste.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814921"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="5c86d-103">Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c86d-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="5c86d-104">A Ferramenta de Stress and Performance do Skype for Business Server 2015 é usada durante o planejamento de capacidade e ajuste de desempenho em ambientes de não produção ou teste.</span><span class="sxs-lookup"><span data-stu-id="5c86d-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="5c86d-105">A Ferramenta de Stress and Performance do Skype for Business Server 2015 inclui ferramentas que simplificarão seu planejamento de capacidade para o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5c86d-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="5c86d-106">A Ferramenta de Stress and Performance do Skype for Business Server 2015 ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="5c86d-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="5c86d-107">Simplifique seu planejamento de hardware para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c86d-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="5c86d-108">Aumentar o conhecimento e as práticas recomendadas para ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="5c86d-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="5c86d-109">Medir o desempenho de suas implantações do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c86d-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="5c86d-110">Normalmente, você usaria essa ferramenta depois de usar a Ferramenta de Planejamento do [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinar a topologia com a Calculadora de Planejamento de Capacidade do Skype for Business Server [2015.](../../management-tools/capacity-planning-calculator.md)</span><span class="sxs-lookup"><span data-stu-id="5c86d-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="5c86d-111">Essa ferramenta não será atualizada para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5c86d-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="5c86d-112">Testes</span><span class="sxs-lookup"><span data-stu-id="5c86d-112">Tests</span></span>

<span data-ttu-id="5c86d-113">A Ferramenta de Stress and Performance pode simular esses tipos de carga de usuário:</span><span class="sxs-lookup"><span data-stu-id="5c86d-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5c86d-114">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="5c86d-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="5c86d-115">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="5c86d-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="5c86d-116">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="5c86d-116">Application sharing</span></span>  <br/> |<span data-ttu-id="5c86d-117">Simulação de VoIP (Voz sobre IP), incluindo simulação de PTSN (Rede Telefônica Pública Comucionária)</span><span class="sxs-lookup"><span data-stu-id="5c86d-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="5c86d-118">Web Access Client conferencing</span><span class="sxs-lookup"><span data-stu-id="5c86d-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="5c86d-119">Atendente automático da conferência</span><span class="sxs-lookup"><span data-stu-id="5c86d-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="5c86d-120">Grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="5c86d-120">Response Groups</span></span>  <br/> |<span data-ttu-id="5c86d-121">Expansão da lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="5c86d-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="5c86d-122">Download do livro de endereços e consulta do livro de endereços</span><span class="sxs-lookup"><span data-stu-id="5c86d-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="5c86d-123">Chamadas aprimoradas do 911 (E911) e perfil de local (plano de discagem)</span><span class="sxs-lookup"><span data-stu-id="5c86d-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="5c86d-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="5c86d-124">MultiView</span></span>  <br/> |<span data-ttu-id="5c86d-125">Colaboração de dados</span><span class="sxs-lookup"><span data-stu-id="5c86d-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="5c86d-126">Mobilidade</span><span class="sxs-lookup"><span data-stu-id="5c86d-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="5c86d-127">Aplicativos e arquivos incluídos na Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c86d-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="5c86d-128">Esses aplicativos fazem parte da Ferramenta de Stress and Performance do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="5c86d-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="5c86d-129">**Ferramenta**</span><span class="sxs-lookup"><span data-stu-id="5c86d-129">**Tool**</span></span>|<span data-ttu-id="5c86d-130">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c86d-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c86d-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="5c86d-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="5c86d-132">Essa ferramenta é usada para criar usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="5c86d-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="5c86d-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="5c86d-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="5c86d-134">Usado para configurar as características da carga do usuário que você está simulando.</span><span class="sxs-lookup"><span data-stu-id="5c86d-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="5c86d-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="5c86d-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="5c86d-136">A ferramenta que simula a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="5c86d-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="5c86d-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="5c86d-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="5c86d-138">Necessário para usar a Ferramenta de Log do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5c86d-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="5c86d-139">Exemplos de script de provisionamento</span><span class="sxs-lookup"><span data-stu-id="5c86d-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="5c86d-140">Usado para configurar a topologia para a execução de testes de carga, com base em cenários específicos.</span><span class="sxs-lookup"><span data-stu-id="5c86d-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="5c86d-141">Você provavelmente precisará modificá-los para torná-los relevantes para seu ambiente específico.</span><span class="sxs-lookup"><span data-stu-id="5c86d-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="5c86d-142">Tópicos nesta seção</span><span class="sxs-lookup"><span data-stu-id="5c86d-142">Topics in this section</span></span>

<span data-ttu-id="5c86d-143">Você deve revisar os seguintes artigos se precisar saber mais:</span><span class="sxs-lookup"><span data-stu-id="5c86d-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="5c86d-144">Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Busines</span><span class="sxs-lookup"><span data-stu-id="5c86d-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="5c86d-145">Cenários de desempenho da Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c86d-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="5c86d-146">Provisionando a topologia para executar a carga em cenários de Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="5c86d-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="5c86d-147">Configurando políticas para a Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c86d-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="5c86d-148">Usando a Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c86d-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="5c86d-149">Perguntas frequentes sobre a Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c86d-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

