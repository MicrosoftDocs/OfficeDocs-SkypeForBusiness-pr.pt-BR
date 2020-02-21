---
title: Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Orientação para a publicação de aplicativos no catálogo de aplicativos do Microsoft Teams locatário.
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
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161610"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>Publicar aplicativos no catálogo de aplicativos do Microsoft Teams locatário
=======================================================

Você pode usar o catálogo de aplicativos do Microsoft Teams locatário para testar e distribuir aplicativos de linha de negócios para sua organização.

O catálogo de aplicativos do locatário do teams permite a distribuição de aplicativos de linha de negócios que foram criados especificamente para a sua organização e que você depende de realizar funções comerciais essenciais.

Para publicar aplicativos para sua organização, entre no cliente do Microsoft Teams usando uma conta com a função de administrador global ou administrador do teams Service e siga as etapas abaixo.

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>Publicar um aplicativo no catálogo de aplicativos locatário do cliente da equipe

> [!NOTE]
> Estas etapas descrevem como publicar um aplicativo usando o cliente do teams. Você também pode publicar um aplicativo na página **gerenciar aplicativos** no centro de administração do Microsoft Teams. Para saber mais, consulte [gerenciar aplicativos no Microsoft Teams](manage-apps.md).

### <a name="get-a-teams-app-package"></a>Obter um pacote de aplicativos do teams

Um pacote do aplicativo Teams é criado usando o [Teams app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Depois que tiver o pacote do aplicativo, você poderá adicioná-lo ao catálogo de aplicativos do locatário. Embora todos os usuários em sua organização possam ver o catálogo de aplicativos, apenas administradores globais e administradores de serviços de equipe podem publicá-los e gerenciá-los.

### <a name="go-to-the-tenant-app-catalog"></a>Vá para o catálogo de aplicativos do locatário

Inicie o Teams e entre usando suas credenciais de administrador de serviço global ou Teams. Selecione **aplicativos** no lado esquerdo do aplicativo e, em seguida, selecione a nova seção chamada para sua organização específica (neste exemplo, contoso). Os usuários em sua organização podem exibir os aplicativos no catálogo e instalá-los para as equipes das quais eles são membros.

![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>Adicionar um aplicativo ao catálogo de aplicativos do locatário

1. Na página **aplicativos** , selecione **carregar um** > carregamento de aplicativo personalizado**para contoso**.

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

    (Você também pode escolher **carregar para mim ou minhas equipes**, que é chamado de *Sideload*. O Sideload torna o aplicativo disponível somente para suas equipes ou para as equipes que você selecionar.)

2. Navegue até o pacote do aplicativo e selecione-o e, em seguida, clique em **abrir**.

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

Quando você voltar ao catálogo de aplicativos do locatário, o novo aplicativo empresarial estará lá. Lembre-se, somente você e os membros da sua organização têm acesso a este catálogo de aplicativos.

### <a name="update-an-app-in-the-tenant-app-catalog"></a>Atualizar um aplicativo no catálogo de aplicativos locatário

1. Em seu catálogo de aplicativos locatário, selecione "**...**" no canto superior direito do aplicativo que você deseja atualizar.

2. Navegue até o pacote do aplicativo atualizado e selecione-o e clique em **abrir**.

    ![Captura de tela da loja de aplicativos do teams mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

O aplicativo será revisado para a versão 2,0. Você também pode excluir o aplicativo de toda a sua empresa neste menu.

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>Usar o centro de administração do Microsoft Teams para gerenciar o catálogo de aplicativos do locatário

Se você tiver aplicativos que precisem de correções de bugs, pode desativar temporariamente aplicativos para usuários em uma política de permissão de aplicativo.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para > **políticas de permissão**de **aplicativos do teams**.
2. Selecione a política de permissão do aplicativo que você deseja editar e, em seguida, clique em **Editar**.
3. Em **aplicativos de locatário**, selecione **bloquear aplicativos específicos e permitir todos os outros**e, em seguida, adicione os aplicativos que você deseja bloquear.

Desabilitar um aplicativo impede que os usuários interajam com o aplicativo, sem excluir o aplicativo totalmente. Esses controles proporcionam flexibilidade e controle adicionais ao gerenciar aplicativos em sua organização.

Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](teams-app-permission-policies.md).