---
title: Selecionar Agentes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: Os agentes são usuários designados para atender chamadas em grupo de resposta. Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas. Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários aptos. Os usuários qualificados estão habilitados para o Skype for Business Server e o Enterprise Voice.
ms.openlocfilehash: 15185ab3ad7bb16018d7995d5e7eaef6198dc68a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690766"
---
# <a name="select-agents"></a><span data-ttu-id="49aca-106">Selecionar Agentes</span><span class="sxs-lookup"><span data-stu-id="49aca-106">Select Agents</span></span>

<span data-ttu-id="49aca-107">Os agentes são usuários designados para atender chamadas em grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="49aca-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="49aca-108">Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="49aca-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="49aca-109">Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários aptos.</span><span class="sxs-lookup"><span data-stu-id="49aca-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="49aca-110">Os usuários qualificados estão habilitados para o Skype for Business Server e o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="49aca-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="49aca-111">Use a caixa de diálogo **Selecionar Agentes** para selecionar os usuários que serão adicionados a um grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="49aca-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="49aca-112">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="49aca-112">UI Reference</span></span>

<span data-ttu-id="49aca-113">A lista a seguir descreve os controles na caixa de diálogo **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="49aca-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="49aca-114">**Localizar** Procura o endereço SIP ou o nome de exibição de um usuário.</span><span class="sxs-lookup"><span data-stu-id="49aca-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="49aca-115">Insira parte ou todo o endereço ou nome.</span><span class="sxs-lookup"><span data-stu-id="49aca-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="49aca-116">Deixe a caixa de pesquisa vazia para exibir todos os usuários que estão habilitados para o Skype for Business Server e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="49aca-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="49aca-117">**Máximo de usuários a serem exibidos** Altera o número de resultados retornados que são exibidos.</span><span class="sxs-lookup"><span data-stu-id="49aca-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="49aca-118">Use esse contador para limitar a pesquisa, caso você espere muitos resultados.</span><span class="sxs-lookup"><span data-stu-id="49aca-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="49aca-119">A lista a seguir descreve os campos na caixa de diálogo  **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="49aca-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="49aca-120">**Agente** do Exibe os nomes de usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="49aca-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="49aca-121">**Endereço SIP** Exibe os endereços SIP do usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="49aca-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="49aca-122">**Telefonia** Exibe o valor do campo de **telefonia** definido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="49aca-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="49aca-123">**Habilitado** Exibe o valor do campo **habilitado para Lync Server** definido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="49aca-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="49aca-124">Para obter detalhes sobre como trabalhar com grupos de agente, consulte [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="49aca-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


