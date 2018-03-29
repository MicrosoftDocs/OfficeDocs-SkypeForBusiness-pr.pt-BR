---
title: Configurar lista de contatos Inteligente no Skype for Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumo: Saiba como ativar o recurso de lista de contatos inteligente no Skype para o cliente de negócios.'
ms.openlocfilehash: f5b5b8f7baa0ce848765a0f2b62aabb118ecb224
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-smart-contacts-list-in-skype-for-business-server"></a><span data-ttu-id="1308c-103">Configurar lista de contatos Inteligente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1308c-103">Configure Smart contacts list in Skype for Business Server</span></span>
 
<span data-ttu-id="1308c-104">**Resumo:** Saiba como ativar o recurso de lista de contatos inteligente no Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="1308c-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>
  
<span data-ttu-id="1308c-105">O recurso de lista inteligente de contatos permite a população automática das listas de contatos para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="1308c-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="1308c-106">Após a primeira usando Skype para os negócios, seu usuários que utilizarão automaticamente ver seu gerente e outras pessoas na sua equipe.</span><span class="sxs-lookup"><span data-stu-id="1308c-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="1308c-107">Esse recurso está ativado por padrão para usuários do Office 365, mas você deve habilitar explicitamente esse recurso para seus usuários locais, definindo a configuração de diretiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="1308c-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>
  
<span data-ttu-id="1308c-108">Lembre-se do seguinte ao configurar esse recurso:</span><span class="sxs-lookup"><span data-stu-id="1308c-108">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="1308c-109">Usuários, até 13, são automaticamente adicionados à lista de contatos inteligentes na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="1308c-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>
    
  1. <span data-ttu-id="1308c-110">Gerente</span><span class="sxs-lookup"><span data-stu-id="1308c-110">Manager</span></span>
    
  2. <span data-ttu-id="1308c-111">Direciona em ordem alfabética</span><span class="sxs-lookup"><span data-stu-id="1308c-111">Directs in alphabetical order</span></span>
    
  3. <span data-ttu-id="1308c-112">Pares na ordem alfabética</span><span class="sxs-lookup"><span data-stu-id="1308c-112">Peers in alphabetical order</span></span>
    
- <span data-ttu-id="1308c-113">Na primeira vez que um usuário fizer o logon, um novo grupo, denominado Meu Grupo, será criado.</span><span class="sxs-lookup"><span data-stu-id="1308c-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="1308c-114">O grupo é preenchido automaticamente com pessoas em relação de grupo do AD do usuário com base no alias do usuário preenchido no campo gerente.</span><span class="sxs-lookup"><span data-stu-id="1308c-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="1308c-115">Observe que as alterações na associação do grupo AD não provocam atualizações em Meu Grupo após ter sido inicialmente preenchido.</span><span class="sxs-lookup"><span data-stu-id="1308c-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="1308c-116">Se um usuário excluir um contato ou grupo, nenhum contato ou grupo será recriado.</span><span class="sxs-lookup"><span data-stu-id="1308c-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 
    
- <span data-ttu-id="1308c-117">Se a auto marcação estiver ativada, os contatos na lista serão marcados para as alterações de presença.</span><span class="sxs-lookup"><span data-stu-id="1308c-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="1308c-118">A auto marcação é ativada por padrão, mas você pode optar por desativá-la.</span><span class="sxs-lookup"><span data-stu-id="1308c-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 
    
- <span data-ttu-id="1308c-119">Todos os novos usuários no grupo serão informados que foram adicionados à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="1308c-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="1308c-120">Os usuários podem adicionar manualmente novos membros ao Meu Grupo ou a outros grupos da sua escolha.</span><span class="sxs-lookup"><span data-stu-id="1308c-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>
    
