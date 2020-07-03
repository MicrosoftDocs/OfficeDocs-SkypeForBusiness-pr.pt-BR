---
title: Gerenciar seus aplicativos no centro de administração do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Saiba como gerenciar seus aplicativos do teams na página Gerenciar aplicativos do centro de administração do Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 7884aa033d3d137ac36fe86a47a2861732b50bb5
ms.sourcegitcommit: ad82786076cc965e75b1ec5ffd4bc9bf75437340
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45028087"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar seus aplicativos no centro de administração do Microsoft Teams
======================================================

Como administrador, a página **gerenciar aplicativos** no centro de administração do Microsoft Teams é onde você vê e gerencia todos os aplicativos do teams no catálogo de aplicativos da sua organização. Aqui, você pode ver o status e as propriedades dos aplicativos no nível da organização, carregar novos aplicativos personalizados para o catálogo de aplicativos do locatário, bloquear ou permitir aplicativos no nível da organização e gerenciar as configurações de aplicativo de toda a organização.

A página **gerenciar aplicativos** oferece uma exibição de todos os aplicativos disponíveis em seu catálogo de locatários, fornecendo as informações necessárias para decidir quais aplicativos permitir ou bloquear em sua organização. Em seguida, você pode usar [políticas de permissão do aplicativo](teams-app-permission-policies.md), políticas de configuração do [aplicativo](teams-app-setup-policies.md)e [políticas e configurações personalizadas do aplicativo](teams-custom-app-policies-and-settings.md) para configurar a experiência do aplicativo para usuários específicos em sua organização.

Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**. Você deve ser administrador global ou administrador do teams Service para acessar a página.

## <a name="view-apps-in-your-tenant-app-catalog"></a>Exibir aplicativos em seu catálogo de aplicativos locatário

Você pode exibir todos os aplicativos no catálogo do aplicativo locatário, incluindo as informações a seguir sobre cada aplicativo.

![Captura de tela da página de aplicativos gerenciados](media/manage-apps.png)

