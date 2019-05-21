---
title: Cenários de desempenho da ferramenta de stress e desempenho do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer o teste de desempenho e carga, usando a ferramenta stress and performance.
ms.openlocfilehash: 2aedb43a6b7214aaf582e1dfd4754e626a602508
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299380"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="91a33-103">Cenários de desempenho da ferramenta de stress e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="91a33-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="91a33-104">Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer o teste de desempenho e carga, usando a ferramenta stress and performance.</span><span class="sxs-lookup"><span data-stu-id="91a33-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="91a33-105">Para executar a ferramenta de stress and performance do Skype for Business Server 2015 (LyncPerfTool), a topologia do Skype for Business Server 2015 deve primeiro ser configurada para cenários relevantes para você.</span><span class="sxs-lookup"><span data-stu-id="91a33-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="91a33-106">Se o Skype for Business Server 2015 não estiver configurado ou estiver configurado incorretamente, a simulação de carga provavelmente falhará.</span><span class="sxs-lookup"><span data-stu-id="91a33-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="91a33-107">Com a ferramenta de stress e desempenho do Skype for Business Server 2015, estamos fornecendo exemplos de scripts do Shell de gerenciamento do Skype for Business Server e arquivos de recursos básicos como parte do [download da ferramenta](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="91a33-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="91a33-108">Elas podem ser usadas como um ponto de partida para configurar a implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="91a33-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="91a33-109">Este artigo descreve os exemplos do Windows PowerShell fornecidos.</span><span class="sxs-lookup"><span data-stu-id="91a33-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91a33-110">Este tópico não ajudará você a descrever como configurar o Skype for Business Server 2015 em geral, temos outros tópicos de planejamento e implantação para isso.</span><span class="sxs-lookup"><span data-stu-id="91a33-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="91a33-111">Para obter detalhes sobre como trabalhar com o Windows PowerShell no Skype for Business Server 2015, consulte a documentação do Shell de gerenciamento do Skype for Business Server em inserir introdução aqui.</span><span class="sxs-lookup"><span data-stu-id="91a33-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="91a33-112">Sobre como executar scripts do Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a33-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="91a33-113">Estamos fornecendo exemplos de scripts do PowerShell que você pode usar para se preparar para suas simulações de carga.</span><span class="sxs-lookup"><span data-stu-id="91a33-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="91a33-114">Como esses scripts são destinados à simulação de carga, você os encontrará como simples e permissivos.</span><span class="sxs-lookup"><span data-stu-id="91a33-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="91a33-115">Isso pode não ser adequado para o seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="91a33-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="91a33-116">Reembolsamos que esses scripts são exemplos, você precisará examiná-los e, em muitos casos, fazer alterações pertinentes ao seu ambiente antes de poder usá-los de forma prática.</span><span class="sxs-lookup"><span data-stu-id="91a33-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="91a33-117">No mínimo, esperamos que você precise modificar o script de grupo de serviços de resposta (RSG) com sua topologia em mente (para especificar os agentes atribuídos aos grupos de agente).</span><span class="sxs-lookup"><span data-stu-id="91a33-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="91a33-118">Mas você não precisa executá-lo, se não precisar.</span><span class="sxs-lookup"><span data-stu-id="91a33-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="91a33-119">Tome cuidado ao revisar e compreender esses exemplos.</span><span class="sxs-lookup"><span data-stu-id="91a33-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="91a33-120">Os scripts substituirão as configurações existentes na topologia quando forem executados.</span><span class="sxs-lookup"><span data-stu-id="91a33-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="91a33-121">Nomes de versão de cliente de ferramenta de stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="91a33-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="91a33-122">Talvez seja necessário configurar a política de verificação de versão do cliente se você tiver alterado anteriormente as configurações dos valores padrão.</span><span class="sxs-lookup"><span data-stu-id="91a33-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="91a33-123">Se você não tiver certeza sobre isso, verifique a [documentação da verificação de versão do cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="91a33-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="91a33-124">A ferramenta stress and Performance usa as seguintes versões de agente de usuário por padrão ao se comunicar com o Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="91a33-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="91a33-125">LSPT/15.0.0.0 (ferramenta de stress e desempenho do Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="91a33-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="91a33-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="91a33-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="91a33-127">Para o cliente Mobility (UCWA) no LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="91a33-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="91a33-128">Ferramenta perf UCWA/Web Conference</span><span class="sxs-lookup"><span data-stu-id="91a33-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="91a33-129">Ferramenta perf UCWA/móvel</span><span class="sxs-lookup"><span data-stu-id="91a33-129">UCWA Perf Tool/Mobile</span></span>
    

