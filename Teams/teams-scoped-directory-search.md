---
title: Usar a pesquisa de diretório no escopo do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Saiba como usar a pesquisa de diretório em escopo do Microsoft Teams para fornecer exibições personalizadas do diretório.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e3b95e9d8de04abc6299a52a27cf07d95365a4f
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305794"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="d8e15-103">Usar a pesquisa de diretório no escopo do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8e15-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="d8e15-104">A pesquisa de diretório em escopo do Microsoft Teams permite que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8e15-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="d8e15-105">O Microsoft Teams permite que as organizações forneçam modos de exibição personalizados do diretório para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="d8e15-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="d8e15-106">O Microsoft Teams usa [políticas do catálogo de endereços do Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) para dar suporte a essas exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d8e15-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="d8e15-107">Depois que as políticas são habilitadas, os resultados retornados por pesquisas para outros usuários (por exemplo, para iniciar um chat ou para adicionar membros a uma equipe) serão definidos em escopo de acordo com as políticas configuradas.</span><span class="sxs-lookup"><span data-stu-id="d8e15-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="d8e15-108">Os usuários não poderão pesquisar nem descobrir Teams quando a pesquisa com escopo estiver em vigor.</span><span class="sxs-lookup"><span data-stu-id="d8e15-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="d8e15-109">Em ambientes híbridos do Exchange, esse recurso funciona apenas com caixas de correio do Exchange Online e não com caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="d8e15-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="d8e15-110">Quando você deve usar pesquisas de diretório de escopo?</span><span class="sxs-lookup"><span data-stu-id="d8e15-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="d8e15-111">Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="d8e15-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="d8e15-112">Por exemplo, você pode querer usar a pesquisa de diretório em escopo nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="d8e15-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="d8e15-113">Sua organização tem várias empresas dentro no locatário que você deseja manter separadas.</span><span class="sxs-lookup"><span data-stu-id="d8e15-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="d8e15-114">Sua escola quer limitar os chats entre professores e alunos.</span><span class="sxs-lookup"><span data-stu-id="d8e15-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="d8e15-115">Para saber como usar as políticas do catálogo de endereços, leia [as políticas do catálogo de endereços no Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="d8e15-115">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8e15-116">As políticas de catálogo de endereços fornecem apenas uma separação virtual de usuários da perspectiva do diretório.</span><span class="sxs-lookup"><span data-stu-id="d8e15-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="d8e15-117">Os usuários ainda podem iniciar comunicações com outras pessoas fornecendo endereços de e-mail completos.</span><span class="sxs-lookup"><span data-stu-id="d8e15-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="d8e15-118">Também é importante observar que todos os dados do usuário que já haviam sido armazenados em cache, antes da aplicação de políticas novas ou atualizadas do catálogo de endereços, permanecerão disponíveis para os usuários por até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="d8e15-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="d8e15-119">Ativar a pesquisa de diretório escopo</span><span class="sxs-lookup"><span data-stu-id="d8e15-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="d8e15-120">Use as políticas de catálogo de endereços para configurar sua organização em subgrupos virtuais.</span><span class="sxs-lookup"><span data-stu-id="d8e15-120">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="d8e15-121">Para obter mais informações, consulte [procedimentos para políticas do catálogo de endereços](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="d8e15-121">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="d8e15-122">No centro de administração do Microsoft Teams, selecione**configurações de equipes** **de configurações** > de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="d8e15-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="d8e15-123">Em **Pesquisar**, ao lado de **pesquisa de diretório de escopo no Teams usando uma política de catálogo de endereços do Exchange (APB)**, ative o botão **de alternância.**</span><span class="sxs-lookup"><span data-stu-id="d8e15-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Pesquisa de diretório em escopo no centro de administração do Microsoft Teams](media/teams-scoped-directory-search-image1.png)



