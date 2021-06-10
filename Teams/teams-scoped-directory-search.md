---
title: Usar a pesquisa de diretório no escopo do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
description: Saiba como usar a Microsoft Teams de diretório com escopo para fornecer exibições personalizadas do diretório.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1048b6451163cd7b0cdbcd3f52e48c6b0f4811d1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717792"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="c006c-103">Usar a pesquisa de diretório no escopo do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c006c-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="c006c-104">Microsoft Teams pesquisa de diretório com escopo permite que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c006c-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="c006c-105">Microsoft Teams permite que as organizações forneçam exibições personalizadas do diretório para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="c006c-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="c006c-106">Microsoft Teams usa políticas [de Barreira de Informações](/microsoft-365/compliance/information-barriers) para dar suporte a essas exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c006c-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="c006c-107">Depois que as políticas são habilitadas, os resultados retornados pelas pesquisas de outros usuários (por exemplo, para iniciar um chat ou para adicionar membros a uma equipe) serão escopos de acordo com as políticas configuradas.</span><span class="sxs-lookup"><span data-stu-id="c006c-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="c006c-108">Os usuários não poderão pesquisar ou descobrir nenhuma equipe quando a pesquisa com escopo estiver em vigor, mas os membros existentes nessas equipes podem adicionar usuários, conforme permitido pelas políticas ativas da Barreira de Informações.</span><span class="sxs-lookup"><span data-stu-id="c006c-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="c006c-109">Em Exchange ambientes híbridos, esse recurso só funciona com Exchange Online caixas de correio, e não com caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="c006c-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

<span data-ttu-id="c006c-110">Consulte também [Políticas de livro de endereços Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="c006c-110">See also [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="c006c-111">Quando você deve usar pesquisas de diretório com escopo?</span><span class="sxs-lookup"><span data-stu-id="c006c-111">When should you use scoped directory searches?</span></span>

<span data-ttu-id="c006c-112">Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política do livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="c006c-112">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="c006c-113">Por exemplo, talvez você queira usar a pesquisa de diretório com escopo nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="c006c-113">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="c006c-114">Sua organização tem várias empresas dentro no locatário que você deseja manter separadas.</span><span class="sxs-lookup"><span data-stu-id="c006c-114">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="c006c-115">Sua escola quer limitar os chats entre professores e alunos.</span><span class="sxs-lookup"><span data-stu-id="c006c-115">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="c006c-116">Para saber como usar políticas de livro de endereços, leia [Políticas de Barreira](/microsoft-365/compliance/information-barriers)de Informações em Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="c006c-116">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c006c-117">As políticas do livro de endereços fornecem apenas uma separação virtual dos usuários da perspectiva do diretório.</span><span class="sxs-lookup"><span data-stu-id="c006c-117">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="c006c-118">Também é importante observar que quaisquer dados de usuário que já foram armazenados em cache, antes da aplicação de políticas de livro de endereços novas ou atualizadas, permanecerão disponíveis para os usuários por até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c006c-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="c006c-119">Ativar a pesquisa de diretório com escopo</span><span class="sxs-lookup"><span data-stu-id="c006c-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="c006c-120">Use políticas de Barreira de Informações para configurar sua organização em subgrupos virtuais.</span><span class="sxs-lookup"><span data-stu-id="c006c-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="c006c-121">Para obter mais informações, consulte [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span><span class="sxs-lookup"><span data-stu-id="c006c-121">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="c006c-122">No centro Microsoft Teams de administração, selecione **Configurações** em toda a  >  **organização Teams configurações**.</span><span class="sxs-lookup"><span data-stu-id="c006c-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="c006c-123">Em **Pesquisa**, ao lado da pesquisa de diretório escopo no Teams usando uma política de Exchange de **endereços (ABP),** a opção **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="c006c-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Pesquisa de diretório com escopo no Microsoft Teams de administração](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="c006c-125">Essa alteração pode levar algumas horas para ser replicada.</span><span class="sxs-lookup"><span data-stu-id="c006c-125">This change can take a few hours to replicate.</span></span>
