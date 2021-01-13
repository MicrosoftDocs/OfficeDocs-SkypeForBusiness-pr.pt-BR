---
title: Cenários de desempenho da Ferramenta de Stress and Performance do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tarefas que você precisará realizar para configurar o Skype for Business Server 2015 para realizar testes de desempenho e carga, usando a Ferramenta de Stress and Performance.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814701"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="df59a-103">Cenários de desempenho da Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="df59a-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="df59a-104">Tarefas que você precisará realizar para configurar o Skype for Business Server 2015 para realizar testes de desempenho e carga, usando a Ferramenta de Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="df59a-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="df59a-105">Para executar a Ferramenta de Stress and Performance do Skype for Business Server 2015 (LyncPerfTool), a topologia do Skype for Business Server 2015 deve primeiro ser configurada para cenários relevantes para você.</span><span class="sxs-lookup"><span data-stu-id="df59a-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="df59a-106">Se o Skype for Business Server 2015 não estiver configurado ou estiver configurado incorretamente, sua simulação de carga provavelmente falhará.</span><span class="sxs-lookup"><span data-stu-id="df59a-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="df59a-107">Com a Ferramenta de Stress and Performance do Skype for Business Server 2015, fornecemos exemplos de scripts do Shell de Gerenciamento do Skype for Business Server e arquivos de recursos básicos como parte do download da [ferramenta.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="df59a-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="df59a-108">Eles podem ser usados como ponto de partida para configurar sua implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="df59a-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="df59a-109">Este artigo descreve os exemplos do Windows PowerShell fornecidos.</span><span class="sxs-lookup"><span data-stu-id="df59a-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df59a-110">Este tópico não ajudará você a descrever como configurar o Skype for Business Server 2015 em geral, temos outros tópicos de Planejamento e Implantação para isso.</span><span class="sxs-lookup"><span data-stu-id="df59a-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="df59a-111">Para obter detalhes sobre como trabalhar com o Windows PowerShell no Skype for Business Server 2015, consulte a documentação do Shell de Gerenciamento do Skype for Business Server em Inserir introdução AQUI.</span><span class="sxs-lookup"><span data-stu-id="df59a-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="df59a-112">Sobre a execução de scripts do shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="df59a-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="df59a-113">Fornecemos exemplos de scripts do PowerShell que você pode usar para se preparar para suas simulações de carga.</span><span class="sxs-lookup"><span data-stu-id="df59a-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="df59a-114">Como esses scripts se destinam à simulação de carga, você os verá como simples e permissivos.</span><span class="sxs-lookup"><span data-stu-id="df59a-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="df59a-115">Isso pode não ser apropriado para seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="df59a-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="df59a-116">Novamente, enfatizamos que esses scripts são exemplos, você precisará revisá-los e, em muitos casos, fazer alterações relevantes para seu ambiente antes de poder usá-los de forma prática.</span><span class="sxs-lookup"><span data-stu-id="df59a-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="df59a-117">No mínimo, esperamos que você precise modificar o script RSG (Grupo de Serviço de Resposta) com sua topologia em mente (para especificar os agentes atribuídos aos grupos de agentes).</span><span class="sxs-lookup"><span data-stu-id="df59a-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="df59a-118">Mas você não precisa executar isso, se não precisar.</span><span class="sxs-lookup"><span data-stu-id="df59a-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="df59a-119">Tome cuidado ao analisar e entender esses exemplos.</span><span class="sxs-lookup"><span data-stu-id="df59a-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="df59a-120">Os scripts substituirão quaisquer configurações existentes na topologia quando executados.</span><span class="sxs-lookup"><span data-stu-id="df59a-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="df59a-121">Nomes de versão do cliente da Ferramenta de Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="df59a-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="df59a-122">Talvez seja necessário configurar a política de Verificação de Versão do Cliente se tiver alterado anteriormente as configurações dos valores padrão.</span><span class="sxs-lookup"><span data-stu-id="df59a-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="df59a-123">Se você não tiver certeza sobre isso, verifique a documentação de Verificação [de Versão do Cliente.](https://msdn.microsoft.com/vsto/jj923060)</span><span class="sxs-lookup"><span data-stu-id="df59a-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="df59a-124">A Ferramenta de Stress and Performance usa as seguintes versões do Agente do Usuário por padrão ao se comunicar com o Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="df59a-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="df59a-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="df59a-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="df59a-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="df59a-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="df59a-127">Para o cliente de Mobilidade (UCWA) no LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="df59a-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="df59a-128">Ferramenta UCWA Perf/Web Conference</span><span class="sxs-lookup"><span data-stu-id="df59a-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="df59a-129">Ferramenta UCWA Perf/Mobile</span><span class="sxs-lookup"><span data-stu-id="df59a-129">UCWA Perf Tool/Mobile</span></span>
    

