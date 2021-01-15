---
title: Gerenciar seus aplicativos no centro de administração do Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Saiba como gerenciar seus aplicativos do Teams na página Gerenciar aplicativos do Centro de administração do Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 3a79f25e9f260e798ec6e0456cacf6ba2dfe618b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822901"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar seus aplicativos no centro de administração do Microsoft Teams
======================================================

Como administrador, a página Gerenciar aplicativos no centro de administração do Microsoft Teams é onde você visualiza e gerencia todos os aplicativos do Teams para sua organização. Aqui, você pode ver o status e as propriedades de aplicativos no nível da organização, aprovar ou carregar novos aplicativos personalizados na loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização, adicionar aplicativos a equipes, comprar serviços para aplicativos de terceiros, exibir permissões solicitadas por aplicativos, conceder consentimento de administrador a aplicativos e gerenciar configurações de aplicativos em toda a organização.

A página Gerenciar aplicativos oferece uma exibição de todos os aplicativos disponíveis, fornecendo as informações necessárias para decidir quais aplicativos permitir ou bloquear em toda a organização. Em seguida, você [pode](teams-app-permission-policies.md)usar políticas de permissão de [aplicativo,](teams-app-setup-policies.md)políticas de configuração de aplicativo e políticas e configurações personalizadas para configurar a experiência do aplicativo para usuários [específicos](teams-custom-app-policies-and-settings.md) em sua organização.

Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.** Você deve ser um administrador global ou administrador de serviço do Teams para acessar a página.

> [!NOTE]
> A página Gerenciar aplicativos ainda não está disponível nas implantações do Microsoft 365 Government Community Cloud (GCC) do Teams.

## <a name="view-apps"></a>Exibir aplicativos

Você pode exibir todos os aplicativos, incluindo as seguintes informações sobre cada aplicativo.

![Captura de tela da página Aplicativos gerenciados](media/manage-apps.png)

- **Nome**: o nome do aplicativo. Clique no nome do aplicativo para ir até a página de detalhes do aplicativo para ver mais informações sobre o aplicativo. Isso inclui uma descrição do aplicativo, se ele é permitido ou bloqueado, versão, política de privacidade, termos de uso, categorias que se aplicam ao aplicativo, status de certificação, recursos com suporte e ID do aplicativo. Veja um exemplo:

  ![Captura de tela da página de detalhes de aplicativos para um aplicativo](media/manage-apps-app-details.png)
  
