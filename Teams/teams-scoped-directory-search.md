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
description: Saiba como usar a pesquisa de diretório com escopo do Microsoft Teams para fornecer exibições personalizadas do diretório.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779925"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="ccfa0-103">Usar a pesquisa de diretório no escopo do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ccfa0-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="ccfa0-104">A pesquisa de diretório com escopo do Microsoft Teams permite que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="ccfa0-105">O Microsoft Teams permite que as organizações forneçam exibições personalizadas do diretório para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="ccfa0-106">O Microsoft Teams usa [políticas de Barreira de Informações](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) para dar suporte a essas exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="ccfa0-107">Depois que as políticas são habilitadas, os resultados retornados pelas pesquisas de outros usuários (por exemplo, para iniciar um chat ou adicionar membros a uma equipe) serão analisados de acordo com as políticas configuradas.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="ccfa0-108">Os usuários não poderão pesquisar ou descobrir equipes quando a pesquisa com escopo estiver em vigor.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="ccfa0-109">Em ambientes híbridos do Exchange, esse recurso só funciona com caixas de correio do Exchange Online, e não com caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="ccfa0-110">Quando você deve usar pesquisas de diretório com escopo?</span><span class="sxs-lookup"><span data-stu-id="ccfa0-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="ccfa0-111">Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política de livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="ccfa0-112">Por exemplo, talvez você queira usar a pesquisa de diretório com escopo nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="ccfa0-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="ccfa0-113">Sua organização tem várias empresas dentro no locatário que você deseja manter separadas.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="ccfa0-114">Sua escola quer limitar os chats entre professores e alunos.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="ccfa0-115">Para saber como usar políticas de livro de endereços, leia as políticas de Barreira [de Informações no Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="ccfa0-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccfa0-116">As políticas do livro de endereços fornecem apenas uma separação virtual dos usuários da perspectiva do diretório.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="ccfa0-117">Também é importante observar que todos os dados do usuário que já foram armazenados em cache, antes da aplicação de políticas de livro de endereços novas ou atualizadas, permanecerão disponíveis para os usuários por até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="ccfa0-118">Ativar a pesquisa de diretório com escopo</span><span class="sxs-lookup"><span data-stu-id="ccfa0-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="ccfa0-119">Use políticas de Barreira de Informações para configurar sua organização em subgrupos virtuais.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="ccfa0-120">Para obter mais informações, consulte [Definir políticas de Barreira de Informações.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="ccfa0-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="ccfa0-121">No centro de administração do Microsoft Teams, selecione **configurações do** Teams em toda a  >  **organização.**</span><span class="sxs-lookup"><span data-stu-id="ccfa0-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="ccfa0-122">Em **Pesquisa**, ao lado da pesquisa de diretório de escopo no Teams usando uma política de livro de endereços **do Exchange (ABP),** a opção **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="ccfa0-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Pesquisa de diretório com escopo no centro de administração do Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="ccfa0-124">Essa alteração pode levar algumas horas para ser replicada.</span><span class="sxs-lookup"><span data-stu-id="ccfa0-124">This change can take a few hours to replicate.</span></span>
