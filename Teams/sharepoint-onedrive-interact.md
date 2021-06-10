---
title: Como SharePoint e OneDrive interagir com Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive interação com Teams; armazenamento de arquivos de chat & interação entre equipe, canal padrão, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855950"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="4e5b1-103">Como SharePoint e OneDrive interagir com Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e5b1-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="4e5b1-104">Assista à sessão a seguir para saber como o Teams interage com Azure Active Directory (AAD), grupos Microsoft 365, Exchange, SharePoint e OneDrive: [fundamentos do Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="4e5b1-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="4e5b1-105">Cada equipe no Microsoft Teams tem um site de equipe no SharePoint, e cada canal padrão em uma equipe obtém uma pasta dentro da biblioteca de documentos de site de equipe padrão.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="4e5b1-106">Cada [canal privado](private-channels.md) obtém seu próprio site SharePoint site.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="4e5b1-107">Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="4e5b1-108">Para ver o impacto da alteração de um endereço de site em SharePoint, leia [Alterar um endereço de site](/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="4e5b1-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="4e5b1-109">Os arquivos de chat privados são armazenados na pasta de OneDrive do remetente e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="4e5b1-110">Se os usuários não são atribuídos SharePoint licenças, eles não têm OneDrive armazenamento no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="4e5b1-111">O compartilhamento de arquivos funciona em canais padrão, mas os usuários não poderão compartilhar arquivos em chats sem OneDrive armazenamento no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="4e5b1-112">Ao armazenar os arquivos na biblioteca SharePoint de documentos e OneDrive, todas as regras de conformidade configuradas no nível da organização serão seguidas.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="4e5b1-113">A integração com SharePoint Server não tem suporte para Teams.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="4e5b1-114">A seguir está o exemplo de relações entre equipe, canal padrão e biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="4e5b1-115">É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="4e5b1-116">Cada canal padrão, incluindo **o canal Geral** (o canal padrão para cada equipe) tem uma pasta em Documentos **Compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama de pastas documentos compartilhados em SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="4e5b1-118">O padrão SharePoint site e biblioteca de documentos não podem ser substituídos por outro.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="4e5b1-119">Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama da pasta OneDrive chamada Microsoft Teams Chat Files](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="4e5b1-121">Observe que, para equipes públicas, o site SharePoint equipe é provisionado com acesso "Todos, exceto usuários externos".</span><span class="sxs-lookup"><span data-stu-id="4e5b1-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="4e5b1-122">A equipe pública não é exibida no Teams para pessoas que não são membros dessa equipe.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="4e5b1-123">No entanto, eles podem acessar o conteúdo no site SharePoint equipe usando a URL do site SharePoint equipe.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="4e5b1-124">Guia Arquivos de Canal</span><span class="sxs-lookup"><span data-stu-id="4e5b1-124">Channel Files tab</span></span>

<span data-ttu-id="4e5b1-125">A **guia Arquivos** no Teams se parece muito com o SharePoint de documentos.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="4e5b1-126">Na guia **Arquivos,** os usuários podem:</span><span class="sxs-lookup"><span data-stu-id="4e5b1-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="4e5b1-127">Consulte opções adicionais no menu **Novo** arquivo.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="4e5b1-128">Sincronizar arquivos com a unidade local.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="4e5b1-129">No menu **Todos os Documentos,** alternar do **exibição Lista** para a lista **Compacta** para **o exibição Blocos.**</span><span class="sxs-lookup"><span data-stu-id="4e5b1-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="4e5b1-130">Identifique arquivos que precisam de atenção ou que tenham malware.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="4e5b1-131">Consulte imediatamente se um arquivo é somente leitura ou check-out.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="4e5b1-132">Fazer check-out e fazer check-in de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-132">Check out and check in files.</span></span>
- <span data-ttu-id="4e5b1-133">Fixar, desempinar e alterar a ordem de classificação de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="4e5b1-134">Identificar quais arquivos precisam de metadados</span><span class="sxs-lookup"><span data-stu-id="4e5b1-134">Identify which files need metadata</span></span>
- <span data-ttu-id="4e5b1-135">Escolha entre muitas outras opções de filtro.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="4e5b1-136">Arquivos de grupo com base em títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-136">Group files based on column headings.</span></span>
- <span data-ttu-id="4e5b1-137">Modificar configurações de coluna (mover para a esquerda ou para a direita, ocultar) e largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="4e5b1-138">Configuração de tipo de link padrão</span><span class="sxs-lookup"><span data-stu-id="4e5b1-138">Default link type setting</span></span>

<span data-ttu-id="4e5b1-139">O tipo de link de compartilhamento mostrado por padrão quando um usuário compartilhou um arquivo é definido no SharePoint de administração.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="4e5b1-140">Consulte [Alterar o tipo de link padrão quando os usuários receberem links para compartilhamento](/sharepoint/change-default-sharing-link) para obter informações.</span><span class="sxs-lookup"><span data-stu-id="4e5b1-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e5b1-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4e5b1-141">Related topics</span></span>

<span data-ttu-id="4e5b1-142">[SharePoint e Teams: melhor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="4e5b1-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="4e5b1-143">Como é a experiência do convidado</span><span class="sxs-lookup"><span data-stu-id="4e5b1-143">What the guest experience is like</span></span>](guest-experience.md)