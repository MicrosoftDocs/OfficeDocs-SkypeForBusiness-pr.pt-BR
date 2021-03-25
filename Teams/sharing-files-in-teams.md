---
title: Compartilhamento de arquivos e pastas no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: Saiba mais sobre a experiência de compartilhamento de arquivos e pastas no Microsoft Teams.
ms.openlocfilehash: 53997f4493a0217e980427ab0d1f85d64095b9c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117019"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="3fa4f-103">Compartilhando arquivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fa4f-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="3fa4f-104">No Microsoft Teams os usuários podem compartilhar conteúdo com outros usuários do Microsoft Teams dentro e fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="3fa4f-105">O compartilhamento de arquivos e pastas no Teams se baseia nas configurações configuradas no SharePoint e no OneDrive, portanto, o que você configurar para o SharePoint e o OneDrive também afetará o compartilhamento no Teams.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="3fa4f-106">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="3fa4f-106">Overview</span></span>

<span data-ttu-id="3fa4f-107">Os usuários podem compartilhar arquivos do OneDrive, de equipes e de sites que tenham acesso para e a partir do computador. </span><span class="sxs-lookup"><span data-stu-id="3fa4f-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="3fa4f-108">Para compartilhar um arquivo, os usuários podem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3fa4f-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="3fa4f-p103">Em um canal, clicar em **Anexar** (o ícone de clipe de papel), selecione **Recente**, **Navegar Microsoft Teams e Canais**, **OneDrive** ou **Carregar do meu computador** e, em seguida, escolher o arquivo que desejam compartilhar.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-p103">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share. </span></span><br> 
    <span data-ttu-id="3fa4f-110">![Captura de tela mostrando o compartilhamento de um arquivo de um canal](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="3fa4f-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="3fa4f-p104">Em um chat, clicar em **Anexar** (o ícone de clipe de papel), selecionar **OneDrive** ou **Carregar do meu computador** e, em seguida, escolher o arquivo que desejam compartilhar.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-p104">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share. </span></span><br>
    <span data-ttu-id="3fa4f-112">![Captura de tela mostrando o compartilhamento de um arquivo de um chat](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="3fa4f-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="3fa4f-113">Copiar e colar o link de compartilhamento na caixa de composição.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="3fa4f-114">![Captura de tela mostrando a visualização do arquivo na caixa de composição](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="3fa4f-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="3fa4f-115">Permissões de arquivos compartilhados e links de compartilhamento</span><span class="sxs-lookup"><span data-stu-id="3fa4f-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="3fa4f-116">Quando os usuários compartilham um arquivo dentro do Microsoft Teams, eles podem definir quem pode acessar o arquivo, da mesma forma como fazem em todo o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="3fa4f-117">Eles podem dar acesso a qualquer um, pessoas em sua organização, pessoas com acesso existente ou pessoas específicas (que podem incluir as pessoas em um chat 1:1, chat em grupo ou canal).</span><span class="sxs-lookup"><span data-stu-id="3fa4f-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="3fa4f-118">Quando um arquivo é compartilhado, a visualização do arquivo está disponível na mensagem, junto com todas as ações do arquivo como **Abrir online**, **Baixar** e **Copiar link**.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="3fa4f-119">Por padrão, o arquivo abre no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="3fa4f-120">Quando os usuários compartilham um arquivo em um chat ou canal, eles são notificados se alguns ou todos os recipientes não têm permissão para visualizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="3fa4f-121">Eles podem alterar as permissões no arquivo antes de compartilhar clicando na seta ao lado da visualização do arquivo que agora aparece na mensagem.</span><span class="sxs-lookup"><span data-stu-id="3fa4f-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Captura de tela de notificação se os recipientes não tiverem permissões](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="3fa4f-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3fa4f-123">Related topics</span></span>

[<span data-ttu-id="3fa4f-124">Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fa4f-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="3fa4f-125">Alterar o tipo de link padrão para um site</span><span class="sxs-lookup"><span data-stu-id="3fa4f-125">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)

[<span data-ttu-id="3fa4f-126">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="3fa4f-126">Collaborate with guests in a team</span></span>](/microsoft-365/solutions/collaborate-as-team)