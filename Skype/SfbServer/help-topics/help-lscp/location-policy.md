---
title: Política de Local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: 5b5afaff156ed0692c7c0ee80ad66dc0b55ed343
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910880"
---
# <a name="location-policy"></a><span data-ttu-id="a3003-103">Política de Local</span><span class="sxs-lookup"><span data-stu-id="a3003-103">Location Policy</span></span>

<span data-ttu-id="a3003-104">As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="a3003-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="a3003-105">As políticas de local incluem a política global e, como opção, uma ou mais políticas de site e de usuário:</span><span class="sxs-lookup"><span data-stu-id="a3003-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="a3003-106">**Política global:** A política global criada por padrão.</span><span class="sxs-lookup"><span data-stu-id="a3003-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="a3003-107">É possível editar a política global, mas não é possível excluí-la.</span><span class="sxs-lookup"><span data-stu-id="a3003-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="a3003-108">Se você tentar remover a política global, todas as configurações serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="a3003-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="a3003-109">**(Opcionais) de políticas de site:** Você pode criar políticas de local site um ou mais, cada um deles se aplica a um site específico.</span><span class="sxs-lookup"><span data-stu-id="a3003-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="a3003-110">As políticas de site substituem a política global.</span><span class="sxs-lookup"><span data-stu-id="a3003-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="a3003-111">**Políticas de usuário (opcionais):** Você pode criar políticas de local usuário um ou mais, cada um deles se aplica a um usuário específico ou grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="a3003-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="a3003-112">As políticas de usuário substituem a política global e as políticas de site.</span><span class="sxs-lookup"><span data-stu-id="a3003-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="a3003-113">Também é possível atribuir políticas de local a sites de rede, que são grupos de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="a3003-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="a3003-114">As políticas de local atribuídas a sites de rede têm precedência sobre todas as outras políticas de usuário.</span><span class="sxs-lookup"><span data-stu-id="a3003-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="a3003-115">Para obter detalhes sobre como atribuir políticas de local aos sites de rede usando cmdlets, consulte [Adicionar uma política de local em um site de rede no Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="a3003-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="a3003-116">Para obter detalhes sobre como usar o Skype para painel de controle do Business Server para atribuir uma política de local a um site de rede, consulte [Configurando Sites de rede](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3003-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="a3003-117">A página  **Política de Local** exibe uma lista de todas as políticas de local definidas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3003-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a3003-118">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="a3003-118">Tasks you can perform</span></span>

<span data-ttu-id="a3003-119">É possível executar as seguintes tarefas na página  **Política de Local**:</span><span class="sxs-lookup"><span data-stu-id="a3003-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="a3003-120">Criar uma nova política de local de site ou uma política de local de usuário</span><span class="sxs-lookup"><span data-stu-id="a3003-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="a3003-121">Alterar a política global ou uma política de site existente ou política de usuário</span><span class="sxs-lookup"><span data-stu-id="a3003-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="a3003-122">Excluir uma política de site ou de usuário</span><span class="sxs-lookup"><span data-stu-id="a3003-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a3003-123">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="a3003-123">UI Reference</span></span>

<span data-ttu-id="a3003-124">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="a3003-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="a3003-125">**Novo** Inicia uma nova política de local de site ou política de local do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3003-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="a3003-126">**Editar** Abre a política de localização selecionada para editá-la, seleciona todas as políticas de local na lista ou exclui a política de site selecionado ou usuário.</span><span class="sxs-lookup"><span data-stu-id="a3003-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3003-127">Para a política global, **Excluir** redefine as configurações para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="a3003-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="a3003-128">**Atualizar** Atualiza a lista de políticas de local.</span><span class="sxs-lookup"><span data-stu-id="a3003-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="a3003-129">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="a3003-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a3003-130">**Nome** Identifica a diretiva de local.</span><span class="sxs-lookup"><span data-stu-id="a3003-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="a3003-131">**Escopo** Identifica o escopo da política de local: global, site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="a3003-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="a3003-132">**E9-1-1** Verificado se os usuários atribuídos a essa política de local estão habilitados para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="a3003-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="a3003-133">**Local** Especifica se é ou não os usuários são solicitados a digitar informações de localização quando seu cliente registra com Skype para Business Server em um novo local e se eles verão um aviso de isenção se recusar o aviso, sem digitar informações de local.</span><span class="sxs-lookup"><span data-stu-id="a3003-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="a3003-134">**Uso da PSTN** Especifica o uso PSTN (rede) telefônica comutada pública que é usado para determinar a rota de voz usada para rotear chamadas de emergência de clientes usando esse perfil.</span><span class="sxs-lookup"><span data-stu-id="a3003-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="a3003-135">**Número de E9-1-1** Especifica o número discado para acessar os serviços de emergências.</span><span class="sxs-lookup"><span data-stu-id="a3003-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="a3003-136">**Máscara de E9-1-1** Especifica um número discado pelo usuário que é convertido no número de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="a3003-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="a3003-137">Para obter detalhes sobre os recursos de serviço de emergência do Enterprise Voice e recursos, consulte [Visão geral do E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a3003-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="a3003-138">Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="a3003-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


