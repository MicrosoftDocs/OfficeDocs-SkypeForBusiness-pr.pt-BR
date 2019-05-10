---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams, como arquivos de bate-papo provados são armazenados e a relação entre equipe, canal e biblioteca de documentos.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827736"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="e0d9b-103">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0d9b-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="e0d9b-104">Assista a sessão a seguir para saber como equipes interage com o Windows Azure Active Directory (AAD), grupos do Office 365, Exchange, SharePoint e OneDrive for Business: [Fundamentos das equipes da Microsoft](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="e0d9b-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="e0d9b-105">Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="e0d9b-106">Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="e0d9b-107">Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do remetente e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="e0d9b-108">Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="e0d9b-109">Compartilhamento de arquivos continuarão a funcionar no canais, mas os usuários não poderão compartilhar arquivos em bate-papos sem OneDrive para armazenamento de negócios no Office 365.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="e0d9b-110">Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="e0d9b-111">Integração com o SharePoint local não é suportada for Microsoft Teams neste momento.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="e0d9b-112">A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="e0d9b-113">É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="e0d9b-114">Todos os canais, inclusive o canal **Geral** (o canal padrão de cada equipe), têm uma pasta em **Documentos Compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama das pastas de documentos selecionados no SharePoint Online para uma equipe e seus canais no Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="e0d9b-116">No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="e0d9b-117">Recebemos o feedback de que isso seria interessante e estamos considerando a ideia.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="e0d9b-118">Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="e0d9b-119">Para adicionar uma guia para a sua equipe que vincula a uma página existente do site do SharePoint ou em sua biblioteca de documentos do SharePoint existente:</span><span class="sxs-lookup"><span data-stu-id="e0d9b-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="e0d9b-120">Selecione o sinal de adição ao lado de guias.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="e0d9b-121">Selecione **SharePoint** para uma página existente do site do SharePoint ou **Biblioteca de documentos** para uma biblioteca de documento existente.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="e0d9b-122">Selecione a biblioteca apropriada de página ou documento.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="e0d9b-123">Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama da pasta do OneDrive, nomeada como Arquivos de Bate-papo do Microsoft Teams para o bate-papo de cada usuário.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="e0d9b-125">Guia de arquivos de canal</span><span class="sxs-lookup"><span data-stu-id="e0d9b-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="e0d9b-126">Na guia **arquivos** em equipes parecida com o modo de exibição de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="e0d9b-127">Na guia **arquivos** , os usuários podem:</span><span class="sxs-lookup"><span data-stu-id="e0d9b-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="e0d9b-128">Consulte as opções adicionais no menu **novo** arquivo.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="e0d9b-129">Sincronizar arquivos para sua unidade local.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="e0d9b-130">No menu **Todos os documentos** , alterne do modo de exibição de **lista** para **lista compacta** ao modo de exibição **lado a lado** .</span><span class="sxs-lookup"><span data-stu-id="e0d9b-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="e0d9b-131">Identifica os arquivos que precisam de atenção ou têm malware.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="e0d9b-132">Ver imediatamente se um arquivo é somente leitura ou check-out.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="e0d9b-133">Check-out e check-in de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-133">Check out and check in files.</span></span>
- <span data-ttu-id="e0d9b-134">Fixar, Desafixar e alterar a ordem de classificação dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="e0d9b-135">Identificar quais arquivos precisam ser metadados</span><span class="sxs-lookup"><span data-stu-id="e0d9b-135">Identify which files need metadata</span></span>
- <span data-ttu-id="e0d9b-136">Escolha uma das muitas mais opções de filtro.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="e0d9b-137">Arquivos de grupo com base nos títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-137">Group files based on column headings.</span></span>
- <span data-ttu-id="e0d9b-138">Modificar configurações de coluna (mover para a esquerda ou direita, ocultar) e a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="e0d9b-139">Configuração de tipo de link padrão</span><span class="sxs-lookup"><span data-stu-id="e0d9b-139">Default link type setting</span></span>

<span data-ttu-id="e0d9b-140">SharePoint e OneDrive têm uma definição de administração para especificar o tipo de link padrão para links que são criados para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="e0d9b-141">As equipes está adotando essa mesma abordagem reutilizando as configurações que o administrador define para SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="e0d9b-142">Para obter mais detalhes sobre essa abordagem são descritos na [alterar o tipo de link padrão quando os usuários obtenham links para compartilhamento](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="e0d9b-143">Mais informações</span><span class="sxs-lookup"><span data-stu-id="e0d9b-143">More information</span></span>

<span data-ttu-id="e0d9b-144">Para obter mais informações sobre como o SharePoint funciona com equipes, consulte [equipes e SharePoint: melhores juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="e0d9b-145">Para saber mais sobre a experiência de convidado em equipes, leia [o que a experiência de convidado é como](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

