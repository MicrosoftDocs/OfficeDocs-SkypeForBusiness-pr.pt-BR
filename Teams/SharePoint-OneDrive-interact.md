---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/12/2018
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
ms.openlocfilehash: 169008f7af8f52be60c7f15d7a4613f77ed161df
ms.sourcegitcommit: ff100b32fa92fc878f1404dace266d956262c24d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2019
ms.locfileid: "30720319"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="37723-103">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37723-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

> [!Tip]
> <span data-ttu-id="37723-104">Assista a sessão a seguir para saber como equipes interage com o Windows Azure Active Directory (AAD), grupos do Office 365, Exchange, SharePoint e OneDrive for Business: [Fundamentos das equipes da Microsoft](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="37723-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="37723-105">Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe.</span><span class="sxs-lookup"><span data-stu-id="37723-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="37723-106">Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="37723-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="37723-107">Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do remetente e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="37723-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="37723-108">Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365.</span><span class="sxs-lookup"><span data-stu-id="37723-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="37723-109">Compartilhamento de arquivos continuarão a funcionar no canais, mas os usuários não poderão compartilhar arquivos em bate-papos sem OneDrive para armazenamento de negócios no Office 365.</span><span class="sxs-lookup"><span data-stu-id="37723-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="37723-110">Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.</span><span class="sxs-lookup"><span data-stu-id="37723-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="37723-111">Integração com o Sharepoint local não é suportada for Microsoft Teams neste momento.</span><span class="sxs-lookup"><span data-stu-id="37723-111">Integration with Sharepoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="37723-112">A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="37723-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="37723-113">É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes.</span><span class="sxs-lookup"><span data-stu-id="37723-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="37723-114">Todos os canais, inclusive o canal **Geral** (o canal padrão de cada equipe), têm uma pasta em **Documentos Compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="37723-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama das pastas de documentos selecionados no SharePoint Online para uma equipe e seus canais no Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="37723-116">No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros.</span><span class="sxs-lookup"><span data-stu-id="37723-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="37723-117">Recebemos o feedback de que isso seria interessante e estamos considerando a ideia.</span><span class="sxs-lookup"><span data-stu-id="37723-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="37723-118">Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="37723-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="37723-119">Para adicionar uma guia para a sua equipe que vincula a uma página existente do site do SharePoint ou em sua biblioteca de documentos do SharePoint existente:</span><span class="sxs-lookup"><span data-stu-id="37723-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="37723-120">Selecione o sinal de adição ao lado de guias.</span><span class="sxs-lookup"><span data-stu-id="37723-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="37723-121">Selecione **SharePoint** para uma página existente do site do SharePoint ou **Biblioteca de documentos** para uma biblioteca de documento existente.</span><span class="sxs-lookup"><span data-stu-id="37723-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="37723-122">Selecione a biblioteca apropriada de página ou documento.</span><span class="sxs-lookup"><span data-stu-id="37723-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="37723-123">Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="37723-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama da pasta do OneDrive, nomeada como Arquivos de Bate-papo do Microsoft Teams para o bate-papo de cada usuário.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<a name="more-information"></a><span data-ttu-id="37723-125">Mais informações</span><span class="sxs-lookup"><span data-stu-id="37723-125">More information</span></span>
----------------

<span data-ttu-id="37723-126">Para obter mais informações sobre como o SharePoint funciona com equipes, consulte [equipes e SharePoint: melhores juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="37723-126">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="37723-127">Para saber mais sobre a experiência de convidado em equipes, leia [o que a experiência de convidado é como](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="37723-127">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

