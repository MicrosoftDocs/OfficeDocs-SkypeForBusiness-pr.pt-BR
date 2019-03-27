---
title: Cenários de desempenho para o Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tarefas que você precisará fazer para configurar Skype para Business 2015 de servidor fazer o desempenho e teste de carga, usando a ferramenta de Stress e desempenho.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874588"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="3fda9-103">Cenários de desempenho para o Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="3fda9-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="3fda9-104">Tarefas que você precisará fazer para configurar Skype para Business 2015 de servidor fazer o desempenho e teste de carga, usando a ferramenta de Stress e desempenho.</span><span class="sxs-lookup"><span data-stu-id="3fda9-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="3fda9-105">Para executar o Skype para Business Server 2015 ferramenta de Stress e desempenho (LyncPerfTool), o Skype para Business Server 2015 topologia deve ser configurada para cenários relevantes para você.</span><span class="sxs-lookup"><span data-stu-id="3fda9-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="3fda9-106">Se Skype para Business Server 2015 não estiver configurado ou está configurada incorretamente, sua simulação de carga é bem provável falha.</span><span class="sxs-lookup"><span data-stu-id="3fda9-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="3fda9-107">Com o Skype para ferramenta de desempenho e estresse do Business Server 2015, estamos fornecendo exemplo Skype para obter scripts de Shell de gerenciamento do servidor de negócios e arquivos de recursos básicos como parte do de [download da ferramenta](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="3fda9-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="3fda9-108">Essas podem ser usadas como um ponto de partida para configurar sua Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3fda9-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="3fda9-109">Este artigo descreve os exemplos do Windows PowerShell fornecidos.</span><span class="sxs-lookup"><span data-stu-id="3fda9-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3fda9-110">Este tópico não ajudá-lo a descrevem como configurar o Skype para Business Server 2015 geralmente, temos outros tópicos de planejamento e implantação para que.</span><span class="sxs-lookup"><span data-stu-id="3fda9-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="3fda9-111">Para obter detalhes sobre como trabalhar com o Windows PowerShell no Skype para Business Server 2015, consulte o Skype para documentação do Shell de gerenciamento do servidor de negócios em Inserir introdução aqui.</span><span class="sxs-lookup"><span data-stu-id="3fda9-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="3fda9-112">Sobre a execução Skype para gerenciamento de servidor de negócios scripts do shell</span><span class="sxs-lookup"><span data-stu-id="3fda9-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="3fda9-113">Estamos fornecendo scripts do PowerShell de amostra que você pode usar para preparar seus simulações de carga.</span><span class="sxs-lookup"><span data-stu-id="3fda9-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="3fda9-114">Porque esses scripts são destinados simulação de carga, você encontrará eles sejam simples e permissivo.</span><span class="sxs-lookup"><span data-stu-id="3fda9-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="3fda9-115">Que pode não ser apropriada para seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="3fda9-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="3fda9-116">Novamente, podemos sobrecarregar que esses scripts são exemplos, você precisará revisá-las e em muitos casos fazer alterações relevantes ao seu ambiente antes de poder fazer uso prático deles.</span><span class="sxs-lookup"><span data-stu-id="3fda9-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="3fda9-117">No mínimo, esperávamos que seria necessário modificar o script de resposta serviço RSG (grupo) com sua topologia em mente (para especificar os operadores atribuídos a grupos de operadores).</span><span class="sxs-lookup"><span data-stu-id="3fda9-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="3fda9-118">Mas você não precisa executar que, se você não precisa.</span><span class="sxs-lookup"><span data-stu-id="3fda9-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3fda9-119">Por favor, tome cuidado na análise e Noções básicas sobre esses exemplos.</span><span class="sxs-lookup"><span data-stu-id="3fda9-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="3fda9-120">Scripts substituirá quaisquer definições existentes na topologia quando executado.</span><span class="sxs-lookup"><span data-stu-id="3fda9-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="3fda9-121">Ferramenta de stress e desempenho nomes de versão de cliente</span><span class="sxs-lookup"><span data-stu-id="3fda9-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="3fda9-122">Você pode precisar configurar a política de verificação de versão do cliente se você alterou anteriormente as configurações dos valores padrão.</span><span class="sxs-lookup"><span data-stu-id="3fda9-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="3fda9-123">Se não tiver certeza sobre isso, consulte a [documentação verificar versão do cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="3fda9-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="3fda9-124">A ferramenta de Stress e desempenho usa as seguintes versões do agente do usuário por padrão durante a comunicação com Skype para Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="3fda9-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="3fda9-125">LSPT/15.0.0.0 (Skype para Business Server 2015 ferramenta de Stress e desempenho)</span><span class="sxs-lookup"><span data-stu-id="3fda9-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="3fda9-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="3fda9-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="3fda9-127">Para o cliente de mobilidade (UCWA) no LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="3fda9-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="3fda9-128">UCWA Perf ferramenta/Webconferência</span><span class="sxs-lookup"><span data-stu-id="3fda9-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="3fda9-129">Ferramenta de Perf UCWA/Mobile</span><span class="sxs-lookup"><span data-stu-id="3fda9-129">UCWA Perf Tool/Mobile</span></span>
    

