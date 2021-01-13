---
title: Estacionamento de Chamada
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Quando uma chamada é estacionada, ela é transferida para um número temporário no qual a chamada é mantida até que alguém a recupere ou o tempo se esvae. Você precisa configurar uma tabela com os intervalos de ramais que você está reservando para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões com nenhum usuário ou telefone atribuído a eles). Cada pool que executa o aplicativo Estacionamento de Chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.
ms.openlocfilehash: 679e13cdeb6ef6cf614f5703f5711e86fa1c8c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812161"
---
# <a name="call-park"></a><span data-ttu-id="c5acf-106">Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="c5acf-106">Call Park</span></span>

<span data-ttu-id="c5acf-107">Quando uma chamada é estacionada, ela é transferida para um número temporário no qual a chamada é mantida até que alguém a recupere ou o tempo se esvae. Você precisa configurar uma tabela com os intervalos de ramais que você está reservando para chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="c5acf-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="c5acf-108">Essas extensões precisam ser extensões virtuais (ou seja, extensões com nenhum usuário ou telefone atribuído a eles).</span><span class="sxs-lookup"><span data-stu-id="c5acf-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="c5acf-109">Cada pool que executa o aplicativo Estacionamento de Chamada pode ter um ou mais intervalos de extensões.</span><span class="sxs-lookup"><span data-stu-id="c5acf-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="c5acf-110">Esses intervalos precisam ser globalmente exclusivos em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="c5acf-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="c5acf-111">A **página Estacionamento de** Chamada exibe uma lista de todos os intervalos de números de Estacionamento de Chamada definidos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c5acf-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c5acf-112">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="c5acf-112">Tasks you can perform</span></span>

<span data-ttu-id="c5acf-113">É possível executar as seguintes tarefas na página **Estacionamento de Chamada**:</span><span class="sxs-lookup"><span data-stu-id="c5acf-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="c5acf-114">Criar um novo intervalo de números</span><span class="sxs-lookup"><span data-stu-id="c5acf-114">Create a new number range</span></span>

- <span data-ttu-id="c5acf-115">Alterar um intervalo de números existente</span><span class="sxs-lookup"><span data-stu-id="c5acf-115">Change an existing number range</span></span>

- <span data-ttu-id="c5acf-116">Excluir um intervalo de números</span><span class="sxs-lookup"><span data-stu-id="c5acf-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c5acf-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="c5acf-117">UI Reference</span></span>

<span data-ttu-id="c5acf-118">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="c5acf-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c5acf-119">**Novo** Inicia um novo intervalo de números de Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="c5acf-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="c5acf-120">**Editar** Abre o intervalo de números selecionado para edição, seleciona todos os intervalos de números na lista ou exclui o intervalo de números selecionado.</span><span class="sxs-lookup"><span data-stu-id="c5acf-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="c5acf-121">**Atualizar** Atualiza a lista de intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="c5acf-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="c5acf-122">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="c5acf-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c5acf-123">**Nome** O nome exclusivo que identifica o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="c5acf-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="c5acf-124">**Intervalo inicial** O número inicial do intervalo.</span><span class="sxs-lookup"><span data-stu-id="c5acf-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="c5acf-125">**Intervalo final** O número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="c5acf-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="c5acf-126">**Destino** O FQDN (nome de domínio totalmente qualificado) ou ID de serviço do serviço de Aplicativo que hospeda o aplicativo Estacionamento de Chamada para o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="c5acf-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="c5acf-127">Para obter detalhes sobre recursos e recursos de Estacionamento de Chamada, consulte [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="c5acf-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="c5acf-128">Para obter detalhes sobre como trabalhar com intervalos de números de Estacionamento de Chamadas, consulte Configurar Extensões de Número de Telefone [para Estacionamento de Chamadas.](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5acf-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


