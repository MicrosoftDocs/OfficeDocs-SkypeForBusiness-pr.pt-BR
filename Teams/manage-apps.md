---
title: Gerenciar seus aplicativos no centro de administração do Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Saiba como gerenciar aplicativos do Teams. Saiba como permitir ou bloquear aplicativos, verificar o status e as propriedades do aplicativo no nível da organização, carregar aplicativos personalizados e gerenciar as configurações do aplicativo.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5e1b5f53ba648d1096460572562b91397b74ab3b
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958056"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar aplicativos do Teams no centro de administração do Microsoft Teams

Você gerencia aplicativos para sua organização na **página de aplicativos do Teams** no portal do Centro de administração do Teams. Use a página Gerenciar aplicativos para exibir e gerenciar todos os aplicativos do Teams no catálogo de aplicativos da sua organização, atender a casos de uso proeminentes para o gerenciamento de aplicativos, definir o acesso a aplicativos usando políticas e muito mais.

:::image type="content" source="media/manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos." lightbox="media/manage-apps.png":::

Para gerenciar aplicativos, use políticas para controlar permissões para usuários, instalação de aplicativos e upload de aplicativos personalizados criados em sua organização. Para entender as políticas, consulte [Visão geral das políticas de aplicativo](app-policies.md).

Para usar o Centro de administração do Teams, você deve ter uma função de administrador global Administração ou administrador do Teams. Para obter detalhes, consulte [funções de administrador do Teams](./using-admin-roles.md) e [funções de administrador do Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> A página Gerenciar aplicativos não está disponível nas implantações do Microsoft 365 Government Community Cloud High (GCCH) ou do Departamento de Defesa (DoD) do Teams.

Durante a criação de um aplicativo, os desenvolvedores criam e adicionam uma ID do aplicativo ao arquivo de manifesto. Você pode exibir essa ID de aplicativo externo na página Gerenciar aplicativos depois de habilitar a coluna nas `External app ID` configurações de coluna. Você também pode exibi-lo na página de detalhes do aplicativo de um aplicativo personalizado. A ID é aplicável somente a aplicativos personalizados.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Casos de uso do gerenciamento de aplicativos e as interfaces disponíveis

As opções para realizar a maioria dos casos de uso do gerenciamento de aplicativos estão disponíveis no Centro de administração do Teams. Além disso, algumas opções estão disponíveis em outros portais ou páginas do centro de administração diferentes no mesmo portal.

| Casos de uso do gerenciamento de aplicativos | Vincular à interface | Documentação |
|:----|:----|:----|
| **No Centro de administração do Teams** | | |
| Controle quais aplicativos estão disponíveis para os usuários em sua organização permitindo e bloqueando aplicativos. Você também pode carregar e aprovar aplicativos personalizados. Depois de gerenciar aplicativos nesta página, você pode usar a permissão do aplicativo e as políticas de configuração de aplicativo para configurar quais aplicativos estão disponíveis para usuários específicos na loja de aplicativos da sua organização. | [Gerenciar aplicativos no Centro de administração do Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Artigo atual |
| As políticas de permissão de aplicativo controlam quais aplicativos você deseja disponibilizar para os usuários do Teams em sua organização. Você pode usar a política padrão global (em toda a organização) e personalizá-la, ou pode criar uma ou mais políticas para atender às necessidades da sua organização. | [Políticas de permissão](https://admin.teams.microsoft.com/policies/app-permission) | [Gerenciar políticas de permissão de aplicativo](teams-app-permission-policies.md) |
| As políticas de configuração de aplicativo controlam como os aplicativos são disponibilizados para um usuário com o aplicativo Teams. Use a política Global (padrão em toda a organização) e personalize-a ou crie políticas personalizadas e atribua-as a um conjunto de usuários. | [Políticas de instalação](https://admin.teams.microsoft.com/policies/app-setup) | [Gerenciar políticas de configuração de aplicativo](teams-app-setup-policies.md) |
| Você pode desenvolver e carregar aplicativos personalizados como pacotes de aplicativos e dispo-los na loja de aplicativos da sua organização. | Configurações de aplicativo em toda a organização em [Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps) | [Gerenciar políticas de aplicativo personalizadas](teams-custom-app-policies-and-settings.md) |
| Você pode personalizar a loja de aplicativos do Teams com o logotipo, a tela de fundo personalizada ou a cor da sua organização. | [Personalizar repositório](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personalizar a loja de aplicativos da sua organização](customize-your-app-store.md) |
| O relatório de uso do aplicativo Teams fornece informações sobre quais aplicativos em uso, usuários ativos e outras informações de uso do aplicativo. | [Relatórios de uso](https://admin.teams.microsoft.com/analytics/reports) | [Relatório de uso de aplicativos do Teams](teams-analytics-and-reports/app-usage-report.md) |
| Os usuários podem adicionar aplicativos quando hospedam reuniões ou chats com convidados. Eles também podem usar aplicativos compartilhados por convidados quando ingressam em reuniões ou chats hospedados externamente. As políticas de dados da organização do usuário de hospedagem e as práticas de compartilhamento de dados de quaisquer aplicativos de terceiros compartilhados pela organização desse usuário são aplicadas. | [Acesso externo](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [Comportamento do aplicativo, dependendo dos tipos de usuários](non-standard-users.md) |
| Com o acesso de convidados, você pode fornecer acesso a aplicativos e outras funcionalidades do Teams para pessoas de fora da sua organização, mantendo o controle sobre seus dados corporativos. | [Acesso de convidados](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Acesso de convidados ao Teams](guest-access.md) |
| As políticas de atualização são usadas para gerenciar usuários de visualização do Teams e do Office que verão recursos de pré-lançamento ou versão prévia no aplicativo Teams.  | [Políticas de atualização do Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Visualização pública do Teams](public-preview-doc-updates.md) |
| **Centro de administração fora do Teams** | | |
| Gerenciar licenças e assinaturas de aplicativos de terceiros no Centro de administração do Microsoft 365 | [Centro de administração do Microsoft 365](https://admin.microsoft.com/#/licenses) | [Gerenciar assinaturas de aplicativo de terceiros](/microsoft-365/commerce/manage-saas-apps) |
| Auditar eventos de aplicativo do Teams portal de conformidade do Microsoft Purview. | [Auditoria](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Atividades do Teams](audit-app-management-activities.md) |
| Os aplicativos podem receber permissões para sua organização e seus dados por três métodos: um administrador consente com o aplicativo para todos os usuários, um usuário concede consentimento ao aplicativo ou um administrador integrando um aplicativo e habilitando o acesso de autoatendimento ou atribuindo usuários diretamente ao aplicativo. Verifique as permissões do Graph para aplicativos. Verifique as permissões que os usuários forneceram ou que os administradores delegaram. | [Azure AD portal](https://aad.portal.azure.com/) | [Examinar as permissões concedidas a aplicativos](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>Permitir e bloquear aplicativos

A página Gerenciar aplicativos é onde você permite ou bloqueia aplicativos individuais no nível da organização. A página exibe todo o aplicativo disponível e o status atual do aplicativo no nível da organização. A lista de aplicativos inclui aplicativos fornecidos pela Microsoft, por desenvolvedores de terceiros e por desenvolvedores em sua organização.

Para permitir ou bloquear um aplicativo:

1. Entre no Centro de administração do Teams.
1. Página Gerenciar **aplicativos do Access Teams** > .**[](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Selecione um aplicativo na lista de aplicativos. Você pode pesquisar pelo nome do aplicativo e, em seguida, selecioná-lo.
1. Selecione **a opção** Permitir **ou** Bloquear.

Quando você permite (ou bloqueia) um aplicativo na página [](https://admin.teams.microsoft.com/policies/manage-apps) Gerenciar aplicativos no Centro de administração do Teams, o aplicativo específico é permitido (ou bloqueado) para todos os usuários em sua organização. Esse método difere da política de permissão do aplicativo no contexto que permitir (ou bloquear) um aplicativo por meio da política de permissão afeta apenas os usuários específicos que recebem a política.

Um usuário pode instalar e usar um aplicativo somente quando o aplicativo é permitido por meio da configuração em todo o locatário e permitido para o usuário por meio da política de permissão.

## <a name="manage-user-requests-to-unblock-apps"></a>Gerenciar solicitações de usuário para desbloquear aplicativos

Você pode exibir solicitações para disponibilizar um aplicativo bloqueado para uso. A solicitação é enviada ao administrador de TI, que pode exibir e gerenciar solicitações de usuário no centro de administração do Teams.

  :::image type="content" source="media/user-request.png" alt-text="Fazer uma solicitação de aprovação de aplicativos bloqueados":::

### <a name="view-a-request"></a>Exibir uma solicitação

 1. Entre no centro de administração do Teams e selecione [Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)

    :::image type="content" source="media/requested-apps1.png" alt-text="As solicitações do usuário final para aplicativos bloqueados são exibidas no centro de administração do Teams na coluna intitulitada Solicitações por usuários." lightbox="media/requested-apps.png":::

 1. Para exibir e verificar o número de solicitações para cada aplicativo, classifique as solicitações na coluna **Solicitações por** usuário.
 1. Selecione o nome do aplicativo que você deseja desbloquear e ele abrirá a página de detalhes do aplicativo.
 1. Selecione **Gerenciar solicitações** e conclua as etapas exibidas na caixa de diálogo pop-up. As etapas para aprovar um aplicativo variam de acordo com o método usado para bloqueiá-lo.

    * Se o aplicativo for bloqueado usando políticas de permissão, permita que o aplicativo modifique as [políticas de permissão](teams-app-permission-policies.md).
    * Se o aplicativo estiver bloqueado para todos os usuários, [permita o aplicativo](#allow-and-block-apps).
    * Se todos os aplicativos forem bloqueados para todos os usuários, modifique [as configurações de toda a organização](#manage-org-wide-app-settings).

 Se um administrador permitir um aplicativo, ele não informará ao usuário final que a solicitação foi acionda. O usuário deve visitar o aplicativo na Loja para verificar se o aplicativo está desbloqueado ou não.

### <a name="dismiss-a-user-request"></a>Ignorar uma solicitação de usuário

 1. Selecione o nome do aplicativo para o qual você deseja ignorar as solicitações do usuário.
 1. Selecione **Gerenciar solicitações** e **selecione Ignorar todas as solicitações** na caixa de diálogo.
 1. Quando uma solicitação é ignorada, ela redefine as solicitações do usuário para zero.

  :::image type="content" source="media/reject.png" alt-text="rejeição de aplicativos bloqueados."border="true":::

Se um administrador ignorar uma solicitação, ele não informará ao usuário final que a solicitação foi acionda. O usuário deve visitar o aplicativo na Loja para verificar se o aplicativo está desbloqueado ou não.

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>Permitir os aplicativos bloqueados pelos desenvolvedores

Quando um desenvolvedor publica um aplicativo na loja de aplicativos do Teams, pode ser necessário que os administradores configurem ou personalizem a experiência do aplicativo. Os administradores disponibilizam a experiência para os usuários finais quando o aplicativo é configurado.

Por exemplo, a Contoso Electronics é um ISV que criou um aplicativo de suporte ajuda para o Microsoft Teams. A Contoso Electronics deseja que seus clientes configurem determinadas propriedades do aplicativo para que, quando os usuários interajam com o aplicativo, ele funcione conforme o esperado. Antes que um administrador possa permitir ou bloquear o aplicativo, ele será exibido  como Bloqueado pelo editor no centro de administração do Teams e ficará oculto dos usuários finais por padrão. Depois de seguir as diretrizes do editor para configurar o aplicativo, você pode dispo-lo para os usuários alterando o status para **Permitido**.

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Captura de tela do bloqueio pelo status do editor no Centro de administração do Teams.":::

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativo em toda a organização

Use as configurações de aplicativo em toda a organização para controlar se os usuários com uma licença [F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtêm a experiência de aplicativo de linha de frente personalizada, se os usuários podem instalar aplicativos de terceiros e se os usuários podem carregar ou interagir com aplicativos personalizados em sua organização. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Você pode usá-los para controlar aplicativos maliciosos ou problemáticos.

> [!NOTE]
> Para saber como usar as configurações de aplicativo em toda a organização nas implantações do Microsoft 365 Government – Government Community Cloud High GCCH e do Departamento de Defesa (DoD) do Teams, consulte Gerenciar políticas de permissão de aplicativo no [Teams](teams-app-permission-policies.md).

1. Na página Gerenciar aplicativos, selecione **configurações de aplicativo em toda a organização**. Em seguida, você pode definir as configurações desejadas no painel.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Captura de tela do painel configurações de aplicativos em toda a organização na página Gerenciar aplicativos":::

1. Em **aplicativos personalizados**, desative ou ative **Mostrar aplicativos personalizados**. Quando essa configuração está ativada, os usuários com uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtêm a experiência de aplicativo de linha de frente personalizada. Essa experiência fixa os aplicativos mais relevantes no Teams para trabalhadores da linha de frente. Para saber mais, confira [Personalizar aplicativos do Teams para seus funcionários da linha de frente](pin-teams-apps-based-on-license.md).

    Esse recurso está disponível para licenças F. Outros tipos de licença terão suporte no futuro.
1. Em **Aplicativos de terceiros**, desabilite ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    * **Permitir aplicativos de terceiros**: controla se os usuários podem usar aplicativos de terceiros. Se você desativar essa configuração, os usuários não poderão instalar nem usar aplicativos de terceiros, e o status do aplicativo desses aplicativos será exibido como Bloqueado em toda a  organização na tabela.

        > [!NOTE]
        > Quando Permitir aplicativos de terceiros está desativado, os [webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) de saída ainda estão habilitados para todos os usuários, mas você pode **controlá-los** no nível do usuário permitindo ou bloqueando o aplicativo webhook de saída por meio de políticas de permissão de [aplicativo.](teams-app-permission-policies.md) Observe que, se você tiver políticas [](teams-app-permission-policies.md) de permissão de aplicativo existentes para aplicativos  da **Microsoft** que usam a configuração Permitir aplicativos específicos e bloquear todos os outros, e quiser habilitar webhooks de saída para os usuários, adicione o aplicativo Webhook de Saída à lista.

        > [!NOTE]
        > Os usuários do Teams podem adicionar aplicativos ao hospedar reuniões ou chats com pessoas de outras organizações. Eles também podem usar aplicativos compartilhados por pessoas de outras organizações quando ingressarem em reuniões ou chats hospedados por essas organizações. As políticas de dados da organização do usuário de hospedagem, assim como as práticas de compartilhamento de dados de qualquer aplicativo de terceiros compartilhado pela organização desse usuário, serão aplicadas.

    * **Permitir novos aplicativos de terceiros publicados na loja por padrão**: isso controla se os novos aplicativos de terceiros publicados na loja de aplicativos Teams se tornam automaticamente disponíveis no Teams. Você só pode definir essa opção se permitir aplicativos de terceiros.

1. Em **Aplicativos personalizados**, desative ou ative **Permitir interação com aplicativos personalizados**. Essa configuração controla se os usuários podem interagir com aplicativos personalizados. Para saber mais, confira [Gerenciar políticas e configurações de aplicativos personalizados no Teams](teams-custom-app-policies-and-settings.md).
1. Selecione **Salvar** para que as configurações de aplicativo em toda a organização entre em vigor.

## <a name="related-article"></a>Artigo relacionado

* [Gerenciar o Teams durante a transição do Skype for Business de administração](manage-teams-skypeforbusiness-admin-center.md)
