---
title: Selecionar Agentes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Agentes são usuários designados para atender chamadas do Grupo de Resposta. Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas. Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários elegíveis. Os usuários qualificados estão habilitados para o Skype for Business Server e o Enterprise Voice.
ms.openlocfilehash: 3c79d46096a39cde01ea4c3246f71b972933c4d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829141"
---
# <a name="select-agents"></a><span data-ttu-id="30b3d-106">Selecionar Agentes</span><span class="sxs-lookup"><span data-stu-id="30b3d-106">Select Agents</span></span>

<span data-ttu-id="30b3d-107">Agentes são usuários designados para atender chamadas do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="30b3d-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="30b3d-108">Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="30b3d-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="30b3d-109">Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários elegíveis.</span><span class="sxs-lookup"><span data-stu-id="30b3d-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="30b3d-110">Os usuários qualificados estão habilitados para o Skype for Business Server e o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="30b3d-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="30b3d-111">Use a caixa de diálogo **Selecionar Agentes** para selecionar os usuários que serão adicionados a um grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="30b3d-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="30b3d-112">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="30b3d-112">UI Reference</span></span>

<span data-ttu-id="30b3d-113">A lista a seguir descreve os controles na caixa de diálogo **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="30b3d-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="30b3d-114">**Find** Pesquisa o endereço SIP ou o nome de exibição de um usuário.</span><span class="sxs-lookup"><span data-stu-id="30b3d-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="30b3d-115">Insira parte ou todo o endereço ou nome.</span><span class="sxs-lookup"><span data-stu-id="30b3d-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="30b3d-116">Deixe a caixa de pesquisa vazia para exibir todos os usuários habilitados para o Skype for Business Server e o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="30b3d-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="30b3d-117">**Máximo de usuários a exibir** Altera o número de resultados retornados exibidos.</span><span class="sxs-lookup"><span data-stu-id="30b3d-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="30b3d-118">Use esse contador para limitar a pesquisa, se você esperar muitos resultados.</span><span class="sxs-lookup"><span data-stu-id="30b3d-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="30b3d-119">A lista a seguir descreve os campos na caixa de diálogo **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="30b3d-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="30b3d-120">**Agente** Exibe os nomes de usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="30b3d-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="30b3d-121">**Endereço SIP** Exibe os endereços SIP do usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="30b3d-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="30b3d-122">**Telefonia** Exibe o valor do campo **Telefonia** definido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="30b3d-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="30b3d-123">**Habilitado** Exibe o valor do campo **Habilitado para Lync Server** definido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="30b3d-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="30b3d-124">Para obter detalhes sobre como trabalhar com grupos de agente, consulte [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="30b3d-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


