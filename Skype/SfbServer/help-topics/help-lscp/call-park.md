---
title: Estacionamento de Chamada
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Quando uma chamada estiver estacionada, ele será transferido para um número temporário onde a chamada é mantida até que alguém as recupere ou ele expire. Você precisa configurar uma tabela com os intervalos de números de ramal que você é reservar para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões sem usuário ou telefone atribuídas a ela). Cada pool que executa o aplicativo de estacionamento de chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.
ms.openlocfilehash: e78cdaa143cd0287bed49abe3fc8e06022b8d6f6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975617"
---
# <a name="call-park"></a><span data-ttu-id="fb217-106">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="fb217-106">Call Park</span></span>
 
<span data-ttu-id="fb217-107">Quando uma chamada estiver estacionada, ele será transferido para um número temporário onde a chamada é mantida até que alguém as recupere ou ele expire. Você precisa configurar uma tabela com os intervalos de números de ramal que você é reservar para chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="fb217-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="fb217-108">Essas extensões precisam ser extensões virtuais (ou seja, extensões sem usuário ou telefone atribuídas a ela).</span><span class="sxs-lookup"><span data-stu-id="fb217-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="fb217-109">Cada pool que executa o aplicativo de estacionamento de chamada pode ter um ou mais intervalos de extensões.</span><span class="sxs-lookup"><span data-stu-id="fb217-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="fb217-110">Esses intervalos precisam ser globalmente exclusivos em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="fb217-110">These ranges must be globally unique across your deployment.</span></span>
  
<span data-ttu-id="fb217-111">Página **Estacionamento** de chamada exibe uma lista de todos os intervalos números estacionamento de chamada definidas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fb217-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="fb217-112">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="fb217-112">Tasks you can perform</span></span>

<span data-ttu-id="fb217-113">É possível executar as seguintes tarefas na página **Estacionamento de Chamada**:</span><span class="sxs-lookup"><span data-stu-id="fb217-113">You can perform the following tasks from the **Call Park** page:</span></span>
  
- <span data-ttu-id="fb217-114">Criar um novo intervalo de números</span><span class="sxs-lookup"><span data-stu-id="fb217-114">Create a new number range</span></span>
    
- <span data-ttu-id="fb217-115">Alterar um intervalo de números existente</span><span class="sxs-lookup"><span data-stu-id="fb217-115">Change an existing number range</span></span>
    
- <span data-ttu-id="fb217-116">Excluir um intervalo de números</span><span class="sxs-lookup"><span data-stu-id="fb217-116">Delete a number range</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="fb217-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="fb217-117">UI Reference</span></span>

<span data-ttu-id="fb217-118">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="fb217-118">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="fb217-119">**Novo** Inicia um novo intervalo de números do estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fb217-119">**New** Starts a new Call Park number range.</span></span>
    
- <span data-ttu-id="fb217-120">**Editar** Abre o intervalo de números selecionado para edição, seleciona todos os intervalos de números na lista ou exclui o intervalo de números selecionado.</span><span class="sxs-lookup"><span data-stu-id="fb217-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>
    
- <span data-ttu-id="fb217-121">**Atualizar** Atualiza a lista de intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="fb217-121">**Refresh** Refreshes the list of number ranges.</span></span>
    
<span data-ttu-id="fb217-122">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="fb217-122">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="fb217-123">**Nome** O nome exclusivo que identifica o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="fb217-123">**Name** The unique name that identifies the number range.</span></span>
    
- <span data-ttu-id="fb217-124">**Intervalo inicial** O número inicial do intervalo.</span><span class="sxs-lookup"><span data-stu-id="fb217-124">**Start range** The beginning number of the range.</span></span>
    
- <span data-ttu-id="fb217-125">**Intervalo final** O número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="fb217-125">**End range** The ending number of the range.</span></span>
    
- <span data-ttu-id="fb217-126">**Destino** Domínio totalmente qualificado (FQDN) nome ou ID de serviço do serviço aplicativo que hospeda o aplicativo de estacionamento de chamada para o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="fb217-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>
    
<span data-ttu-id="fb217-127">Para obter detalhes sobre os recursos de estacionamento de chamada e capacidades, consulte [Planejar estacionamento de chamada no Skype para negócios 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="fb217-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="fb217-128">Para obter detalhes sobre como trabalhar com intervalos de números do estacionamento de chamada, consulte [Configurar extensões de número de telefone para o estacionamento de chamadas](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb217-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

