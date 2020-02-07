---
title: Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Orientação para a publicação de aplicativos no catálogo de aplicativos Microsoft Teams locatário.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1b2fb38dcca7142cad82d290b1225e69f035bae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836911"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
=======================================================

Você pode usar o catálogo de aplicativos Microsoft Teams locatário para testar e distribuir aplicativos de linha de negócios para sua organização.

O catálogo de aplicativos de locatários do teams permite distribuir aplicativos de linha de negócios que foram criados especificamente para a sua organização e que você depende de realizar funções comerciais essenciais.

Para publicar aplicativos para sua organização, entre no cliente do Microsoft Teams usando uma conta com as funções de administrador global ou administrador do Team Service e siga as instruções abaixo.

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>Publicar um aplicativo no catálogo de aplicativos do locatário a partir do cliente do teams

> [!NOTE]
> Você precisa estar conectado ao cliente do Microsoft Teams com uma conta que tenha a função de administrador global de administrador ou Teams Service habilitada para publicar aplicativos para a sua organização. Saiba mais sobre o [uso de funções de administrador para gerenciar o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).

### <a name="get-a-teams-app-package"></a>Obter um pacote de aplicativos do teams

Um pacote do aplicativo Teams é criado usando o [Teams app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Depois que tiver o pacote do aplicativo, você poderá adicioná-lo ao catálogo de aplicativos da empresa. Embora todos os usuários no locatário possam ver o catálogo de aplicativos, apenas administradores globais e administradores de serviço de equipe têm a capacidade de publicá-lo e gerenciá-lo.

### <a name="go-to-the-tenant-apps-catalog"></a>Vá para o catálogo de aplicativos do locatário

Inicie o cliente do Microsoft Teams e entre usando suas credenciais de administrador do serviço global ou Teams. Selecione **aplicativos** no lado esquerdo do aplicativo e, em seguida, selecione a nova seção chamada para sua organização específica (neste exemplo, contoso). Os usuários em sua organização podem exibir os aplicativos no catálogo e instalá-los para as equipes das quais eles são membros.

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Adicionar um aplicativo ao catálogo de aplicativos do locatário

1. Na página **aplicativos** , selecione **carregar um** > carregamento de aplicativo personalizado**para contoso**.

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

Se você tiver aplicativos que precisem de correções de bugs, poderá desabilitar temporariamente os aplicativos por meio do centro de administração do Microsoft 365 >**políticas de permissão** de**aplicativos** > do **Centro** > de administração do Microsoft > <nome da política, por exemplo: "global (padrão para toda a organização)" > **aplicativos locatário** > bloquear aplicativos específicos e permitir todos os outros e adicionar seu aplicativo à lista.

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

Desabilitar um aplicativo impedirá que os usuários interajam com o aplicativo, sem excluir o aplicativo totalmente. Esses controles proporcionam flexibilidade e controle adicionais ao gerenciar aplicativos em sua empresa.
