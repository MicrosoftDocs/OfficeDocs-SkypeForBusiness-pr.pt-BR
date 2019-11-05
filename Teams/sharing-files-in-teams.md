---
title: Compartilhando arquivos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
search.appverid: MET150
description: O Microsoft Teams usa as configurações do OneDrive e do SharePoint para controlar o compartilhamento.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4114444da68e7a18fe66f7d32e3f64ab98a0b00b
ms.sourcegitcommit: 7920c47eb73e665dad4bf7214b28541d357bce25
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37962075"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="3dba9-103">Compartilhando arquivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3dba9-103">Sharing files in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-coming-soon-article](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="3dba9-104">Os recursos de compartilhamento de arquivos no Microsoft Teams permitem que os usuários compartilhem conteúdo com outros usuários do Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3dba9-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="3dba9-105">O compartilhamento no Teams é baseado nas configurações definidas no SharePoint e no OneDrive, portanto, o que você configurou para o SharePoint e o OneDrive também controlará o compartilhamento no Teams.</span><span class="sxs-lookup"><span data-stu-id="3dba9-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

![Diagrama mostrando como as equipes, o SharePoint e o OneDrive trabalham juntos](media/sharing-files-in-teams-image1.png)

<span data-ttu-id="3dba9-107">O compartilhamento de equipes permite que os usuários façam o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3dba9-107">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="3dba9-108">Compartilhar arquivos do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3dba9-108">Share files from OneDrive.</span></span>

- <span data-ttu-id="3dba9-109">Defina as permissões para os arquivos que desejam compartilhar com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="3dba9-109">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="3dba9-110">Compartilhe arquivos entre equipes.</span><span class="sxs-lookup"><span data-stu-id="3dba9-110">Share files across Teams.</span></span>

- <span data-ttu-id="3dba9-111">Compartilhar arquivos a partir de sua lista de arquivos acessados recentemente (normalmente, estes são os arquivos que os usuários estão mais interessados em compartilhar).</span><span class="sxs-lookup"><span data-stu-id="3dba9-111">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="3dba9-112">Permaneça dentro do teams quando clicar em um nome de arquivo para abrir um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3dba9-112">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="3dba9-113">O Teams encurta URLS longas do SharePoint e URLS de navegador que apontam para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3dba9-113">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="3dba9-114">O Teams usa apenas o nome do arquivo para vincular a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3dba9-114">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="3dba9-115">Além disso, a opção **obter link** foi alterada para **copiar** para eliminar a confusão que os usuários podem ter para dar acesso a um arquivo a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="3dba9-115">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="3dba9-116">Configurar o compartilhamento no OneDrive e no SharePoint</span><span class="sxs-lookup"><span data-stu-id="3dba9-116">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="3dba9-117">Para obter mais informações sobre o compartilhamento de arquivos no OneDrive e no SharePoint, incluindo como configurar o compartilhamento e como ativar e desativar o compartilhamento, consulte:</span><span class="sxs-lookup"><span data-stu-id="3dba9-117">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="3dba9-118">[Visão geral do compartilhamento externo](https://docs.microsoft.com/sharepoint/external-sharing-overview) – descreve o que acontece quando os usuários compartilham, dependendo do que estão compartilhando e com quem.</span><span class="sxs-lookup"><span data-stu-id="3dba9-118">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="3dba9-119">[Ativar ou desativar o compartilhamento externo](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) -descreve como os administradores globais e do SharePoint podem alterar as configurações de compartilhamento no nível da organização para o SharePoint e o onedrive.</span><span class="sxs-lookup"><span data-stu-id="3dba9-119">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="3dba9-120">[Alterar o compartilhamento externo de um site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – descreve como os administradores globais e do SharePoint podem ativar ou desativar o compartilhamento externo de um site.</span><span class="sxs-lookup"><span data-stu-id="3dba9-120">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="3dba9-121">[Altere o tipo de link padrão quando os usuários recebem links para compartilhamento](https://docs.microsoft.com/sharepoint/change-default-sharing-link) – descreve como definir o tipo de link padrão para que seja mais restritivo.</span><span class="sxs-lookup"><span data-stu-id="3dba9-121">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="3dba9-122">Mais informações</span><span class="sxs-lookup"><span data-stu-id="3dba9-122">More information</span></span>

- [<span data-ttu-id="3dba9-123">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3dba9-123">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="3dba9-124">[SharePoint e Teams: melhor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="3dba9-124">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="3dba9-125">Compartilhar arquivos e pastas do OneDrive</span><span class="sxs-lookup"><span data-stu-id="3dba9-125">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="3dba9-126">Compartilhar arquivos ou pastas do SharePoint</span><span class="sxs-lookup"><span data-stu-id="3dba9-126">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

