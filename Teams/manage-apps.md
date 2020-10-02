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
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Saiba como gerenciar seus aplicativos do teams na página Gerenciar aplicativos do centro de administração do Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: d75664a6d3884529936f8adcb69a928bdd238b3d
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48336941"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar seus aplicativos no centro de administração do Microsoft Teams
======================================================

Como administrador, a página Gerenciar aplicativos no centro de administração do Microsoft Teams é onde você vê e gerencia todos os aplicativos do teams para sua organização. Aqui, você pode ver o status e as propriedades de nível de organização de aplicativos, aprovar ou carregar novos aplicativos personalizados para a loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização, adicionar aplicativos às equipes (na visualização), comprar serviços para aplicativos de terceiros, exibir as permissões solicitadas por aplicativos, conceder consentimento de administrador aos aplicativos e gerenciar as configurações de aplicativo em toda a

A página Gerenciar aplicativos fornece um modo de exibição para todos os aplicativos disponíveis, fornecendo a você as informações de que você precisa para decidir quais aplicativos permitir ou bloquear em sua organização. Em seguida, você pode usar [políticas de permissão do aplicativo](teams-app-permission-policies.md), políticas de configuração do [aplicativo](teams-app-setup-policies.md)e [políticas e configurações personalizadas do aplicativo](teams-custom-app-policies-and-settings.md) para configurar a experiência do aplicativo para usuários específicos em sua organização.

Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**. Você deve ser administrador global ou administrador do teams Service para acessar a página.

> [!NOTE]
> A página Gerenciar aplicativos ainda não está disponível nas implantações da Comunidade do governo do Microsoft 365 (GCC) do teams.

## <a name="view-apps"></a>Exibir aplicativos

Você pode exibir todos os aplicativos, incluindo as informações a seguir sobre cada aplicativo.

![Captura de tela da página de aplicativos gerenciados](media/manage-apps.png)

- **Nome**: o nome do aplicativo. Clique no nome do aplicativo para acessar a página detalhes do aplicativo e ver mais informações sobre o aplicativo. Isso inclui uma descrição do aplicativo, seja ela permitida ou bloqueada, versão, política de privacidade, termos de uso, categorias que se aplicam ao aplicativo, status de certificação, recursos com suporte e ID do aplicativo. Veja um exemplo:

  ![Captura de tela da página de detalhes de aplicativos de um aplicativo](media/manage-apps-app-details.png)
  
