---
title: Configurar a lista de contatos inteligentes nos clientes do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumo: saiba como ativar o recurso da lista de contatos inteligentes no cliente Skype for Business.'
ms.openlocfilehash: 17981e13c239241f050704b7c98593f95a29ab27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234234"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="318e6-103">Configurar a lista de contatos inteligentes nos clientes do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="318e6-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="318e6-104">**Resumo:** Saiba como ativar o recurso da lista de contatos inteligentes no cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="318e6-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="318e6-105">O recurso de lista inteligente de contatos permite a população automática das listas de contatos para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="318e6-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="318e6-106">Depois de usar o Skype for Business, os usuários verão automaticamente o seu gerente e outras pessoas da equipe.</span><span class="sxs-lookup"><span data-stu-id="318e6-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="318e6-107">Esse recurso está ativado por padrão para os usuários do Office 365, mas você deve habilitar explicitamente esse recurso para seus usuários locais definindo a configuração de política do cliente.</span><span class="sxs-lookup"><span data-stu-id="318e6-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="318e6-108">Lembre-se do seguinte ao configurar esse recurso:</span><span class="sxs-lookup"><span data-stu-id="318e6-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="318e6-109">Os usuários, até 13, são adicionados automaticamente à lista de contatos inteligentes na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="318e6-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="318e6-110">Gerente</span><span class="sxs-lookup"><span data-stu-id="318e6-110">Manager</span></span>

  2. <span data-ttu-id="318e6-111">Direciona em ordem alfabética</span><span class="sxs-lookup"><span data-stu-id="318e6-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="318e6-112">Pares na ordem alfabética</span><span class="sxs-lookup"><span data-stu-id="318e6-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="318e6-113">Na primeira vez que um usuário fizer o logon, um novo grupo, denominado Meu Grupo, será criado.</span><span class="sxs-lookup"><span data-stu-id="318e6-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="318e6-114">O grupo é automaticamente preenchido com pessoas na relação do grupo de anúncios do usuário com base no alias do usuário preenchido no campo gerente.</span><span class="sxs-lookup"><span data-stu-id="318e6-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="318e6-115">Observe que as alterações na associação do grupo AD não provocam atualizações em Meu Grupo após ter sido inicialmente preenchido.</span><span class="sxs-lookup"><span data-stu-id="318e6-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="318e6-116">Se um usuário excluir um contato ou grupo, nenhum contato ou grupo será recriado.</span><span class="sxs-lookup"><span data-stu-id="318e6-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="318e6-117">Se a auto marcação estiver ativada, os contatos na lista serão marcados para as alterações de presença.</span><span class="sxs-lookup"><span data-stu-id="318e6-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="318e6-118">A auto marcação é ativada por padrão, mas você pode optar por desativá-la.</span><span class="sxs-lookup"><span data-stu-id="318e6-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="318e6-119">Todos os novos usuários no grupo serão informados que foram adicionados à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="318e6-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="318e6-120">Os usuários podem adicionar manualmente novos membros ao Meu Grupo ou a outros grupos da sua escolha.</span><span class="sxs-lookup"><span data-stu-id="318e6-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="318e6-121">Esse recurso funciona somente para os usuários que estiverem entrando pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="318e6-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="318e6-122">Se um usuário tiver feito o logon anteriormente de qualquer dispositivo -- incluindo, por exemplo, qualquer dispositivo móvel ou de um Mac -- o recurso não estará habilitado para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="318e6-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="318e6-123">Configurar lista de contatos Inteligente</span><span class="sxs-lookup"><span data-stu-id="318e6-123">Configure Smart contacts list</span></span>

<span data-ttu-id="318e6-124">Para habilitar o recurso de lista de contatos Inteligente para seus usuários, será necessário executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="318e6-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="318e6-125">Crie uma nova entrada CsClientPolicy e adicione-a à política de cliente global.</span><span class="sxs-lookup"><span data-stu-id="318e6-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="318e6-126">Certifique-se de que Pesquisa da Agenda está configurada somente para Pesquisa na Web.</span><span class="sxs-lookup"><span data-stu-id="318e6-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="318e6-127">Criar uma entrada de política para habilitar a lista de contatos Inteligente</span><span class="sxs-lookup"><span data-stu-id="318e6-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="318e6-128">Para criar uma entrada de política para habilitar o recurso da lista de contatos inteligentes, use o cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="318e6-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="318e6-129">Em seguida, use o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para gravar as alterações na política global da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="318e6-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="318e6-130">Como opção, é possível criar uma política para desativar a marcação automática da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="318e6-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="318e6-131">Você também deve definir o parâmetro AddressBookAvailability para a política correspondente ao WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="318e6-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="318e6-132">Para obter mais informações, consulte [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="318e6-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="318e6-133">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="318e6-133">Troubleshoot</span></span>

<span data-ttu-id="318e6-134">Se a Lista de contatos Inteligente não está funcionando conforme o esperado, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="318e6-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="318e6-135">Validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="318e6-135">Validate the configuration.</span></span> 

- <span data-ttu-id="318e6-136">Confirme se as informações da organização AD foram preenchidas.</span><span class="sxs-lookup"><span data-stu-id="318e6-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="318e6-137">Coletar logs do cliente Skype for Business em um novo usuário para análise adicional.</span><span class="sxs-lookup"><span data-stu-id="318e6-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="318e6-138">Confirme se a interface do usuário do cliente Skype for Business não está exibindo uma mensagem informando que não consegue se conectar ao catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="318e6-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="318e6-139">Para confirmar a conectividade do catálogo de endereços, realize uma pesquisa de um usuário na barra de pesquisa do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="318e6-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="318e6-140">Os problemas de replicação do AD DS podem fazer com que os contatos sejam desresolvidos quando um usuário entrar pela primeira vez no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="318e6-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


