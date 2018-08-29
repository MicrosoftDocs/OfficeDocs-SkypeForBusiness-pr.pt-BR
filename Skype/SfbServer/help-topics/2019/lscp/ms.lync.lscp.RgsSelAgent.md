---
title: Selecionar Agentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: Operadores são usuários que são projetados para atender chamadas de grupo de resposta. Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas. Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários aptos. Usuários qualificados estão habilitados para Skype para Business Server e o Enterprise Voice.
ms.openlocfilehash: 23e274f11183742ab96f4117ea5d7c754596253a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23262824"
---
# <a name="select-agents"></a><span data-ttu-id="31b7e-106">Selecionar Agentes</span><span class="sxs-lookup"><span data-stu-id="31b7e-106">Select Agents</span></span>

<span data-ttu-id="31b7e-107">Operadores são usuários que são projetados para atender chamadas de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="31b7e-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="31b7e-108">Os grupos de resposta precisam ter um grupo de agentes atribuídos que identifica os agentes que podem receber chamadas para o grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="31b7e-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="31b7e-109">Uma forma de criar um grupo de agentes é definir um grupo personalizado selecionando usuários aptos.</span><span class="sxs-lookup"><span data-stu-id="31b7e-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="31b7e-110">Usuários qualificados estão habilitados para Skype para Business Server e o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="31b7e-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="31b7e-111">Use a caixa de diálogo **Selecionar Agentes** para selecionar os usuários que serão adicionados a um grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="31b7e-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="31b7e-112">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="31b7e-112">UI Reference</span></span>

<span data-ttu-id="31b7e-113">A lista a seguir descreve os controles na caixa de diálogo **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="31b7e-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="31b7e-114">**Encontre** Procura o SIP de endereços ou o nome de exibição para um usuário.</span><span class="sxs-lookup"><span data-stu-id="31b7e-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="31b7e-115">Insira parte ou todo o endereço ou nome.</span><span class="sxs-lookup"><span data-stu-id="31b7e-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="31b7e-116">Deixe a caixa de pesquisa vazio para exibir todos os usuários habilitados para o Skype para Business Server e o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="31b7e-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="31b7e-117">**Máximo de usuários para exibir** Altera o número de resultados retornados que são exibidos.</span><span class="sxs-lookup"><span data-stu-id="31b7e-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="31b7e-118">Use esse contador para limitar a pesquisa, caso você espere muitos resultados.</span><span class="sxs-lookup"><span data-stu-id="31b7e-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="31b7e-119">A lista a seguir descreve os campos na caixa de diálogo  **Selecionar Agentes**.</span><span class="sxs-lookup"><span data-stu-id="31b7e-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="31b7e-120">**Agente** Exibe os nomes de usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="31b7e-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="31b7e-121">**Endereço SIP** Exibe os endereços SIP do usuário retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="31b7e-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="31b7e-122">**Telefonia** Exibe o valor do campo **telefonia** definido para usuários.</span><span class="sxs-lookup"><span data-stu-id="31b7e-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="31b7e-123">**Habilitado** Exibe o valor do campo **habilitado para o Lync Server** definido para usuários.</span><span class="sxs-lookup"><span data-stu-id="31b7e-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="31b7e-124">Para obter detalhes sobre como trabalhar com grupos de operadores, consulte [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="31b7e-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


