---
title: Selecionar Agentes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: Os agentes são usuários designados para atender chamadas em grupo de resposta. Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas. Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários aptos. Os usuários qualificados estão habilitados para o Skype for Business Server e o Enterprise Voice.
ms.openlocfilehash: 0efc0c0afeff33472075c68cf4300bb5ecf51c66
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793469"
---
# <a name="select-agents"></a><span data-ttu-id="06bc0-106">Selecionar Agentes</span><span class="sxs-lookup"><span data-stu-id="06bc0-106">Select Agents</span></span>

<span data-ttu-id="06bc0-107">Os agentes são usuários designados para atender chamadas em grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="06bc0-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="06bc0-108">Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="06bc0-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="06bc0-109">Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários aptos.</span><span class="sxs-lookup"><span data-stu-id="06bc0-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="06bc0-110">Os usuários qualificados estão habilitados para o Skype for Business Server e o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="06bc0-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="06bc0-111">Use a caixa de diálogo **Selecionar Agentes** para selecionar os usuários que serão adicionados a um grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="06bc0-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="06bc0-112">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="06bc0-112">UI Reference</span></span>

<span data-ttu-id="06bc0-113">A lista a seguir descreve os controles na caixa de diálogo **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="06bc0-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="06bc0-114">**Localizar** Procura o endereço SIP ou o nome de exibição de um usuário.</span><span class="sxs-lookup"><span data-stu-id="06bc0-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="06bc0-115">Insira parte ou todo o endereço ou nome.</span><span class="sxs-lookup"><span data-stu-id="06bc0-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="06bc0-116">Deixe a caixa de pesquisa vazia para exibir todos os usuários que estão habilitados para o Skype for Business Server e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="06bc0-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="06bc0-117">**Máximo de usuários a serem exibidos** Altera o número de resultados retornados que são exibidos.</span><span class="sxs-lookup"><span data-stu-id="06bc0-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="06bc0-118">Use esse contador para limitar a pesquisa, caso você espere muitos resultados.</span><span class="sxs-lookup"><span data-stu-id="06bc0-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="06bc0-119">A lista a seguir descreve os campos na caixa de diálogo  **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="06bc0-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="06bc0-120">**Agente** do Exibe os nomes de usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="06bc0-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="06bc0-121">**Endereço SIP** Exibe os endereços SIP do usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="06bc0-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="06bc0-122">**Telefonia** Exibe o valor do campo de **telefonia** definido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="06bc0-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="06bc0-123">**Habilitado** Exibe o valor do campo **habilitado para Lync Server** definido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="06bc0-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="06bc0-124">Para obter detalhes sobre como trabalhar com grupos de agente, consulte [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="06bc0-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


