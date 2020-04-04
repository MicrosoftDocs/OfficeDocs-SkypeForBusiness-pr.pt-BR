---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & interação do OneDrive for Business com o Teams; armazenamento de arquivos de chat particular & interação entre a equipe, o canal padrão & a biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fd34bf368667fcfa5776de40cad0d1444440805a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137251"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="2f625-103">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f625-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="2f625-104">Assista à sessão a seguir para saber como as equipes interagem com o Azure Active Directory (AAD), o Office 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [bases do Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="2f625-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="2f625-105">Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal padrão em uma equipe Obtém uma pasta dentro da biblioteca de documentos padrão do site de equipe.</span><span class="sxs-lookup"><span data-stu-id="2f625-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="2f625-106">Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="2f625-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="2f625-107">Para ver o impacto da alteração de um endereço de site no SharePoint, leia [alterar um endereço de site](https://docs.microsoft.com/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="2f625-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="2f625-108">Este artigo se aplica somente a canais padrão.</span><span class="sxs-lookup"><span data-stu-id="2f625-108">This article applies only to standard channels.</span></span> <span data-ttu-id="2f625-109">A arquitetura para canais privados é diferente dos canais padrão.</span><span class="sxs-lookup"><span data-stu-id="2f625-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="2f625-110">Cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai.</span><span class="sxs-lookup"><span data-stu-id="2f625-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="2f625-111">Para saber mais, confira [canais privados no Microsoft Teams](private-channels.md).</span><span class="sxs-lookup"><span data-stu-id="2f625-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="2f625-112">Os arquivos de chat particulares são armazenados na pasta do OneDrive for Business do remetente, e as permissões são automaticamente concedidas a todos os participantes como parte do processo de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2f625-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="2f625-113">Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f625-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="2f625-114">O compartilhamento de arquivos continuará a funcionar em canais padrão, mas os usuários não poderão compartilhar arquivos em chats sem o armazenamento do OneDrive for Business no Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f625-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="2f625-115">Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.</span><span class="sxs-lookup"><span data-stu-id="2f625-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="2f625-116">A integração com o SharePoint local não é compatível com o Microsoft Teams no momento.</span><span class="sxs-lookup"><span data-stu-id="2f625-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="2f625-117">Veja a seguir o exemplo de relações entre a equipe, o canal padrão e a biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="2f625-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="2f625-118">É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes.</span><span class="sxs-lookup"><span data-stu-id="2f625-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="2f625-119">Cada canal padrão, incluindo o canal **geral** (o canal padrão de cada equipe) tem uma pasta em **documentos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="2f625-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama de pastas de documentos compartilhados no SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="2f625-121">No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros.</span><span class="sxs-lookup"><span data-stu-id="2f625-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="2f625-122">Recebemos o feedback de que isso seria interessante e estamos considerando a ideia.</span><span class="sxs-lookup"><span data-stu-id="2f625-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="2f625-123">Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="2f625-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="2f625-124">Para adicionar uma guia à sua equipe que vincula a uma página de site do SharePoint existente ou à biblioteca de documentos do SharePoint existente:</span><span class="sxs-lookup"><span data-stu-id="2f625-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="2f625-125">Selecione o sinal de adição ao lado das guias.</span><span class="sxs-lookup"><span data-stu-id="2f625-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="2f625-126">Selecione o **SharePoint** para uma página de site ou uma **biblioteca de documentos** do SharePoint existente para uma biblioteca de documentos existente.</span><span class="sxs-lookup"><span data-stu-id="2f625-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="2f625-127">Selecione a página ou biblioteca de documentos apropriada.</span><span class="sxs-lookup"><span data-stu-id="2f625-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="2f625-128">Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="2f625-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama da pasta OneDrive chamado arquivos de chat do Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="2f625-130">Guia arquivos do canal</span><span class="sxs-lookup"><span data-stu-id="2f625-130">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="2f625-131">A guia **arquivos** em equipes é parecida com o modo de exibição documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2f625-131">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="2f625-132">Na guia **arquivos** , os usuários podem:</span><span class="sxs-lookup"><span data-stu-id="2f625-132">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="2f625-133">Veja opções adicionais no menu **novo** arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f625-133">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="2f625-134">Sincronize arquivos com a unidade local.</span><span class="sxs-lookup"><span data-stu-id="2f625-134">Sync files to their local drive.</span></span>
- <span data-ttu-id="2f625-135">No menu **todos os documentos** , alternar do modo de exibição de **lista** para a **lista compacta** para o modo de exibição de **blocos** .</span><span class="sxs-lookup"><span data-stu-id="2f625-135">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="2f625-136">Identifique os arquivos que precisam de atenção ou de malware.</span><span class="sxs-lookup"><span data-stu-id="2f625-136">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="2f625-137">Veja imediatamente se um arquivo é somente leitura ou com check-out.</span><span class="sxs-lookup"><span data-stu-id="2f625-137">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="2f625-138">Fazer check-out e check-in de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2f625-138">Check out and check in files.</span></span>
- <span data-ttu-id="2f625-139">Fixar, Desafixar e alterar a ordem de classificação dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="2f625-139">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="2f625-140">Identificar quais arquivos precisam de metadados</span><span class="sxs-lookup"><span data-stu-id="2f625-140">Identify which files need metadata</span></span>
- <span data-ttu-id="2f625-141">Escolha entre várias opções de filtro.</span><span class="sxs-lookup"><span data-stu-id="2f625-141">Choose from many more filter options.</span></span>
- <span data-ttu-id="2f625-142">Agrupar arquivos com base em títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="2f625-142">Group files based on column headings.</span></span>
- <span data-ttu-id="2f625-143">Modifique as configurações de coluna (mover para a esquerda ou direita, ocultar) e largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="2f625-143">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="2f625-144">Configuração do tipo de link padrão</span><span class="sxs-lookup"><span data-stu-id="2f625-144">Default link type setting</span></span>

<span data-ttu-id="2f625-145">O SharePoint e o OneDrive têm uma configuração de administrador para especificar o tipo de link padrão para links que são criados para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f625-145">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="2f625-146">O Microsoft Teams está adotando essa mesma abordagem reutilizando as configurações que o administrador define para o SharePoint e o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2f625-146">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="2f625-147">Mais detalhes sobre essa abordagem são descritos em [alterar o tipo de link padrão quando os usuários recebem links para compartilhamento](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="2f625-147">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="2f625-148">Mais informações</span><span class="sxs-lookup"><span data-stu-id="2f625-148">More information</span></span>

<span data-ttu-id="2f625-149">Para obter mais informações sobre como o SharePoint funciona com o Microsoft Teams, consulte [SharePoint e Teams: melhor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="2f625-149">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="2f625-150">Para saber mais sobre a experiência de convidado no Microsoft Teams, leia [o que a experiência de convidado é curtir](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="2f625-150">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

