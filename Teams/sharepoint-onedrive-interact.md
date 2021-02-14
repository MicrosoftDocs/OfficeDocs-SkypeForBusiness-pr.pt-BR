---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Interação do SharePoint Online & OneDrive for Business com o Teams; armazenamento de arquivos de chat particular & interação entre equipe, canal padrão, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ff18a0645f81d1892e246ee7432d58a1c728f3ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757776"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="c13c2-103">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c13c2-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="c13c2-104">Assista à seguinte sessão para saber como as equipes interagem com o Azure Active Directory (AAD), o Microsoft 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [Fundamentos do Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="c13c2-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="c13c2-105">Cada equipe no Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal padrão em uma equipe obtém uma pasta dentro da biblioteca de documentos do site de equipe padrão.</span><span class="sxs-lookup"><span data-stu-id="c13c2-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="c13c2-106">Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="c13c2-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="c13c2-107">Para ver o impacto da alteração de um endereço de site no SharePoint, leia [Alterar um endereço de site.](https://docs.microsoft.com/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="c13c2-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="c13c2-108">Este artigo se aplica somente aos canais padrão.</span><span class="sxs-lookup"><span data-stu-id="c13c2-108">This article applies only to standard channels.</span></span> <span data-ttu-id="c13c2-109">A arquitetura para canais privados é diferente dos canais padrão.</span><span class="sxs-lookup"><span data-stu-id="c13c2-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="c13c2-110">Cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai.</span><span class="sxs-lookup"><span data-stu-id="c13c2-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="c13c2-111">Para saber mais, consulte [Canais privados no Microsoft Teams.](private-channels.md)</span><span class="sxs-lookup"><span data-stu-id="c13c2-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="c13c2-112">Arquivos de chat particular são armazenados na pasta do OneDrive for Business do remetente, e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c13c2-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="c13c2-113">Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="c13c2-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c13c2-114">O compartilhamento de arquivos continuará a funcionar em canais padrão, mas os usuários não poderão compartilhar arquivos em chats sem o armazenamento do OneDrive for Business no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="c13c2-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="c13c2-115">Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.</span><span class="sxs-lookup"><span data-stu-id="c13c2-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="c13c2-116">A integração com o SharePoint local não tem suporte no momento para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c13c2-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="c13c2-117">A seguir, é possível ver o exemplo de relações entre equipe, canal padrão e biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c13c2-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="c13c2-118">É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes.</span><span class="sxs-lookup"><span data-stu-id="c13c2-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="c13c2-119">Cada canal padrão, incluindo **o canal Geral** (o canal padrão para cada equipe) tem uma pasta em Documentos **Compartilhados.**</span><span class="sxs-lookup"><span data-stu-id="c13c2-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama de pastas documentos compartilhados no SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="c13c2-121">No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros.</span><span class="sxs-lookup"><span data-stu-id="c13c2-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="c13c2-122">Recebemos o feedback de que isso seria interessante e estamos considerando a ideia.</span><span class="sxs-lookup"><span data-stu-id="c13c2-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="c13c2-123">Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="c13c2-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="c13c2-124">Para adicionar uma guia à sua equipe que vincula a uma página de site existente do SharePoint ou à biblioteca de documentos existente do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c13c2-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="c13c2-125">Selecione o sinal de mais ao lado das guias.</span><span class="sxs-lookup"><span data-stu-id="c13c2-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="c13c2-126">Selecione o **SharePoint para** uma página de site existente do SharePoint **ou** Biblioteca de Documentos para uma biblioteca de documentos existente.</span><span class="sxs-lookup"><span data-stu-id="c13c2-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="c13c2-127">Selecione a página ou biblioteca de documentos apropriada.</span><span class="sxs-lookup"><span data-stu-id="c13c2-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="c13c2-128">Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="c13c2-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama da pasta do OneDrive chamada Arquivos de Chat do Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="c13c2-130">Observe que, para equipes públicas, o site de equipe do SharePoint é provisionado com acesso "Todos exceto usuários externos".</span><span class="sxs-lookup"><span data-stu-id="c13c2-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="c13c2-131">A equipe pública não é exibida no Teams para pessoas que não são membros dessa equipe.</span><span class="sxs-lookup"><span data-stu-id="c13c2-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="c13c2-132">No entanto, eles podem acessar o conteúdo no site de equipe do SharePoint usando a URL do site de equipe do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c13c2-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="c13c2-133">Guia Arquivos de Canal</span><span class="sxs-lookup"><span data-stu-id="c13c2-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="c13c2-134">A **guia** Arquivos no Teams se assemelha muito ao exibição de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c13c2-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="c13c2-135">Na guia **Arquivos,** os usuários podem:</span><span class="sxs-lookup"><span data-stu-id="c13c2-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="c13c2-136">Veja opções adicionais no menu **Novo** arquivo.</span><span class="sxs-lookup"><span data-stu-id="c13c2-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="c13c2-137">Sincronize arquivos com a unidade local.</span><span class="sxs-lookup"><span data-stu-id="c13c2-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="c13c2-138">No menu **Todos os Documentos,** alternar do **exibição** lista para **a lista Compacta** para o **exibição Blocos.**</span><span class="sxs-lookup"><span data-stu-id="c13c2-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="c13c2-139">Identifique arquivos que precisam de atenção ou que tenham malware.</span><span class="sxs-lookup"><span data-stu-id="c13c2-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="c13c2-140">Veja imediatamente se um arquivo é somente leitura ou check-out.</span><span class="sxs-lookup"><span data-stu-id="c13c2-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="c13c2-141">Fazer check-out e check-in de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c13c2-141">Check out and check in files.</span></span>
- <span data-ttu-id="c13c2-142">Fixe,pine e altere a ordem de classificação dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="c13c2-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="c13c2-143">Identificar quais arquivos precisam de metadados</span><span class="sxs-lookup"><span data-stu-id="c13c2-143">Identify which files need metadata</span></span>
- <span data-ttu-id="c13c2-144">Escolha entre muitas outras opções de filtro.</span><span class="sxs-lookup"><span data-stu-id="c13c2-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="c13c2-145">Agrupar arquivos com base nos títulos de colunas.</span><span class="sxs-lookup"><span data-stu-id="c13c2-145">Group files based on column headings.</span></span>
- <span data-ttu-id="c13c2-146">Modifique as configurações de coluna (mover para a esquerda ou para a direita, ocultar) e a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="c13c2-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="c13c2-147">Configuração de tipo de link padrão</span><span class="sxs-lookup"><span data-stu-id="c13c2-147">Default link type setting</span></span>

<span data-ttu-id="c13c2-148">O SharePoint e o OneDrive têm uma configuração de administrador para especificar o tipo de link padrão para links criados para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="c13c2-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="c13c2-149">O Teams está adotando essa mesma abordagem reutilando as configurações que o administrador define para o SharePoint e o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c13c2-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="c13c2-150">Mais detalhes sobre essa abordagem são descritos em Alterar o tipo de link padrão [quando os usuários receberem links para compartilhamento.](https://docs.microsoft.com/sharepoint/change-default-sharing-link)</span><span class="sxs-lookup"><span data-stu-id="c13c2-150">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="c13c2-151">Mais informações</span><span class="sxs-lookup"><span data-stu-id="c13c2-151">More information</span></span>

<span data-ttu-id="c13c2-152">Para saber mais sobre como o SharePoint funciona com o Teams, confira o SharePoint e o [Teams: melhor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="c13c2-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="c13c2-153">Para saber mais sobre a experiência de convidado no Teams, leia como é a [experiência do convidado.](guest-experience.md)</span><span class="sxs-lookup"><span data-stu-id="c13c2-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