- **Nome**: o nome do aplicativo. Clique no nome do aplicativo para ver mais informações sobre o aplicativo. Isso inclui uma descrição do aplicativo, seja ele permitido ou bloqueado, versão, categorias que se aplicam ao aplicativo, status de certificação, recursos com suporte e ID do aplicativo. Veja um exemplo:<br> 
![Captura de tela da página de detalhes de aplicativos de um aplicativo](media/manage-apps-app-details.png)
- **Certificação**: se o aplicativo tiver passado pela certificação, você verá o **Microsoft 365 Certified** ou **atestado de fornecedor**. Clique no link para exibir os detalhes de certificação do aplicativo. Se você vir " **--** ", não temos informações de certificação para o aplicativo. Para saber mais sobre aplicativos certificados no Teams, leia [o programa de certificação de aplicativos Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Categorias**: categorias que se aplicam ao aplicativo.
- **Status do aplicativo**: status do aplicativo no nível da organização, que pode ser um dos seguintes:
    - **Permitido**: o aplicativo está disponível para todos os usuários em sua organização.
    - **Bloqueado**: o aplicativo está bloqueado e não está disponível para os usuários de sua organização.
    - **Bloqueou toda a organização**: o aplicativo está bloqueado em configurações de aplicativo de toda a organização. <br>
É importante saber que essa coluna representa o status permitido e bloqueado dos aplicativos que estavam anteriormente no painel configurações de **toda a organização** . Agora, você vê, bloqueia e permite aplicativos na organização toda a partir da página **gerenciar aplicativos** . 
- **Versão**: versão do aplicativo.

Para ver as informações desejadas na tabela, clique em **Editar coluna** no canto superior direito para adicionar ou remover colunas à tabela.

## <a name="upload-a-new-app"></a>Carregar um novo aplicativo

Você pode usar o catálogo de aplicativos para testar e distribuir aplicativos personalizados que são criados especificamente para a sua organização. Um pacote do aplicativo Teams é criado usando o [Teams app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Quando você tem o pacote do aplicativo, pode adicioná-lo ao seu catálogo de aplicativos. Embora todos os usuários em sua organização possam ver o catálogo de aplicativos, somente administradores globais e administradores de serviços de equipe podem publicá-lo e gerenciá-lo.

Para carregar um novo aplicativo personalizado para o catálogo de aplicativos do locatário, clique em **carregar novo aplicativo** para carregar seu pacote de aplicativo em formato. zip. O aplicativo não está realçado depois de carregado, portanto, você precisará pesquisar o catálogo de aplicativos para localizá-lo.

Para atualizar um aplicativo após ele ser carregado, na lista de aplicativos na página **gerenciar aplicativos** , clique no nome do aplicativo e, em seguida, clique em **Atualizar**. Isso substitui o aplicativo existente em seu catálogo de aplicativos e todas as políticas de permissão do aplicativo e políticas de configuração do aplicativo permanecem impostas para o aplicativo atualizado.

Para saber mais, consulte [gerenciar seus aplicativos personalizados no Microsoft Teams](manage-your-custom-apps.md).

## <a name="allow-and-block-apps"></a>Permitir e bloquear aplicativos

A página **gerenciar aplicativos** é onde você permite ou bloqueia aplicativos individuais no nível da organização. Ele mostra todos os aplicativos disponíveis e seu status atual do aplicativo de nível da organização. (O bloqueio e a permissão de aplicativos no nível da organização foram movidos do painel **configurações do aplicativo de toda a organização** para este local.)

Para permitir ou bloquear um aplicativo, selecione-o e, em seguida, clique em **permitir** ou **Bloquear**. Quando você bloqueia um aplicativo, todas as interações com esse aplicativo são desabilitadas e o aplicativo não aparece no Teams para os usuários de sua organização.

Quando você bloqueia ou permite um aplicativo na página **gerenciar aplicativos** , esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização.  Quando você bloqueia ou permite um aplicativo em uma política de permissão do aplicativo Teams, ele é bloqueado ou permitido para os usuários atribuídos a essa política. Para que um usuário possa instalar e interagir com qualquer aplicativo, você deve permitir o aplicativo no nível da organização na página **gerenciar aplicativos** e na política de permissão do aplicativo atribuída ao usuário.

 > [!NOTE]
 > Para desinstalar um aplicativo, clique com o botão direito do mouse no aplicativo e, em seguida, clique em **desinstalar** ou use o menu **mais aplicativos** no lado esquerda. 

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativo de toda a organização

Use as configurações de aplicativo de toda a organização para controlar se os usuários podem instalar aplicativos de terceiros e se os usuários podem carregar ou interagir com aplicativos personalizados em sua organização. As configurações de aplicativo de toda a organização governam o comportamento para todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Você pode usá-los para controlar aplicativos mal-intencionados ou problemáticos.

1. Na página **gerenciar aplicativos** , selecione **configurações de aplicativo de toda a organização**. Em seguida, você pode definir as configurações desejadas no painel.

    ![Captura de tela das configurações de aplicativo de toda a organização](media/manage-apps-org-wide-app-settings.png)
    
2. Em **aplicativos de terceiros**, desative ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    - **Permitir aplicativos de terceiros**: isso controla se os usuários podem usar aplicativos de terceiros. Se você desabilitar essa configuração, os usuários não poderão instalar ou usar qualquer aplicativo de terceiros, e o status do aplicativo desses aplicativos será exibido como **bloqueado em toda a organização** na tabela.

        > [!NOTE]
        > Em uma implantação do Microsoft 365 governo-GCC do Teams, a configuração **permitir aplicativos** de terceiros está desativada por padrão.

        Quando **permitir que aplicativos de terceiros** estejam desativados, os [WebHooks de saída](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) são desativados, o que significa que os usuários não podem criá-los. Quando essa configuração está ativada, os WebHooks de saída são habilitados para todos os usuários, independentemente de a configuração estar ativada ou desativada na política de permissão do aplicativo dos usuários.
    - **Permitir que todos os novos aplicativos de terceiros publicados na loja por padrão**: controlam se novos aplicativos de terceiros publicados na App App Store se tornam disponíveis automaticamente no Teams. Você só pode definir esta opção se permitir aplicativos de terceiros.

3. Em **aplicativos personalizados**, desative ou ative **permitir interação com aplicativos personalizados**. Esta configuração controla se os usuários podem interagir com aplicativos personalizados. Para saber mais, consulte [gerenciar políticas e configurações personalizadas do aplicativo no Microsoft Teams](teams-custom-app-policies-and-settings.md).
4. Clique em **salvar** para que as configurações de aplicativo de toda a organização entrem em vigor.

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de administração para aplicativos no Teams](admin-settings.md)
