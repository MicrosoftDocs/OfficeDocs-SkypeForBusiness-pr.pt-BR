---
title: Estacionamento de Chamada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Quando uma chamada está estacionada, ela é transferida para um número temporário em que a chamada é mantida até alguém recuperá-la ou expirar. Você precisa configurar uma tabela com os intervalos de números de extensão que você está reservando para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões sem usuário ou telefone atribuídas a ela). Cada pool que executa o aplicativo de estacionamento de chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.
ms.openlocfilehash: 7f4a660c3fdd1dbba5080b93bec0aac116d453ea
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797808"
---
# <a name="call-park"></a><span data-ttu-id="9d774-106">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="9d774-106">Call Park</span></span>

<span data-ttu-id="9d774-107">Quando uma chamada está estacionada, ela é transferida para um número temporário em que a chamada é mantida até alguém recuperá-la ou expirar. Você precisa configurar uma tabela com os intervalos de números de extensão que você está reservando para chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="9d774-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="9d774-108">Essas extensões precisam ser extensões virtuais (ou seja, extensões sem usuário ou telefone atribuídas a ela).</span><span class="sxs-lookup"><span data-stu-id="9d774-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="9d774-109">Cada pool que executa o aplicativo de estacionamento de chamada pode ter um ou mais intervalos de extensões.</span><span class="sxs-lookup"><span data-stu-id="9d774-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="9d774-110">Esses intervalos precisam ser globalmente exclusivos em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="9d774-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="9d774-111">A página **estacionamento de chamada** exibe uma lista de todos os intervalos numéricos do parque de chamadas definidos para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="9d774-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9d774-112">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="9d774-112">Tasks you can perform</span></span>

<span data-ttu-id="9d774-113">É possível executar as seguintes tarefas na página **Estacionamento de Chamada**:</span><span class="sxs-lookup"><span data-stu-id="9d774-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="9d774-114">Criar um novo intervalo de números</span><span class="sxs-lookup"><span data-stu-id="9d774-114">Create a new number range</span></span>

- <span data-ttu-id="9d774-115">Alterar um intervalo de números existente</span><span class="sxs-lookup"><span data-stu-id="9d774-115">Change an existing number range</span></span>

- <span data-ttu-id="9d774-116">Excluir um intervalo de números</span><span class="sxs-lookup"><span data-stu-id="9d774-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9d774-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="9d774-117">UI Reference</span></span>

<span data-ttu-id="9d774-118">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="9d774-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="9d774-119">**Novo** Inicia um novo intervalo de números do parque da chamada.</span><span class="sxs-lookup"><span data-stu-id="9d774-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="9d774-120">**Editar** Abre o intervalo de números selecionado para edição, seleciona todos os intervalos de números na lista ou exclui o intervalo de números selecionado.</span><span class="sxs-lookup"><span data-stu-id="9d774-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="9d774-121">**Atualização** Atualiza a lista de intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="9d774-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="9d774-122">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="9d774-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="9d774-123">**Nome** O nome exclusivo que identifica o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="9d774-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="9d774-124">**Iniciar intervalo** O número inicial do intervalo.</span><span class="sxs-lookup"><span data-stu-id="9d774-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="9d774-125">**Intervalo final** O número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="9d774-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="9d774-126">**Destino** O nome de domínio totalmente qualificado (FQDN) ou a ID de serviço do serviço de aplicativo que hospeda o aplicativo parque de chamadas para o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="9d774-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="9d774-127">Para obter detalhes sobre os recursos e recursos do parque da chamada, consulte [planejar o estacionamento de chamadas no Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="9d774-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="9d774-128">Para obter detalhes sobre como trabalhar com intervalos numéricos do parque da chamada, consulte [Configurar extensões de número de telefone para chamadas com estacionamento](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="9d774-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


