---
title: Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: O Skype para ferramenta de desempenho e estresse do Business Server 2015 é usado durante o planejamento de capacidade e ajuste em ambientes de não-produção ou de teste de desempenho.
ms.openlocfilehash: 9ccd4b851ad64f829a15bd6138764995f789dbf6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984460"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="0723c-103">Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="0723c-104">O Skype para ferramenta de desempenho e estresse do Business Server 2015 é usado durante o planejamento de capacidade e ajuste em ambientes de não-produção ou de teste de desempenho.</span><span class="sxs-lookup"><span data-stu-id="0723c-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="0723c-105">O Skype para ferramenta de desempenho e estresse do Business Server 2015 inclui ferramentas que simplificarão seu planejamento de capacidade do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0723c-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="0723c-106">O Skype para ferramenta de desempenho e estresse do Business Server 2015 ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="0723c-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="0723c-107">Simplificar seu hardware planejando Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0723c-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="0723c-108">Dar conhecimento é aumentada e práticas recomendadas para ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="0723c-109">Medir o desempenho do seu Skype para implantações de servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="0723c-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="0723c-110">Normalmente você usaria esta ferramenta depois de usar o [Skype para ferramenta de planejamento do Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinando a topologia com o [Skype para Calculadora de planejamento de capacidade do Business Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="0723c-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="0723c-111">Essa ferramenta não será atualizada para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0723c-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="0723c-112">Testes</span><span class="sxs-lookup"><span data-stu-id="0723c-112">Tests</span></span>

<span data-ttu-id="0723c-113">A ferramenta de Stress e desempenho podem simular esses tipos de carga de usuário:</span><span class="sxs-lookup"><span data-stu-id="0723c-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0723c-114">Instant Messaging (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="0723c-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="0723c-115">Serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="0723c-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="0723c-116">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0723c-116">Application sharing</span></span>  <br/> |<span data-ttu-id="0723c-117">Simulação (PTSN) de voz sobre IP (VoIP), incluindo a rede telefônica pública comutada</span><span class="sxs-lookup"><span data-stu-id="0723c-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="0723c-118">Webconferência de acesso para cliente</span><span class="sxs-lookup"><span data-stu-id="0723c-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="0723c-119">Atendedor automático de conferência</span><span class="sxs-lookup"><span data-stu-id="0723c-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="0723c-120">Grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="0723c-120">Response Groups</span></span>  <br/> |<span data-ttu-id="0723c-121">Expansão de lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="0723c-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="0723c-122">Download do catálogo de endereços e consulta de catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="0723c-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="0723c-123">Enhanced nas 911 chamadas (E911) e o perfil de local (plano de discagem)</span><span class="sxs-lookup"><span data-stu-id="0723c-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="0723c-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="0723c-124">MultiView</span></span>  <br/> |<span data-ttu-id="0723c-125">Colaboração de dados</span><span class="sxs-lookup"><span data-stu-id="0723c-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="0723c-126">Mobilidade</span><span class="sxs-lookup"><span data-stu-id="0723c-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="0723c-127">Aplicativos e arquivos incluídos com o Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="0723c-128">Esses aplicativos são parte do Skype para ferramenta de desempenho e estresse do Business Server:</span><span class="sxs-lookup"><span data-stu-id="0723c-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="0723c-129">**Ferramenta**</span><span class="sxs-lookup"><span data-stu-id="0723c-129">**Tool**</span></span>|<span data-ttu-id="0723c-130">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0723c-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0723c-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="0723c-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="0723c-132">Essa ferramenta é usada para criar usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="0723c-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="0723c-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="0723c-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="0723c-134">Usado para configurar as características da carga de usuário que você está simulando.</span><span class="sxs-lookup"><span data-stu-id="0723c-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="0723c-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="0723c-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="0723c-136">A ferramenta que simula a carga de usuários.</span><span class="sxs-lookup"><span data-stu-id="0723c-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="0723c-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="0723c-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="0723c-138">Necessário para usar o Skype para ferramenta de log do Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0723c-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="0723c-139">Exemplos de scripts de provisionamento</span><span class="sxs-lookup"><span data-stu-id="0723c-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="0723c-140">Usado para configurar a topologia para executar testes de carga, com base em cenários específicos.</span><span class="sxs-lookup"><span data-stu-id="0723c-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="0723c-141">Você provavelmente precisará modificá-los para que sejam relevantes para seu ambiente específico.</span><span class="sxs-lookup"><span data-stu-id="0723c-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="0723c-142">Tópicos desta seção</span><span class="sxs-lookup"><span data-stu-id="0723c-142">Topics in this section</span></span>

<span data-ttu-id="0723c-143">Se você precisa saber mais, você deve examinar os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0723c-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="0723c-144">Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0723c-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="0723c-145">Cenários de desempenho para o Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="0723c-146">Provisionamento a topologia para executar a carga em cenários de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="0723c-147">Configurando políticas para o Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="0723c-148">Usando o Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="0723c-149">Perguntas frequentes para o Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="0723c-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