- **Certificação**: se o aplicativo tiver passado pela certificação, você verá o **Microsoft 365 Certified** ou **atestado de fornecedor**. Clique no link para exibir os detalhes de certificação do aplicativo. Se você vir " **--** ", não temos informações de certificação para o aplicativo. Para saber mais sobre aplicativos certificados no Teams, leia [o programa de certificação de aplicativos Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Fornecedor**: nome do fornecedor.
- **Status de publicação**: status de publicação de aplicativos personalizados.
- **Status**: status do aplicativo no nível da organização, que pode ser um dos seguintes:

    - **Permitido**: o aplicativo está disponível para todos os usuários em sua organização.
    
    - **Bloqueado**: o aplicativo está bloqueado e não está disponível para os usuários de sua organização.
    
    - **Bloqueou toda a organização**: o aplicativo está bloqueado em configurações de aplicativo de toda a organização.
    
      É importante saber que essa coluna representa o status permitido e bloqueado dos aplicativos que estavam anteriormente no painel configurações de **toda a organização** . Agora, você vê, bloqueia e permite aplicativos na organização toda a partir da página **gerenciar aplicativos** . 
- **Licenças**: indica se um aplicativo oferece uma assinatura SaaS (software como serviço) para compra. Esta coluna se aplica somente a aplicativos de terceiros. Cada aplicativo de terceiros terá um dos seguintes valores:
    - **Compre agora**: o aplicativo oferece uma assinatura SaaS e está disponível para compra.  
    - **Comprado**: o aplicativo oferece uma assinatura SaaS e você comprou licenças para ela.
    - **--**: O aplicativo não oferece uma assinatura SaaS.
- **Aplicativo personalizado**: se o aplicativo é um aplicativo personalizado.
- **Permissões**: indica se um aplicativo de terceiros ou personalizado registrado no Azure Active Directory (Azure AD) tem permissões que precisam de consentimento. Você verá um dos seguintes valores:
    - **Exibir detalhes**: o aplicativo tem permissões que exigem consentimento para que o aplicativo possa acessar dados. 
    - **--**: O aplicativo não tem permissões que precisem de consentimento.
- **Categorias**: categorias que se aplicam ao aplicativo.
- **Versão**: versão do aplicativo.

Para ver as informações desejadas na tabela, clique em **Editar coluna** no canto superior direito para adicionar ou remover colunas à tabela.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publicar um aplicativo personalizado na loja de aplicativos da sua organização

Use a página Gerenciar aplicativos para publicar aplicativos criados especificamente para a sua organização. Depois de publicar um aplicativo personalizado, ele estará disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado na loja de aplicativos da sua organização. A maneira como você usa depende de como você obtém o aplicativo.

- [Aprovar um aplicativo personalizado](#approve-a-custom-app): Use esse método se o desenvolvedor enviar o aplicativo diretamente para a página Gerenciar aplicativos usando a API de envio do aplicativo Teams. Em seguida, você pode revisar e publicar (ou rejeitar) o aplicativo diretamente da página de detalhes do aplicativo.
- [Carregar um pacote de aplicativo](#upload-an-app-package): Use esse método se o desenvolvedor enviar o pacote do aplicativo em formato. zip. Você publica o aplicativo carregando o pacote do aplicativo.

###  <a name="approve-a-custom-app"></a>Aprovar um aplicativo personalizado

O widget **aprovações pendentes** na página Gerenciar aplicativos informa quando um desenvolvedor envia um aplicativo usando a API de envio de aplicativo Teams. Um aplicativo recém enviado é listado com um **status** de publicação **enviado** e um **status** de **bloqueado**. Acesse a página de detalhes do aplicativo para ver mais informações sobre o aplicativo e, em seguida, publicá-lo, defina o **status de publicação** como **publicar**.

Você também é notificado quando um desenvolvedor envia uma atualização para um aplicativo personalizado. Em seguida, você pode revisar e publicar (ou rejeitar) a atualização na página de detalhes do aplicativo. Todas as políticas de permissão do aplicativo e políticas de configuração do aplicativo permanecem impostas para o aplicativo atualizado.

Para saber mais, confira [publicar um aplicativo personalizado enviado por meio da API de envio de aplicativos Teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Carregar um pacote de aplicativo

O desenvolvedor cria um pacote de aplicativos Teams usando o [Teams app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)e, em seguida, o envia para você no formato. zip. Quando você tem o pacote do aplicativo, pode carregá-lo na loja de aplicativos da sua organização.

Para carregar um novo aplicativo personalizado, selecione **carregar** para carregar o pacote do aplicativo. O aplicativo não está realçado depois de carregado, portanto, você precisará pesquisar a lista de aplicativos na página Gerenciar aplicativos para localizá-lo.

Para atualizar um aplicativo após ele ser carregado, na lista de aplicativos na página Gerenciar aplicativos, clique no nome do aplicativo e, em seguida, clique em **Atualizar**. Isso substitui o aplicativo existente e todas as políticas de permissão do aplicativo e as políticas de configuração do aplicativo permanecem impostas para o aplicativo atualizado.

Para saber mais, confira [publicar um aplicativo personalizado carregando um pacote de aplicativo](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Permitir e bloquear aplicativos

A página Gerenciar aplicativos é onde você permite ou bloqueia aplicativos individuais no nível da organização. Ele mostra todos os aplicativos disponíveis e seu status atual do aplicativo de nível da organização. (O bloqueio e a permissão de aplicativos no nível da organização foram movidos do painel **configurações do aplicativo de toda a organização** para este local.)

Para permitir ou bloquear um aplicativo, selecione-o e, em seguida, clique em **permitir** ou **Bloquear**. Quando você bloqueia um aplicativo, todas as interações com esse aplicativo são desabilitadas e o aplicativo não aparece no Teams para os usuários de sua organização.

Quando você bloqueia ou permite um aplicativo na página Gerenciar aplicativos, esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização.  Quando você bloqueia ou permite um aplicativo em uma política de permissão do aplicativo Teams, ele é bloqueado ou permitido para os usuários atribuídos a essa política. Para que um usuário possa instalar e interagir com qualquer aplicativo, você deve permitir o aplicativo no nível da organização na página Gerenciar aplicativos e na política de permissão do aplicativo atribuída ao usuário.

 > [!NOTE]
 > Para desinstalar um aplicativo, clique com o botão direito do mouse no aplicativo e, em seguida, clique em **desinstalar** ou use o menu **mais aplicativos** no lado esquerdo.

## <a name="add-an-app-to-a-team"></a>Adicionar um aplicativo a uma equipe

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Use o botão **Adicionar à equipe** para instalar um aplicativo para uma equipe. Lembre-se de que isso é somente para aplicativos que podem ser instalados em um escopo de equipe. O botão **Adicionar à equipe** não está disponível para aplicativos que só podem ser instalados no escopo pessoal.

![Captura de tela do botão Adicionar à equipe](media/manage-apps-add-app-team.png)

1. Procure o aplicativo desejado e, em seguida, selecione o aplicativo clicando à esquerda do nome do aplicativo.
2. Selecione **Adicionar à equipe**.
3. No painel **Adicionar à equipe** , procure a equipe à qual você deseja adicionar o aplicativo, selecione a equipe e, em seguida, selecione **aplicar**.

## <a name="purchase-services-for-third-party-apps"></a>Comprar serviços para aplicativos de terceiros

Você pode pesquisar e comprar licenças de serviços oferecidos por aplicativos de terceiros para os usuários de sua organização diretamente na página Gerenciar aplicativos. A coluna **licenças** na tabela indica se um aplicativo oferece uma assinatura SaaS paga. Clique em **comprar agora** para ver as informações de planos e preços e comprar licenças para seus usuários. Para saber mais, confira [serviços de compra do Microsoft Teams para aplicativos de terceiros no centro de administração do Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Conceder consentimento de administrador aos aplicativos

Você pode revisar e conceder consentimento para aplicativos que solicitam permissões em nome de todos os usuários em sua organização. Isso é feito para que os usuários não precisem revisar e aceitar as permissões solicitadas pelo aplicativo quando iniciarem o aplicativo. A coluna **permissões** indica se um aplicativo tem permissões que precisam de consentimento. Você verá um link **Exibir detalhes** para cada aplicativo registrado no Azure AD que tenha permissões que precisem de consentimento. Para saber mais, consulte [exibir permissões do aplicativo e conceder consentimento ao administrador no centro de administração do Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Exibir permissões de consentimento específicas do recurso

As permissões de consentimento específico do recurso (RSC) permitem que os proprietários da equipe concederem consentimento para que um aplicativo acesse e modifique os dados de uma equipe. Permissões de RSC são específicas, permissões específicas de equipes que definem o que um aplicativo pode fazer em uma equipe específica. Você pode exibir permissões de RSC na guia **permissões** da página de detalhes do aplicativo para um aplicativo. Para saber mais, consulte [exibir permissões do aplicativo e conceder consentimento ao administrador no centro de administração do Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativo de toda a organização

Use as configurações de aplicativo de toda a organização para controlar se os usuários podem instalar aplicativos de terceiros e se os usuários podem carregar ou interagir com aplicativos personalizados em sua organização. As configurações de aplicativo de toda a organização governam o comportamento para todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Você pode usá-los para controlar aplicativos mal-intencionados ou problemáticos.

> [!NOTE]
> Para saber como usar as configurações de aplicativo de toda a organização nas implantações do Microsoft 365 governo-GCC do Teams, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](teams-app-permission-policies.md).

1. Na página Gerenciar aplicativos, selecione **configurações de aplicativo de toda a organização**. Em seguida, você pode definir as configurações desejadas no painel.

    ![Captura de tela das configurações de aplicativo de toda a organização](media/manage-apps-org-wide-app-settings.png)
    
2. Em **aplicativos de terceiros**, desative ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    - **Permitir aplicativos de terceiros**: isso controla se os usuários podem usar aplicativos de terceiros. Se você desabilitar essa configuração, os usuários não poderão instalar ou usar qualquer aplicativo de terceiros, e o status do aplicativo desses aplicativos será exibido como **bloqueado em toda a organização** na tabela.

        > [!NOTE]
        > Quando **permitir que aplicativos de terceiros** estejam desativados, os [WebHooks de saída](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) são desativados, o que significa que os usuários não podem criá-los. Quando essa configuração está ativada, os WebHooks de saída são habilitados para todos os usuários e você pode controlá-los no nível do usuário, permitindo ou bloqueando o aplicativo webhook de saída por meio [das políticas de permissão do aplicativo](teams-app-permission-policies.md). <br><br>Observe que, se você tiver [políticas de permissão de aplicativo](teams-app-permission-policies.md) existentes para **aplicativos da Microsoft** que usam a configuração **permitir aplicativos específicos e bloquear todas as outras** e desejar habilitar WebHooks de saída para usuários, adicione o aplicativo webhook de saída à lista.
    - **Permitir que todos os novos aplicativos de terceiros publicados na loja por padrão**: controlam se novos aplicativos de terceiros publicados na App App Store se tornam disponíveis automaticamente no Teams. Você só pode definir esta opção se permitir aplicativos de terceiros.

3. Em **aplicativos personalizados**, desative ou ative **permitir interação com aplicativos personalizados**. Esta configuração controla se os usuários podem interagir com aplicativos personalizados. Para saber mais, consulte [gerenciar políticas e configurações personalizadas do aplicativo no Microsoft Teams](teams-custom-app-policies-and-settings.md).
4. Clique em **salvar** para que as configurações de aplicativo de toda a organização entrem em vigor.

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de administração para aplicativos no Teams](admin-settings.md)