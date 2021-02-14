---
title: Política de Local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: bb7a63e63864b3d342d37fd62b26f806434644b7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824781"
---
# <a name="location-policy"></a><span data-ttu-id="cfc83-103">Política de Local</span><span class="sxs-lookup"><span data-stu-id="cfc83-103">Location Policy</span></span>

<span data-ttu-id="cfc83-104">As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="cfc83-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="cfc83-105">As políticas de local incluem a política global e, como opção, uma ou mais políticas de site e de usuário:</span><span class="sxs-lookup"><span data-stu-id="cfc83-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="cfc83-106">**Política global:** A política global é criada por padrão.</span><span class="sxs-lookup"><span data-stu-id="cfc83-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="cfc83-107">É possível editar a política global, mas não é possível exclui-la.</span><span class="sxs-lookup"><span data-stu-id="cfc83-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="cfc83-108">Se você tentar remover a política global, todas as configurações serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="cfc83-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="cfc83-109">**Políticas de site (opcional):** Você pode criar uma ou mais políticas de local de site, cada uma delas se aplicando a um site específico.</span><span class="sxs-lookup"><span data-stu-id="cfc83-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="cfc83-110">As políticas de site substituem a política global.</span><span class="sxs-lookup"><span data-stu-id="cfc83-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="cfc83-111">**Políticas de usuário (opcional):** Você pode criar uma ou mais políticas de local de usuário, cada uma delas se aplicando a um usuário ou grupo de usuários específico.</span><span class="sxs-lookup"><span data-stu-id="cfc83-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="cfc83-112">As políticas de usuário substituem a política global e as políticas de site.</span><span class="sxs-lookup"><span data-stu-id="cfc83-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="cfc83-113">Também é possível atribuir políticas de local a sites de rede, que são grupos de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="cfc83-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="cfc83-114">As políticas de local atribuídas a sites de rede têm precedência sobre todas as outras políticas de usuário.</span><span class="sxs-lookup"><span data-stu-id="cfc83-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="cfc83-115">Para obter detalhes sobre como atribuir políticas de local a sites de rede usando cmdlets, consulte Adicionar uma política de local a um site de rede no [Skype for Business Server.](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)</span><span class="sxs-lookup"><span data-stu-id="cfc83-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="cfc83-116">Para obter detalhes sobre como usar o Painel de Controle do Skype for Business Server para atribuir uma política de local a um site de rede, consulte [Configurando sites de rede.](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)</span><span class="sxs-lookup"><span data-stu-id="cfc83-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="cfc83-117">A página **Política de Local** exibe uma lista de todas as políticas de local definidas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="cfc83-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="cfc83-118">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="cfc83-118">Tasks you can perform</span></span>

<span data-ttu-id="cfc83-119">É possível executar as seguintes tarefas na página **Política de Local**:</span><span class="sxs-lookup"><span data-stu-id="cfc83-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="cfc83-120">Criar uma nova política de local de site ou uma política de local de usuário</span><span class="sxs-lookup"><span data-stu-id="cfc83-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="cfc83-121">Alterar a política global ou uma política de site existente ou política de usuário</span><span class="sxs-lookup"><span data-stu-id="cfc83-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="cfc83-122">Excluir uma política de site ou de usuário</span><span class="sxs-lookup"><span data-stu-id="cfc83-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cfc83-123">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="cfc83-123">UI Reference</span></span>

<span data-ttu-id="cfc83-124">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="cfc83-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="cfc83-125">**Novo** Inicia uma nova política de local de site ou uma política de local de usuário.</span><span class="sxs-lookup"><span data-stu-id="cfc83-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="cfc83-126">**Editar** Abre a política de local selecionada para editá-la, seleciona todas as políticas de local na lista ou exclui a política de site ou política de usuário selecionada.</span><span class="sxs-lookup"><span data-stu-id="cfc83-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cfc83-127">Para a política global, **Excluir** redefine as configurações para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="cfc83-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="cfc83-128">**Atualizar** Atualiza a lista de políticas de local.</span><span class="sxs-lookup"><span data-stu-id="cfc83-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="cfc83-129">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="cfc83-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="cfc83-130">**Nome** Identifica a política de local.</span><span class="sxs-lookup"><span data-stu-id="cfc83-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="cfc83-131">**Escopo** Identifica o escopo da política de local: global, site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="cfc83-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="cfc83-132">**E9-1-1** Verifica se os usuários atribuídos a essa política de local estão habilitados para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="cfc83-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="cfc83-133">**Localização** Especifica se os usuários serão solicitados ou não a inserir informações de local quando seus clientes se registram no Skype for Business Server em um novo local e se veem um aviso de isenção de responsabilidade se descartarem a solicitação sem inserir informações de local.</span><span class="sxs-lookup"><span data-stu-id="cfc83-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="cfc83-134">**Uso de PSTN** Especifica o uso da PSTN (Rede Telefônica Pública Comutado) usada para determinar a rota de voz usada para rotear chamadas de emergência de clientes que usam esse perfil.</span><span class="sxs-lookup"><span data-stu-id="cfc83-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="cfc83-135">**Número de E9-1-1** Especifica o número discado para alcançar os serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="cfc83-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="cfc83-136">**Máscara de E9-1-1** Especifica um número que um usuário disca e que é convertido no número de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="cfc83-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="cfc83-137">Para obter detalhes sobre os recursos do serviço de emergência do Enterprise Voice, consulte [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="cfc83-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="cfc83-138">Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="cfc83-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


