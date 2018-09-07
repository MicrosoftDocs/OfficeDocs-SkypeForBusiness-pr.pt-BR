---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams, como arquivos de bate-papo provados são armazenados e a relação entre equipe, canal e biblioteca de documentos.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ef9773ce43ce395cd27982eeb91d1c6081a88d4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861187"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="939bc-103">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="939bc-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="939bc-104">Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe.</span><span class="sxs-lookup"><span data-stu-id="939bc-104">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="939bc-105">Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="939bc-105">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="939bc-106">Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do remetente e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="939bc-106">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="939bc-107">Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365.</span><span class="sxs-lookup"><span data-stu-id="939bc-107">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="939bc-108">Compartilhamento de arquivos continuarão a funcionar no canais, mas os usuários não poderão compartilhar arquivos em bate-papos sem OneDrive para armazenamento de negócios no Office 365.</span><span class="sxs-lookup"><span data-stu-id="939bc-108">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="939bc-109">Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.</span><span class="sxs-lookup"><span data-stu-id="939bc-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="939bc-110">Integração com o Sharepoint local não é suportada for Microsoft Teams neste momento.</span><span class="sxs-lookup"><span data-stu-id="939bc-110">Integration with Sharepoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="939bc-111">A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="939bc-111">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="939bc-112">É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes.</span><span class="sxs-lookup"><span data-stu-id="939bc-112">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="939bc-113">Todos os canais, inclusive o canal **Geral** (o canal padrão de cada equipe), têm uma pasta em **Documentos Compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="939bc-113">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama das pastas de documentos selecionados no SharePoint Online para uma equipe e seus canais no Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="939bc-115">No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros.</span><span class="sxs-lookup"><span data-stu-id="939bc-115">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="939bc-116">Recebemos o feedback de que isso seria interessante e estamos considerando a ideia.</span><span class="sxs-lookup"><span data-stu-id="939bc-116">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="939bc-117">Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="939bc-117">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="939bc-118">Para adicionar uma guia para a sua equipe que links para um SharePoint existente de site ou biblioteca de documentos no seu SharePoint existente:</span><span class="sxs-lookup"><span data-stu-id="939bc-118">To add a tab to your team that links to an existing SharePoint site or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="939bc-119">Selecione o sinal de adição ao lado de guias.</span><span class="sxs-lookup"><span data-stu-id="939bc-119">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="939bc-120">Selecione o **site**.</span><span class="sxs-lookup"><span data-stu-id="939bc-120">Select **Website**.</span></span>
> 3. <span data-ttu-id="939bc-121">Digite um nome e digite a URL do seu SharePoint site ou biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="939bc-121">Type a name and enter the URL of your SharePoint site or document library.</span></span>

<span data-ttu-id="939bc-122">Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="939bc-122">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama da pasta do OneDrive, nomeada como Arquivos de Bate-papo do Microsoft Teams para o bate-papo de cada usuário.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
