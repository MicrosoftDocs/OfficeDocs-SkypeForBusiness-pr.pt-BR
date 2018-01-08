---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams, como arquivos de bate-papo provados são armazenados e a relação entre equipe, canal e biblioteca de documentos."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: b7d9ffad23c8f26d7d95c3f31df4ff0307517179
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="27f59-103">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27f59-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="27f59-104">Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe.</span><span class="sxs-lookup"><span data-stu-id="27f59-104">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="27f59-105">Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="27f59-105">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="27f59-106">Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do **remetente** e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="27f59-106">Private chat files are stored in the **sender’s** OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="27f59-107">Se o SharePoint Online não está habilitado em seu locatário, os usuários do Microsoft Teams não podem compartilhar arquivos em equipes.</span><span class="sxs-lookup"><span data-stu-id="27f59-107">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users cannot always share files in teams.</span></span> <span data-ttu-id="27f59-108">Os usuários no chat privado também não podem compartilhar arquivos, pois o OneDrive for Business (que é vinculado à licença do SharePoint) é necessário para essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="27f59-108">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="27f59-109">Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.</span><span class="sxs-lookup"><span data-stu-id="27f59-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="27f59-110">A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="27f59-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="27f59-111">É criado um site SharePoint para cada equipe e a pasta *Documentos compartilhados* é a pasta padrão criada para cada uma das equipes.</span><span class="sxs-lookup"><span data-stu-id="27f59-111">For every team, a SharePoint site is created, and the *Shared Documents* folder is the default folder created for the team.</span></span> <span data-ttu-id="27f59-112">Todos os canais, inclusive o canal **Geral**, o canal padrão de cada equipe, têm uma pasta dentro da pasta *Documentos compartilhados*.</span><span class="sxs-lookup"><span data-stu-id="27f59-112">Each channel, including the **General** channel, the default channel for each team, has a folder under the *Shared Documents* folder.</span></span>

![Diagrama das pastas de documentos selecionados no SharePoint Online para uma equipe e seus canais no Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="27f59-114">Para cada usuário, a pasta *Arquivos de bate-papo do Microsoft Teams* do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="27f59-114">For every user, the OneDrive folder *Microsoft Teams Chat Files* is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama da pasta do OneDrive, nomeada como Arquivos de Bate-papo do Microsoft Teams para o bate-papo de cada usuário.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