- <span data-ttu-id="1308c-121">Esse recurso funciona somente para os usuários que estiverem entrando pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="1308c-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="1308c-122">Se um usuário tiver feito o logon anteriormente de qualquer dispositivo -- incluindo, por exemplo, qualquer dispositivo móvel ou de um Mac -- o recurso não estará habilitado para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="1308c-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>
    
## <a name="configure-smart-contacts-list"></a><span data-ttu-id="1308c-123">Configurar lista de contatos Inteligente</span><span class="sxs-lookup"><span data-stu-id="1308c-123">Configure Smart contacts list</span></span>

<span data-ttu-id="1308c-124">Para habilitar o recurso de lista de contatos Inteligente para seus usuários, será necessário executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="1308c-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 
  
- <span data-ttu-id="1308c-125">Criar uma nova entrada de CsClientPolicy e adicioná-lo à política de cliente global.</span><span class="sxs-lookup"><span data-stu-id="1308c-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 
    
- <span data-ttu-id="1308c-126">Certifique-se de que Pesquisa da Agenda está configurada somente para Pesquisa na Web.</span><span class="sxs-lookup"><span data-stu-id="1308c-126">Make sure that Address Book Search is configured for Web Search only.</span></span>
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="1308c-127">Criar uma entrada de política para habilitar a lista de contatos Inteligente</span><span class="sxs-lookup"><span data-stu-id="1308c-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="1308c-128">Para criar uma entrada de política para habilitar o recurso de lista de contatos inteligente, use o cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam conforme segue:</span><span class="sxs-lookup"><span data-stu-id="1308c-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="1308c-129">Em seguida, use o cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para gravar as alterações na política global, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1308c-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="1308c-130">Como opção, é possível criar uma política para desativar a marcação automática da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1308c-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

<span data-ttu-id="1308c-131">Você também deve definir o parâmetro AddressBookAvailability para a política correspondente ao WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="1308c-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="1308c-132">Para obter mais informações, consulte [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1308c-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 
  
### <a name="troubleshoot"></a><span data-ttu-id="1308c-133">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="1308c-133">Troubleshoot</span></span>

<span data-ttu-id="1308c-134">Se a Lista de contatos Inteligente não está funcionando conforme o esperado, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1308c-134">If Smart contacts list is not functioning as expected, check the following:</span></span>
  
- <span data-ttu-id="1308c-135">Validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="1308c-135">Validate the configuration.</span></span> 
    
- <span data-ttu-id="1308c-136">Confirme que as informações da organização AD são preenchidas.</span><span class="sxs-lookup"><span data-stu-id="1308c-136">Confirm that the AD organization information is populated.</span></span>
    
- <span data-ttu-id="1308c-137">Colete Skype para logs do cliente de negócios em um novo usuário para análise adicional.</span><span class="sxs-lookup"><span data-stu-id="1308c-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>
    
- <span data-ttu-id="1308c-138">Confirme que o Skype para o cliente de negócios da interface do usuário não está exibindo uma mensagem que não puder se conectar ao catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="1308c-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="1308c-139">Para confirmar a conectividade do catálogo de endereços, execute uma pesquisa para um usuário do Skype para a barra de pesquisa do cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="1308c-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>
    
- <span data-ttu-id="1308c-140">Se houver problemas de conexão com a Agenda, use STrace para coletar rastreamentos HTTPS e HTTPReplay para analisar os rastreamentos coletados.</span><span class="sxs-lookup"><span data-stu-id="1308c-140">If there are problems connecting to the Address Book, use STrace to collect HTTPS traces and HTTPReplay to analyze the collected traces.</span></span> <span data-ttu-id="1308c-141">Para obter mais informações, consulte a [postagem de blog relacionado](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/).</span><span class="sxs-lookup"><span data-stu-id="1308c-141">For more information, see the [related blog post](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/).</span></span>
    
- <span data-ttu-id="1308c-142">Problemas de replicação do AD DS podem causar contatos para não ser resolvidos quando um usuário entra pela primeira vez o Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="1308c-142">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>
    

