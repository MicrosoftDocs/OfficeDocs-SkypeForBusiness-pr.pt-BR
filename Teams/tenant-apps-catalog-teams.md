---
title: Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Orientação para a publicação de aplicativos no catálogo de aplicativos Microsoft Teams locatário.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d016fd1c341774115b9b68edafcc47a63e42b0d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221321"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
=======================================================

Você pode usar o catálogo de aplicativos Microsoft Teams locatário para testar e distribuir aplicativos de linha de negócios para sua organização.

O catálogo de aplicativos de locatários do teams permite distribuir aplicativos de linha de negócios que foram criados especificamente para a sua organização e que você depende de realizar funções comerciais essenciais.

Para publicar aplicativos para sua organização, entre no cliente do Microsoft Teams usando as credenciais de administrador global e siga as instruções abaixo.

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>Publicar um aplicativo no catálogo de aplicativos do locatário a partir do cliente do teams

> [!NOTE]
> Você precisa estar conectado ao cliente do Microsoft Teams usando suas credenciais de administrador global para publicar aplicativos para a sua organização.

### <a name="get-a-teams-app-package"></a>Obter um pacote de aplicativos do teams

Um pacote do aplicativo Teams é criado usando o [Teams app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Depois que tiver o pacote do aplicativo, você poderá adicioná-lo ao catálogo de aplicativos da empresa. Embora todos os usuários no locatário possam ver o catálogo de aplicativos, atualmente somente os administradores globais têm a capacidade de publicá-lo e gerenciá-lo. (Eventualmente, os administradores do teams também poderão fazer isso.)

### <a name="go-to-the-tenant-apps-catalog"></a>Vá para o catálogo de aplicativos do locatário

Inicie o cliente do Microsoft Teams e entre usando suas credenciais de administrador global. Na loja do Microsoft Teams, selecione a nova seção nomeada para a sua organização específica (neste exemplo, contoso). Os usuários em sua organização podem exibir os aplicativos no catálogo e instalá-los para as equipes das quais eles são membros.

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Adicionar um aplicativo ao catálogo de aplicativos do locatário

1. Na loja, selecione **carregar um** > carregamento de aplicativo personalizado**para contoso**.

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

    (Você também pode escolher **carregar para mim ou minhas equipes**, que é chamado de *Sideload*. O Sideload torna o aplicativo disponível somente para suas equipes ou para as equipes que você selecionar.)

2. Navegue até o pacote do aplicativo e selecione-o e, em seguida, clique em **abrir**.

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

Quando você voltar ao catálogo de aplicativos do locatário, o novo aplicativo empresarial estará lá. Lembre-se, somente você e os membros da sua organização têm acesso a este catálogo de aplicativos.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>Atualizar um aplicativo no catálogo de aplicativos do locatário

1. Em seu catálogo de aplicativos do locatário, selecione "**...**" no canto superior direito do aplicativo que você deseja atualizar.

2. Navegue até o pacote do aplicativo atualizado e selecione-o e clique em **abrir**.

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

O aplicativo será revisado para a versão 2,0. Você também pode excluir o aplicativo de toda a sua empresa neste menu.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Usar o portal de administração do Office 365 para gerenciar o catálogo de aplicativos do locatário

Se você tiver aplicativos que precisem de correções de bugs, poderá desabilitar temporariamente os aplicativos por meio do portal de administração do Office 365. Selecione **configurações** > **Serviços & suplementos** > **Microsoft Teams**. Além das configurações anteriores, agora há uma seção dedicada aos aplicativos da sua empresa. Você pode escolher quais aplicativos deseja habilitar ou desabilitar.

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

Desabilitar um aplicativo impedirá que os usuários interajam com o aplicativo, sem excluir o aplicativo totalmente. Esses controles proporcionam flexibilidade e controle adicionais ao gerenciar aplicativos em sua empresa.
