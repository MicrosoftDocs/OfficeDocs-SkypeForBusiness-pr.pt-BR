---
title: Gerenciar seus aplicativos no Centro de administração do Microsoft Teams
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
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar seus aplicativos no Centro de administração do Microsoft Teams
======================================================

Como administrador, a página Gerenciar aplicativos no Centro de administração do Microsoft Teams é onde você visualiza e gerencia todos os aplicativos do Teams para sua organização. Aqui, você pode ver o status no nível da organização e as propriedades dos aplicativos, aprovar ou carregar novos aplicativos personalizados na loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização, adicionar aplicativos às equipes, comprar serviços para aplicativos de terceiros, exibir permissões solicitadas por aplicativos, conceder autorização de administrador aos aplicativos e gerenciar configurações de aplicativos de toda a organização.

A página Gerenciar aplicativos oferece uma exibição em todos os aplicativos disponíveis, fornecendo as informações necessárias para decidir quais aplicativos permitir ou bloquear em toda a organização. Em seguida, [você](teams-app-permission-policies.md)pode usar políticas de permissão de [aplicativo,](teams-app-setup-policies.md)políticas de configuração de aplicativos e políticas e configurações personalizadas do aplicativo para configurar a experiência do aplicativo para usuários [específicos](teams-custom-app-policies-and-settings.md) em sua organização.

Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.** Você deve ser um administrador global ou administrador de serviços do Teams para acessar a página.

> [!NOTE]
> A página Gerenciar aplicativos ainda não está disponível nas implantações do Microsoft 365 Government Community Cloud (GCC) do Teams.

## <a name="view-apps"></a>Exibir aplicativos

Você pode exibir todos os aplicativos, incluindo as seguintes informações sobre cada aplicativo.

![Captura de tela da página Aplicativos gerenciados](media/manage-apps.png)

- **Nome:** o nome do aplicativo. Clique no nome do aplicativo para ir para a página de detalhes do aplicativo para ver mais informações sobre o aplicativo. Isso inclui uma descrição do aplicativo, seja ele permitido ou bloqueado, versão, política de privacidade, termos de uso, categorias que se aplicam ao aplicativo, status de certificação, recursos com suporte e ID do aplicativo. Veja um exemplo:

  ![Captura de tela da página de detalhes de aplicativos de um aplicativo](media/manage-apps-app-details.png)
  
