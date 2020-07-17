---
title: Compartilhando arquivos no Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Saiba mais sobre a experiência de compartilhamento de arquivos no Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138318"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="dd800-103">Compartilhando arquivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd800-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="dd800-104">No Microsoft Teams, os usuários podem compartilhar conteúdo com outros usuários de equipes dentro e fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="dd800-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="dd800-105">O compartilhamento no Teams é baseado nas configurações definidas no SharePoint e no OneDrive, portanto, o que você configurou para o SharePoint e o OneDrive também controlará o compartilhamento no Teams.</span><span class="sxs-lookup"><span data-stu-id="dd800-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="dd800-106">Visão geral</span><span class="sxs-lookup"><span data-stu-id="dd800-106">Overview</span></span>

<span data-ttu-id="dd800-107">Os usuários podem compartilhar arquivos do OneDrive, de equipes e sites aos quais eles têm acesso e do computador.</span><span class="sxs-lookup"><span data-stu-id="dd800-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="dd800-108">Para compartilhar um arquivo, os usuários podem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd800-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="dd800-109">Em um canal, clique em **anexar** (o ícone de clipe de clipes), selecione **recente**, **navegue em equipes e canais**, **onedrive**ou **carregar de meu computador**e, em seguida, escolha o arquivo que deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="dd800-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="dd800-110">![Captura de tela mostrando o compartilhamento de um arquivo de um canal](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="dd800-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="dd800-111">Em um chat, clique em **anexar** (o ícone de clipe de clipe), selecione ou **onedrive** ou **carregar de meu computador**e, em seguida, escolha o arquivo que deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="dd800-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="dd800-112">![Captura de tela mostrando o compartilhamento de um arquivo de um chat](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="dd800-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="dd800-113">Copie e cole o link de compartilhamento na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="dd800-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="dd800-114">![Captura de tela mostrando a visualização de arquivo na caixa de texto](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="dd800-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="dd800-115">O que você precisa saber sobre a experiência de compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="dd800-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="dd800-116">Permissões de arquivos compartilhados e links de compartilhamento</span><span class="sxs-lookup"><span data-stu-id="dd800-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="dd800-117">Quando os usuários compartilham um arquivo navegando para ele no OneDrive ou em equipes e canais, todos os destinatários recebem acesso juntamente com a [permissão padrão definida no nível da organização](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="dd800-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="dd800-118">Quando um usuário copia e cola um link de compartilhamento, as permissões definidas nesse link de compartilhamento são respeitadas e a URL do SharePoint é reduzida ao nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="dd800-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="dd800-119">Em outras palavras, o Teams usa apenas o nome do arquivo para vincular a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="dd800-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="dd800-120">Quando os usuários compartilham um arquivo no Teams, eles podem definir quem pode acessar o arquivo da mesma forma como fazem no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd800-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="dd800-121">Elas podem dar acesso a qualquer pessoa, às pessoas da sua organização, às pessoas com acesso existente ou a pessoas específicas (que podem incluir pessoas em um chat do 1:1, em um chat em grupo ou em um canal).</span><span class="sxs-lookup"><span data-stu-id="dd800-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="dd800-122">Quando um arquivo é compartilhado, a visualização do arquivo está disponível na mensagem, juntamente com todas as ações de arquivo, como **abrir online**, **baixar**e **Copiar link**.</span><span class="sxs-lookup"><span data-stu-id="dd800-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="dd800-123">Por padrão, o arquivo é aberto no Teams.</span><span class="sxs-lookup"><span data-stu-id="dd800-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="dd800-124">Às vezes, o link de compartilhamento pode não ter sido convertido em uma visualização de arquivo quando um usuário envia a mensagem.</span><span class="sxs-lookup"><span data-stu-id="dd800-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="dd800-125">A visualização do arquivo será gerada pelo sistema, mas nesse cenário, o link de compartilhamento não será reduzido apenas para o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="dd800-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="dd800-126">Quando os usuários compartilham um arquivo em um chat ou canal, eles são notificados se alguns ou todos os destinatários não têm permissão para exibir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="dd800-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="dd800-127">Eles podem alterar as permissões no arquivo antes de compartilhá-lo clicando na seta ao lado da visualização do arquivo que agora aparece na mensagem.</span><span class="sxs-lookup"><span data-stu-id="dd800-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Captura de tela da notificação se os destinatários não tiverem permissões](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="dd800-129">Copiar um link de compartilhamento no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd800-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="dd800-130">Os usuários podem copiar um link de compartilhamento do SharePoint e alterar as permissões de compartilhamento da mesma forma que no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd800-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="dd800-131">Elas podem dar acesso a qualquer pessoa, às pessoas de sua organização, às pessoas com acesso existente ou a pessoas específicas.</span><span class="sxs-lookup"><span data-stu-id="dd800-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="dd800-132">A permissão padrão do link é a mesma do conjunto de permissões padrão no nível da organização, a menos que as permissões em nível de site do SharePoint o substituam.</span><span class="sxs-lookup"><span data-stu-id="dd800-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="dd800-133">Configurar o compartilhamento no OneDrive e no SharePoint</span><span class="sxs-lookup"><span data-stu-id="dd800-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="dd800-134">Para obter mais informações sobre o compartilhamento de arquivos no OneDrive e no SharePoint, incluindo como configurar o compartilhamento e como ativar e desativar o compartilhamento, consulte:</span><span class="sxs-lookup"><span data-stu-id="dd800-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="dd800-135">[Visão geral do compartilhamento externo](https://docs.microsoft.com/sharepoint/external-sharing-overview) – descreve o que acontece quando os usuários compartilham, dependendo do que estão compartilhando e com quem.</span><span class="sxs-lookup"><span data-stu-id="dd800-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="dd800-136">[Gerenciar configurações de compartilhamento](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) – descreve como os administradores globais e do SharePoint podem alterar as configurações de compartilhamento no nível da organização para o SharePoint e o onedrive.</span><span class="sxs-lookup"><span data-stu-id="dd800-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="dd800-137">[Ative ou desative o compartilhamento externo de um site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – descreve como os administradores globais e do SharePoint podem ativar ou desativar o compartilhamento externo de um site.</span><span class="sxs-lookup"><span data-stu-id="dd800-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="dd800-138">[Altere o tipo de link padrão para um site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) – descreve como definir o tipo de link padrão para que seja mais restritivo.</span><span class="sxs-lookup"><span data-stu-id="dd800-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="dd800-139">Mais informações</span><span class="sxs-lookup"><span data-stu-id="dd800-139">More information</span></span>

- [<span data-ttu-id="dd800-140">Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd800-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="dd800-141">SharePoint e Teams: melhor juntos</span><span class="sxs-lookup"><span data-stu-id="dd800-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="dd800-142">Compartilhar arquivos e pastas do OneDrive</span><span class="sxs-lookup"><span data-stu-id="dd800-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="dd800-143">Compartilhar arquivos ou pastas do SharePoint</span><span class="sxs-lookup"><span data-stu-id="dd800-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
