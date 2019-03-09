---
title: Usar a pesquisa de diretório no escopo do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar a pesquisa de diretório com escopo Teams da Microsoft para fornecer exibições personalizadas do diretório.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e21cc33ab24dc14bd56f15146180ef90afdde7de
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494153"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="a7212-103">Usar a pesquisa de diretório no escopo do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a7212-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="a7212-104">A pesquisa de diretório com escopo Teams Microsoft permite que as organizações a criar limites virtuais que controlam como os usuários podem localizar e se comunicar com outros usuários em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="a7212-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="a7212-105">Teams Microsoft permite que as organizações fornecem exibições personalizadas do diretório para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a7212-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="a7212-106">Microsoft Teams usa [políticas de catálogo de endereços do Exchange](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) para oferecer suporte a esses modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="a7212-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) to support these custom views.</span></span> <span data-ttu-id="a7212-107">Depois que as diretivas estão habilitadas, os resultados retornados pelo procura por outros usuários (por exemplo, para iniciar um chat ou adicionar membros a uma equipe) terá o escopo de acordo com as diretivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="a7212-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="a7212-108">Os usuários não poderão pesquisar ou descobrir equipes quando com escopo de pesquisa está em vigor.</span><span class="sxs-lookup"><span data-stu-id="a7212-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="a7212-109">Quando você deve usar as pesquisas de diretório com escopo?</span><span class="sxs-lookup"><span data-stu-id="a7212-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="a7212-110">Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="a7212-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="a7212-111">Por exemplo, convém usar a pesquisa de diretório com escopo nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="a7212-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="a7212-112">Sua organização tem várias empresas dentro no locatário que você deseja manter separadas.</span><span class="sxs-lookup"><span data-stu-id="a7212-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="a7212-113">Sua escola quer limitar os chats entre professores e alunos.</span><span class="sxs-lookup"><span data-stu-id="a7212-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="a7212-114">Você pode aprender mais sobre como as políticas de catálogo de endereços podem ser usadas [aqui](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="a7212-114">You can learn more about how address book policies can be used [here](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7212-115">Políticas de catálogo de endereços fornecem apenas uma virtual separação de usuários da perspectiva de diretório.</span><span class="sxs-lookup"><span data-stu-id="a7212-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="a7212-116">Os usuários ainda podem iniciar a comunicação com outras pessoas, fornecendo endereços de email completo.</span><span class="sxs-lookup"><span data-stu-id="a7212-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="a7212-117">Também é importante observar que quaisquer dados de usuário que tinham já foram armazenados em cache, antes da aplicação de políticas de catálogo de endereços novos ou atualizados, ficará disponíveis para os usuários por até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="a7212-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="a7212-118">Habilitar a pesquisa de diretório com escopo</span><span class="sxs-lookup"><span data-stu-id="a7212-118">Enable scoped directory search</span></span>

1.  <span data-ttu-id="a7212-119">Use políticas de catálogo de endereços para configurar sua organização em subgrupos virtuais.</span><span class="sxs-lookup"><span data-stu-id="a7212-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="a7212-120">Para obter mais informações, consulte [procedimentos para políticas de catálogo de endereços](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="a7212-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span></span>

2.  <span data-ttu-id="a7212-121">Entrar no Centro de administração do Microsoft 365, selecione **centrais de Admin**e selecione **equipes & Skype**.</span><span class="sxs-lookup"><span data-stu-id="a7212-121">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="a7212-122">No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização** > **configurações de equipes**.</span><span class="sxs-lookup"><span data-stu-id="a7212-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="a7212-123">Em **pesquisa**, ao lado de **pesquisa de diretório do escopo em equipes usando uma política de catálogo de endereços do Exchange (APB)**, ative a alternância **em**.</span><span class="sxs-lookup"><span data-stu-id="a7212-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![Escopo de pesquisa de diretório no Centro de administração do Microsoft Teams](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="a7212-125">Configurações híbridas (equipes com Exchange local) não suportam o modo de pesquisa com escopo.</span><span class="sxs-lookup"><span data-stu-id="a7212-125">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