- **Certificação:** se o aplicativo passou pela certificação, você verá o certificado **do Microsoft 365** ou **o teste do Publisher.** Clique no link para exibir os detalhes da certificação do aplicativo. Se você vir **--** "", não temos informações de certificação para o aplicativo. Para saber mais sobre aplicativos certificados no Teams, leia o programa de certificação de [aplicativos microsoft 365.](https://docs.microsoft.com/teams-app-certification/all-apps)  
- **Publisher**: Nome do editor.
- **Status de publicação:** status de publicação de aplicativos personalizados.
- **Status:** Status do aplicativo no nível da organização, que pode ser um dos seguintes:

    - **Permitido:** o aplicativo está disponível para todos os usuários em sua organização.
    
    - **Bloqueado:** o aplicativo está bloqueado e não está disponível para os usuários em sua organização.
    
    - **Toda a organização bloqueada:** o aplicativo é bloqueado nas configurações do aplicativo em toda a organização.
    
      É importante saber que essa coluna representa o status permitido e bloqueado dos **aplicativos** que anteriormente estavam no painel de configurações de toda a organização. Agora você pode exibir, bloquear e permitir aplicativos em toda a organização na página **Gerenciar aplicativos.** 
- **Licenças:** indica se um aplicativo oferece uma assinatura de Software como serviço (SaaS) para compra. Esta coluna aplica-se somente a aplicativos de terceiros. Cada aplicativo de terceiros terá um dos seguintes valores:
    - **Compre agora:** o aplicativo oferece uma assinatura do SaaS e está disponível para compra.  
    - **Comprado:** o aplicativo oferece uma assinatura do SaaS e você comprou licenças para ele.
    - **- -** O aplicativo não oferece uma assinatura SaaS.
- **Aplicativo personalizado:** se o aplicativo é um aplicativo personalizado.
- **Permissões:** indica se um aplicativo personalizado ou de terceiros registrado no Azure Active Directory (Azure AD) tem permissões que precisam de consentimento. Você verá um dos seguintes valores:
    - **Exibir detalhes:** o aplicativo tem permissões que exigem consentimento antes que o aplicativo possa acessar dados. 
    - **- -** O aplicativo não tem permissões que precisam de consentimento.
- **Categorias:** categorias que se aplicam ao aplicativo.
- **Versão:** Versão do aplicativo.

Para ver as informações que você  deseja na tabela, clique em Editar Coluna no canto superior direito para adicionar ou remover colunas à tabela.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publicar um aplicativo personalizado na loja de aplicativos da sua organização

Use a página Gerenciar aplicativos para publicar aplicativos criados especificamente para sua organização. Depois de publicar um aplicativo personalizado, ele estará disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado na loja de aplicativos da sua organização. A maneira que você usa depende de como você obter o aplicativo.

- [Aprovar um aplicativo personalizado:](#approve-a-custom-app)use este método se o desenvolvedor enviar o aplicativo diretamente para a página Gerenciar aplicativos usando a API de Envio de Aplicativos do Teams. Em seguida, você pode revisar e publicar (ou rejeitar) o aplicativo diretamente na página de detalhes do aplicativo.
- [Carregar um pacote de aplicativos:](#upload-an-app-package)use este método se o desenvolvedor enviar o pacote de aplicativos no formato .zip. Você publica o aplicativo carregando o pacote de aplicativos.

###  <a name="approve-a-custom-app"></a>Aprovar um aplicativo personalizado

O **widget aprovações pendentes** na página Gerenciar aplicativos o notifica quando um desenvolvedor envia um aplicativo usando a API de envio de aplicativos do Teams. Um aplicativo recém-enviado é listado com um **status de** Publicação enviado **e** **um Status** de **Bloqueado.** Vá para a página de detalhes do aplicativo para ver mais informações sobre o aplicativo e, em seguida, para publicá-lo, de definir **o status** de Publicação como **Publicar.**

Você também será notificado quando um desenvolvedor enviar uma atualização para um aplicativo personalizado. Em seguida, você pode revisar e publicar (ou rejeitar) a atualização na página de detalhes do aplicativo. Todas as políticas de permissão de aplicativo e as políticas de configuração de aplicativo permanecem aplicadas para o aplicativo atualizado.

Para saber mais, confira [Publicar um aplicativo personalizado enviado por meio da API de envio de aplicativos do Teams.](submit-approve-custom-apps.md)

### <a name="upload-an-app-package"></a>Carregar um pacote de aplicativos

O desenvolvedor cria um pacote de aplicativos do Teams usando o [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)e o envia para você no formato .zip. Quando você tiver o pacote de aplicativos, poderá carregar o pacote na loja de aplicativos da sua organização.

Para carregar um novo aplicativo personalizado, selecione **Carregar** para carregar o pacote de aplicativos. O aplicativo não é realçado depois de carregado, portanto, você precisará pesquisar a lista de aplicativos na página Gerenciar aplicativos para encontrá-lo.

Para atualizar um aplicativo depois de carregado, na lista de aplicativos na página Gerenciar aplicativos, clique no nome do aplicativo e clique em **Atualizar.** Isso substitui o aplicativo existente e todas as políticas de permissão do aplicativo e as políticas de configuração do aplicativo permanecem impostas para o aplicativo atualizado.

Para saber mais, confira [Publicar um aplicativo personalizado carregando um pacote de aplicativos.](upload-custom-apps.md)

## <a name="allow-and-block-apps"></a>Permitir e bloquear aplicativos

A página Gerenciar aplicativos é onde você permite ou bloqueia aplicativos individuais no nível da organização. Ele mostra todos os aplicativos disponíveis e seu status atual do aplicativo no nível da organização. (O bloqueio e a permissão de aplicativos no nível da organização foram movidos do painel de configurações de **aplicativos** de toda a organização para aqui.)

Para permitir ou bloquear um aplicativo, selecione-o e clique em **Permitir** ou **Bloquear.** Quando você bloqueia um aplicativo, todas as interações com esse aplicativo são desabilitadas e o aplicativo não aparece no Teams para nenhum usuário em sua organização.

Quando você bloqueia ou permite um aplicativo na página Gerenciar aplicativos, esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização.  Quando você bloqueia ou permite um aplicativo em uma política de permissão do aplicativo Teams, ele é bloqueado ou permitido para os usuários que estão atribuídos a essa política. Para que um usuário possa instalar e interagir com qualquer aplicativo, você deve permitir o aplicativo no nível da organização na página Gerenciar aplicativos e na política de permissão do aplicativo atribuída ao usuário.

 > [!NOTE]
 > Para desinstalar um aplicativo, clique  com o botão direito do mouse no aplicativo e clique em Desinstalar ou usar o **menu** Mais aplicativos no lado esquerdo.

## <a name="add-an-app-to-a-team"></a>Adicionar um aplicativo a uma equipe

Use o **botão Adicionar à equipe** para instalar um aplicativo em uma equipe. Lembre-se de que isso se aplica somente a aplicativos que podem ser instalados em um escopo de equipe. O **botão Adicionar à equipe** não está disponível para aplicativos que só podem ser instalados no escopo pessoal.

![Captura de tela do botão Adicionar à equipe](media/manage-apps-add-app-team.png)

1. Pesquise o aplicativo que você deseja e selecione o aplicativo clicando à esquerda do nome do aplicativo.
2. Selecione **Adicionar à equipe.**
3. No painel **Adicionar à equipe,** procure a equipe à quem você deseja adicionar o aplicativo, selecione a equipe e selecione **Aplicar.**

## <a name="purchase-services-for-third-party-apps"></a>Serviços de compra para aplicativos de terceiros

Você pode pesquisar e comprar licenças para serviços oferecidos por aplicativos de terceiros para usuários em sua organização diretamente na página Gerenciar aplicativos. A **coluna Licenças** na tabela indica se um aplicativo oferece uma assinatura saaS paga. Clique **em Comprar agora** para exibir planos e informações sobre preços e comprar licenças para seus usuários. Para saber mais, consulte Comprar serviços para aplicativos de terceiros do [Teams no Centro de administração do Microsoft Teams.](purchase-third-party-apps.md)

## <a name="grant-admin-consent-to-apps"></a>Conceder autorização de administrador a aplicativos

Você pode revisar e conceder consentimento aos aplicativos que solicitam permissões em nome de todos os usuários em sua organização. Faça isso para que os usuários não tenham que revisar e aceitar as permissões solicitadas pelo aplicativo quando eles iniciarem o aplicativo. A **coluna Permissões** indica se um aplicativo tem permissões que precisam de consentimento. Você verá um **link** exibir detalhes para cada aplicativo registrado no Azure AD que tenha permissões que precisam de consentimento. Para saber mais, consulte Exibir permissões do aplicativo e conceder autorização de [administrador no Centro de administração do Microsoft Teams.](app-permissions-admin-center.md)

## <a name="view-resource-specific-consent-permissions"></a>Exibir permissões de consentimento específicas do recurso

As permissões RSC (consentimento específico do recurso) permitem que os proprietários da equipe concedam o consentimento de um aplicativo para acessar e modificar os dados de uma equipe. As permissões RSC são permissões granulares específicas do Teams que definem o que um aplicativo pode fazer em uma equipe específica. Você pode exibir permissões RSC na **guia Permissões** da página de detalhes do aplicativo para um aplicativo. Para saber mais, consulte Exibir permissões do aplicativo e conceder autorização de [administrador no Centro de administração do Microsoft Teams.](app-permissions-admin-center.md)

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativos de toda a organização

Use as configurações de aplicativos de toda a organização para controlar se os usuários podem instalar aplicativos de terceiros e se os usuários podem carregar ou interagir com aplicativos personalizados em sua organização. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Você pode usá-los para controlar aplicativos maliciosos ou problemáticos.

> [!NOTE]
> Para saber como usar as configurações de aplicativos de toda a organização no Microsoft 365 Government – implantações de GCC do Teams, consulte Gerenciar políticas de permissão de aplicativo [no Teams.](teams-app-permission-policies.md)

1. Na página Gerenciar aplicativos, selecione Configurações do aplicativo em **toda a organização.** Você pode então definir as configurações desejadas no painel.

    ![Captura de tela das configurações do aplicativo para toda a organização](media/manage-apps-org-wide-app-settings.png)
    
2. Em **Aplicativos de terceiros**, desabilite ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    - **Permitir aplicativos de terceiros**: controla se os usuários podem usar aplicativos de terceiros. Se você desativar essa configuração, os usuários não poderão instalar ou usar aplicativos de terceiros,  e o status do aplicativo desses aplicativos será exibido como bloqueado em toda a organização na tabela.

        > [!NOTE]
        > Quando **Permitir aplicativos de** terceiros está desativado, as [webções](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) de saída são desabilitadas, o que significa que os usuários não podem criar esses aplicativos. Quando essa configuração está ativada, as web browsers de saída são habilitadas para todos os usuários e você pode controlá-las no nível do usuário, permitindo ou bloqueando o aplicativo Outgoing Web parental por meio de políticas de permissão do [aplicativo.](teams-app-permission-policies.md) <br><br>Observe que se você [](teams-app-permission-policies.md) tiver políticas de permissão  de aplicativos existentes para aplicativos da **Microsoft** que usam os aplicativos específicos e bloqueiam todas as outras configurações, e se você quiser habilitar webções de saída para os usuários, adicione o aplicativo Webção de Saída à lista.
    - **Permitir novos aplicativos de terceiros publicados na loja por padrão**: isso controla se os novos aplicativos de terceiros publicados na loja de aplicativos Teams se tornam automaticamente disponíveis no Teams. Você só pode definir essa opção se permitir aplicativos de terceiros.

3. Em **Aplicativos personalizados,** desativar ou ativar **Permitir interação com aplicativos personalizados.** Essa configuração controla se os usuários podem interagir com aplicativos personalizados. Para saber mais, confira [Gerenciar políticas e configurações de aplicativos personalizados no Teams](teams-custom-app-policies-and-settings.md).
4. Clique em **Salvar** para que as configurações do aplicativo para toda a organização tenham efeito.

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de administrador para aplicativos no Teams](admin-settings.md)