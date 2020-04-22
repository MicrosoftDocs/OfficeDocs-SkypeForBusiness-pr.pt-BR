---
title: Configurar a lista de contatos inteligente nos clientes do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumo: saiba como ativar o recurso de lista de contatos inteligentes no cliente Skype for Business.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776686"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="47c4b-103">Configurar a lista de contatos inteligente nos clientes do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="47c4b-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="47c4b-104">**Resumo:** Saiba como ativar o recurso de lista de contatos inteligente no cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="47c4b-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="47c4b-105">O recurso de lista de contatos inteligente permite o preenchimento automático de listas de contatos para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="47c4b-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="47c4b-106">Usando o Skype for Business pela primeira vez, seus usuários verão automaticamente o gerente e outras pessoas de sua equipe.</span><span class="sxs-lookup"><span data-stu-id="47c4b-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="47c4b-107">Este recurso está ativado por padrão para os usuários do Microsoft 365 e do Office 365, mas você deve habilitar explicitamente esse recurso para os usuários locais, definindo a configuração de política do cliente.</span><span class="sxs-lookup"><span data-stu-id="47c4b-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="47c4b-108">Tenha em mente o seguinte ao configurar esse recurso:</span><span class="sxs-lookup"><span data-stu-id="47c4b-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="47c4b-109">Os usuários, até 13, são automaticamente adicionados à lista de contatos inteligentes na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="47c4b-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="47c4b-110">Gerente</span><span class="sxs-lookup"><span data-stu-id="47c4b-110">Manager</span></span>

  2. <span data-ttu-id="47c4b-111">Direciona em ordem alfabética</span><span class="sxs-lookup"><span data-stu-id="47c4b-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="47c4b-112">Pares em ordem alfabética</span><span class="sxs-lookup"><span data-stu-id="47c4b-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="47c4b-113">Na primeira vez que um usuário faz logon, um novo grupo, chamado My Group, é criado.</span><span class="sxs-lookup"><span data-stu-id="47c4b-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="47c4b-114">O grupo é preenchido automaticamente com pessoas na relação de grupo do AD do usuário com base no alias de usuário preenchido no campo gerente.</span><span class="sxs-lookup"><span data-stu-id="47c4b-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="47c4b-115">Observe que as alterações feitas na associação do grupo do AD não causam atualizações para o meu grupo depois que ele é inicialmente preenchido.</span><span class="sxs-lookup"><span data-stu-id="47c4b-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="47c4b-116">Se um usuário excluir um contato ou grupo, nem o contato nem o grupo serão recriados.</span><span class="sxs-lookup"><span data-stu-id="47c4b-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="47c4b-117">Se a marcação automática estiver ativada, os contatos na lista serão marcados para alterações de presença.</span><span class="sxs-lookup"><span data-stu-id="47c4b-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="47c4b-118">A marcação automática é ativada por padrão, mas você pode optar por desativá-la.</span><span class="sxs-lookup"><span data-stu-id="47c4b-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="47c4b-119">Todos os novos usuários no grupo serão informados de que foram adicionados à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="47c4b-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="47c4b-120">Os usuários podem adicionar manualmente novos membros ao meu grupo ou a outros grupos de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="47c4b-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="47c4b-121">Esse recurso funciona somente para usuários que estão entrando pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="47c4b-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="47c4b-122">Se um usuário tiver se conectado anteriormente de qualquer dispositivo, incluindo, por exemplo, qualquer dispositivo móvel ou um Mac--o recurso não está habilitado para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="47c4b-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="47c4b-123">Configurar a lista de contatos inteligente</span><span class="sxs-lookup"><span data-stu-id="47c4b-123">Configure Smart contacts list</span></span>

<span data-ttu-id="47c4b-124">Para habilitar o recurso de lista de contatos inteligentes para seus usuários, será necessário executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="47c4b-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="47c4b-125">Crie uma nova entrada de CsClientPolicy e adicione-a à política de cliente global.</span><span class="sxs-lookup"><span data-stu-id="47c4b-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="47c4b-126">Verifique se a pesquisa do catálogo de endereços está configurada somente para pesquisa na Web.</span><span class="sxs-lookup"><span data-stu-id="47c4b-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="47c4b-127">Criar uma entrada de política para habilitar a lista de contatos inteligente</span><span class="sxs-lookup"><span data-stu-id="47c4b-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="47c4b-128">Para criar uma entrada de política para habilitar o recurso de lista de contatos inteligente, use o cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="47c4b-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="47c4b-129">Em seguida, use o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para gravar as alterações na política global da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="47c4b-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="47c4b-130">Opcionalmente, você pode criar uma política para desativar a marcação automática da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="47c4b-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="47c4b-131">Você também deve definir o parâmetro AddressBookAvailability para a política correspondente como WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="47c4b-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="47c4b-132">Para obter mais informações, consulte [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="47c4b-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="47c4b-133">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="47c4b-133">Troubleshoot</span></span>

<span data-ttu-id="47c4b-134">Se a lista de contatos inteligentes não estiver funcionando conforme o esperado, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47c4b-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="47c4b-135">Valide a configuração.</span><span class="sxs-lookup"><span data-stu-id="47c4b-135">Validate the configuration.</span></span> 

- <span data-ttu-id="47c4b-136">Confirme se as informações da organização do AD estão preenchidas.</span><span class="sxs-lookup"><span data-stu-id="47c4b-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="47c4b-137">Coletar logs de cliente do Skype for Business em um novo usuário para análise adicional.</span><span class="sxs-lookup"><span data-stu-id="47c4b-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="47c4b-138">Confirme que a interface do usuário do cliente Skype for Business não está exibindo uma mensagem informando que não pode se conectar ao catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="47c4b-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="47c4b-139">Para confirmar a conectividade do catálogo de endereços, execute uma pesquisa para um usuário na barra de pesquisa de cliente do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="47c4b-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="47c4b-140">Os problemas de replicação do AD DS podem fazer com que os contatos não sejam resolvidos quando um usuário entra pela primeira vez no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="47c4b-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