- **Certificação**: se o aplicativo passou pela certificação, você verá o certificado **do Microsoft 365** ou **o atestado do Publisher.** Clique no link para exibir detalhes de certificação do aplicativo. Se você vir " **--** ", não temos informações de certificação para o aplicativo. Para saber mais sobre aplicativos certificados no Teams, leia o programa de Certificação de Aplicativos do [Microsoft 365.](https://docs.microsoft.com/teams-app-certification/all-apps)  
- **Publisher**: Nome do editor.
- **Status de publicação**: Status de publicação de aplicativos personalizados.
- **Status**: Status do aplicativo no nível da organização, que pode ser um dos seguintes:

    - **Permitido**: o aplicativo está disponível para todos os usuários em sua organização.
    
    - **Bloqueado:** o aplicativo está bloqueado e não está disponível para nenhum usuário em sua organização.
    
    - **Toda a organização bloqueada:** o aplicativo é bloqueado nas configurações do aplicativo em toda a organização.
    
      É importante saber que essa coluna representa o status permitido e bloqueado dos **aplicativos** que anteriormente estavam no painel de configurações de toda a organização. Agora você visualiza, bloqueia e permite aplicativos em toda a organização na página **Gerenciar aplicativos.** 
- **Licenças**: Indica se um aplicativo oferece uma assinatura de Software como Serviço (SaaS) para compra. Esta coluna se aplica somente a aplicativos de terceiros. Cada aplicativo de terceiros terá um dos seguintes valores:
    - **Compre agora:** o aplicativo oferece uma assinatura SaaS e está disponível para compra.  
    - **Comprado**: o aplicativo oferece uma assinatura SaaS e você comprou licenças para ele.
    - **- -**: o aplicativo não oferece uma assinatura SaaS.
- **Aplicativo personalizado**: se o aplicativo é um aplicativo personalizado.
- **Permissões**: Indica se um aplicativo personalizado ou de terceiros que está registrado no Azure Active Directory (Azure AD) tem permissões que precisam de consentimento. Você verá um dos seguintes valores:
    - **Exibir detalhes:** o aplicativo tem permissões que exigem consentimento para que o aplicativo possa acessar dados. 
    - **- -**: O aplicativo não tem permissões que precisam de consentimento.
- **Categorias**: categorias que se aplicam ao aplicativo.
- **Versão**: versão do aplicativo.

Para ver as informações que você deseja na tabela, clique em **Editar** Coluna no canto superior direito para adicionar ou remover colunas à tabela.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publicar um aplicativo personalizado na loja de aplicativos da sua organização

Use a página Gerenciar aplicativos para publicar aplicativos criados especificamente para sua organização. Depois de publicar um aplicativo personalizado, ele estará disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado na loja de aplicativos da sua organização. A maneira como você usa depende de como você obter o aplicativo.

- [Aprovar um aplicativo personalizado:](#approve-a-custom-app)use este método se o desenvolvedor enviar o aplicativo diretamente para a página Gerenciar aplicativos usando a API de Envio de Aplicativos do Teams. Em seguida, você pode revisar e publicar (ou rejeitar) o aplicativo diretamente na página de detalhes do aplicativo.
- [Carregar um pacote de aplicativo:](#upload-an-app-package)use este método se o desenvolvedor enviar o pacote do aplicativo no formato .zip. Publique o aplicativo carregando o pacote do aplicativo.

###  <a name="approve-a-custom-app"></a>Aprovar um aplicativo personalizado

O **widget aprovações pendentes** na página Gerenciar aplicativos notifica você quando um desenvolvedor envia um aplicativo usando a API de Envio de Aplicativos do Teams. Um aplicativo recém-enviado é listado com um **status de** **Publicação** enviado e **um Status** de **Bloqueado.** Vá para a página de detalhes do aplicativo para ver mais informações sobre o aplicativo e, em seguida, para publicá-lo, de definir **o status** de publicação como **Publicar**.

Você também é notificado quando um desenvolvedor envia uma atualização para um aplicativo personalizado. Em seguida, você pode revisar e publicar (ou rejeitar) a atualização na página de detalhes do aplicativo. Todas as políticas de permissão de aplicativo e as políticas de configuração de aplicativos permanecem impostas para o aplicativo atualizado.

Para saber mais, confira [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativos do Teams.](submit-approve-custom-apps.md)

### <a name="upload-an-app-package"></a>Carregar um pacote do aplicativo

O desenvolvedor cria um pacote de aplicativos do [Teams usando o Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)e o envia para você no formato .zip. Quando você tiver o pacote do aplicativo, poderá enviá-lo para a loja de aplicativos da sua organização.

Para carregar um novo aplicativo personalizado, selecione **Carregar** para carregar o pacote do aplicativo. O aplicativo não é realçado depois de carregado, portanto, você precisará pesquisar a lista de aplicativos na página Gerenciar aplicativos para encontrá-lo.

Para atualizar um aplicativo depois de carregado, na lista de aplicativos na página Gerenciar aplicativos, clique no nome do aplicativo e em **Atualizar.** Isso substitui o aplicativo existente e todas as políticas de permissão de aplicativo e as políticas de configuração de aplicativos permanecem impostas para o aplicativo atualizado.

Para saber mais, confira [Publicar um aplicativo personalizado carregando um pacote de aplicativo.](upload-custom-apps.md)

## <a name="allow-and-block-apps"></a>Permitir e bloquear aplicativos

A página Gerenciar aplicativos é onde você permite ou bloqueia aplicativos individuais no nível da organização. Ele mostra todos os aplicativos disponíveis e o status atual do aplicativo no nível da organização. (Bloquear e permitir aplicativos no nível da organização foi movido do painel de configurações de **aplicativos** em toda a organização para aqui.)

Para permitir ou bloquear um aplicativo, selecione-o e clique em **Permitir** ou **Bloquear.** Quando você bloqueia um aplicativo, todas as interações com esse aplicativo são desabilitadas e o aplicativo não aparece no Teams para nenhum usuário em sua organização.

Quando você bloqueia ou permite um aplicativo na página Gerenciar aplicativos, esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização.  Quando você bloqueia ou permite um aplicativo em uma política de permissão de aplicativo do Teams, ele é bloqueado ou permitido para usuários que estão atribuídos a essa política. Para que um usuário possa instalar e interagir com qualquer aplicativo, você deve permitir o aplicativo no nível da organização na página Gerenciar aplicativos e na política de permissão do aplicativo atribuída ao usuário.

 > [!NOTE]
 > Para desinstalar um aplicativo, clique  com o botão direito do mouse no aplicativo e clique em Desinstalar ou usar o **menu** Mais aplicativos no lado esquerdo.

## <a name="add-an-app-to-a-team"></a>Adicionar um aplicativo a uma equipe

Use o botão **Adicionar à equipe** para instalar um aplicativo em uma equipe. Lembre-se de que isso é apenas para aplicativos que podem ser instalados em um escopo de equipe. O **botão Adicionar** à equipe não está disponível para aplicativos que só podem ser instalados no escopo pessoal.

![Captura de tela do botão Adicionar à equipe](media/manage-apps-add-app-team.png)

1. Pesquise o aplicativo que você deseja e selecione o aplicativo clicando à esquerda do nome do aplicativo.
2. Selecione **Adicionar à equipe**.
3. No painel **Adicionar ao painel** de equipe, pesquise a equipe à quem você deseja adicionar o aplicativo, selecione a equipe e selecione **Aplicar**.

## <a name="purchase-services-for-third-party-apps"></a>Serviços de compra para aplicativos de terceiros

Você pode pesquisar e comprar licenças para serviços oferecidos por aplicativos de terceiros para usuários em sua organização diretamente na página Gerenciar aplicativos. A **coluna Licenças** na tabela indica se um aplicativo oferece uma assinatura SaaS paga. Clique **em Comprar agora** para exibir planos e informações de preços e comprar licenças para seus usuários. Para saber mais, confira Serviços de compra para aplicativos de terceiros [do Teams no centro de administração do Microsoft Teams.](purchase-third-party-apps.md)

## <a name="grant-admin-consent-to-apps"></a>Conceder consentimento de administrador a aplicativos

Você pode revisar e conceder consentimento a aplicativos que solicitam permissões em nome de todos os usuários em sua organização. Faça isso para que os usuários não tenham que revisar e aceitar as permissões solicitadas pelo aplicativo quando iniciarem o aplicativo. A **coluna Permissões** indica se um aplicativo tem permissões que precisam de consentimento. Você verá um link **exibir detalhes** para cada aplicativo registrado no Azure AD que tenha permissões que precisam de consentimento. Para saber mais, confira [Exibir permissões do aplicativo e conceder consentimento ao administrador no centro de administração do Microsoft Teams.](app-permissions-admin-center.md)

## <a name="view-resource-specific-consent-permissions"></a>Exibir permissões de consentimento específicas do recurso

As permissões de consentimento específico do recurso (RSC) permitem que os proprietários da equipe concedam consentimento para que um aplicativo acesse e modifique os dados de uma equipe. As permissões RSC são granulares, permissões específicas do Teams que definem o que um aplicativo pode fazer em uma equipe específica. Você pode exibir permissões RSC na guia **Permissões** da página de detalhes do aplicativo para um aplicativo. Para saber mais, confira [Exibir permissões do aplicativo e conceder consentimento ao administrador no centro de administração do Microsoft Teams.](app-permissions-admin-center.md)

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativos em toda a organização

Use as configurações de aplicativos em toda a organização para controlar se os usuários podem instalar aplicativos de terceiros e se os usuários podem carregar ou interagir com aplicativos personalizados em sua organização. As configurações de aplicativos em toda a organização regem o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Você pode usá-los para controlar aplicativos mal-intencionados ou problemáticos.

> [!NOTE]
> Para saber como usar as configurações de aplicativos em toda a organização no Microsoft 365 Government - implantações GCC do Teams, consulte Gerenciar políticas de permissão de aplicativo [no Teams](teams-app-permission-policies.md).

1. Na página Gerenciar aplicativos, selecione **configurações de aplicativos em toda a organização.** Em seguida, você pode definir as configurações que deseja no painel.

    ![Captura de tela das configurações de aplicativos em toda a organização](media/manage-apps-org-wide-app-settings.png)
    
2. Em **aplicativos de** terceiros, desativar ou ativar essas configurações para controlar o acesso a aplicativos de terceiros:

    - **Permitir aplicativos de terceiros:** isso controla se os usuários podem usar aplicativos de terceiros. Se você desativar essa configuração, os usuários não poderão instalar ou usar aplicativos de terceiros e  o status do aplicativo desses aplicativos será exibido como Bloqueado em toda a organização na tabela.

        > [!NOTE]
        > Quando **Permitir aplicativos de** terceiros está desativado, os [webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) de saída são desabilitados, o que significa que os usuários não podem criar. Quando essa configuração está ativada, os webhooks de saída são habilitados para todos os usuários e você pode controlá-los no nível do usuário, permitindo ou bloqueando o aplicativo Webhook de Saída por meio de políticas de permissão de [aplicativo.](teams-app-permission-policies.md) <br><br>Observe que, se [](teams-app-permission-policies.md) você tiver políticas de permissão  de aplicativo existentes para aplicativos **da Microsoft** que usam a configuração Permitir aplicativos específicos e bloquear todos os outros, e quiser habilitar webhooks de saída para os usuários, adicione o aplicativo Webhook de Saída à lista.
    - **Permita que novos** aplicativos de terceiros publicados na loja por padrão: isso controla se novos aplicativos de terceiros publicados na loja de aplicativos do Teams ficam automaticamente disponíveis no Teams. Você só poderá definir essa opção se permitir aplicativos de terceiros.

3. Em **aplicativos personalizados,** desativar ou ativar **Permitir interação com aplicativos personalizados.** Essa configuração controla se os usuários podem interagir com aplicativos personalizados. Para saber mais, confira Gerenciar políticas e configurações [de aplicativos personalizados no Teams.](teams-custom-app-policies-and-settings.md)
4. Clique **em Salvar** para que as configurações de aplicativos em toda a organização entre em vigor.

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de administração para aplicativos no Teams](admin-settings.md)