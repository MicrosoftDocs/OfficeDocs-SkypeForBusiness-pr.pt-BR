---
title: Gerenciar seus aplicativos no centro de administração do Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.reviewer: kojika
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Saiba como gerenciar aplicativos do Teams. Saiba como permitir ou bloquear aplicativos, verificar o status no nível da organização e as propriedades do aplicativo, carregar aplicativos personalizados e gerenciar as configurações do aplicativo.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 053164da8a521566247e982b09f5f929fe6da406
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912610"
---
# <a name="overview-of-app-management-and-governance-in-teams-admin-center"></a>Visão geral do gerenciamento de aplicativos e governança no centro de administração do Teams

Gerencie aplicativos para sua organização na página de **aplicativos do Teams** no portal do Centro de administração do Teams. Use a página Gerenciar aplicativos para exibir e gerenciar todos os aplicativos do Teams no catálogo de aplicativos da sua organização, atender a casos de uso proeminentes para gerenciamento de aplicativos, definir o acesso a aplicativos usando políticas e muito mais.

:::image type="content" source="media/manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos" lightbox="media/manage-apps.png":::

Para gerenciar aplicativos, use políticas para controlar permissões para usuários, instalar aplicativos e fazer upload de aplicativos personalizados criados em sua organização. Para entender as políticas, consulte [Visão geral das políticas de aplicativo](app-policies.md).

Para usar o Centro de administração do Teams, você deve ter uma função de Administrador Global ou Administrador do Teams. Para obter detalhes, consulte [Funções de administrador do Teams](./using-admin-roles.md) [ funções de administrador do Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> A página Gerenciar aplicativos não está disponível nas implantações da Nuvem da Comunidade Governamental do GCCH (High) do Microsoft 365 ou do DoD (Departamento de Defesa) do Teams.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Casos de uso do gerenciamento de aplicativos e as interfaces disponíveis

As opções para realizar a maioria dos casos de uso do gerenciamento de aplicativos estão disponíveis no Centro de administração do Teams. Além disso, algumas opções estão disponíveis em outros portais ou páginas diferentes no centro de administração do Teams.

As tarefas de gerenciamento de aplicativos com suporte no centro de administração estão na tabela abaixo.

| Casos de uso do gerenciamento de aplicativos | Vincular à interface | Documentação |
|:----|:----|:----|
| Controle quais aplicativos estão disponíveis para os usuários em sua organização permitindo e bloqueando aplicativos. Você também pode carregar e aprovar aplicativos personalizados. Depois de gerenciar aplicativos nesta página, você pode usar a permissão do aplicativo e as políticas de configuração do aplicativo para configurar quais aplicativos estão disponíveis para usuários específicos na loja de aplicativos da sua organização. | [Gerenciar aplicativos no Centro de administração do Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Artigo atual |
| As políticas de permissão de aplicativo controlam quais aplicativos você deseja disponibilizar para os usuários do Teams em sua organização. Você pode usar a política Global (para toda a organização) e personalizá-la ou pode criar uma ou mais políticas para atender às necessidades da sua organização. | [Políticas de permissão](https://admin.teams.microsoft.com/policies/app-permission) | [Gerenciar políticas de permissão de aplicativo](teams-app-permission-policies.md) |
| As políticas de configuração de aplicativos controlam como os aplicativos são disponibilizados para um usuário com o aplicativo Teams. Utilize a política Global (padrão de toda a organização) e personalize-a ou crie políticas personalizadas e atribua-as a um conjunto de usuários. | [Políticas de instalação](https://admin.teams.microsoft.com/policies/app-setup) | [Gerenciar políticas de configuração de aplicativo](teams-app-setup-policies.md) |
| Você pode desenvolver e carregar aplicativos personalizados como pacotes de aplicativos e disponibilizá-los na loja de aplicativos da sua organização.  | Configurações de aplicativos em toda a organização em [Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps) | [Gerenciar a configuração de política para aplicativos personalizados](teams-custom-app-policies-and-settings.md) |
| Você pode personalizar a loja de aplicativos do Teams com o logotipo da sua organização e plano de fundo personalizado ou cores. | [Personalizar repositório](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personalizar a loja de aplicativos da sua organização](customize-your-app-store.md) |
| O relatório de uso do aplicativo do Teams fornece informações sobre aplicativos em uso, usuários ativos e outras informações de uso do aplicativo. | [Relatórios de uso](https://admin.teams.microsoft.com/analytics/reports) | [Relatório de uso do Teams](teams-analytics-and-reports/app-usage-report.md) |
| Os usuários podem adicionar aplicativos quando hospedam reuniões ou chats com convidados. Eles também podem usar aplicativos compartilhados por convidados quando ingressam em reuniões ou chats hospedados externamente. As políticas de dados da organização do usuário de hospedagem e as práticas de compartilhamento de dados de qualquer aplicativo de terceiros compartilhado pela organização desse usuário, serão aplicadas. | [Acesso externo](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [Comportamento do aplicativo, dependendo dos tipos de usuários](non-standard-users.md) |
| Com o acesso de convidados, você pode fornecer acesso a aplicativos e outras funcionalidades do Teams para pessoas de fora da sua organização, mantendo o controle sobre seus dados corporativos. | [Acesso de convidados](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Acesso de convidados ao Teams](guest-access.md) |
| As políticas de atualização do Teams são usadas para gerenciar usuários de versão prévia do Teams e do Office que podem ver recursos de pré-lançamento ou visualização no aplicativo Teams. | [Políticas de atualização do Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Visualização pública do Teams](public-preview-doc-updates.md) |

As tarefas de gerenciamento de aplicativos com suporte em outros portais estão na tabela abaixo.

| Casos de uso do gerenciamento de aplicativos | Vincular à interface | Documentação |
|:----|:----|:----|
| Gerenciar licenças e assinaturas de aplicativos de terceiros no Microsoft 365 de administração | [Centro de administração do Microsoft 365](https://admin.microsoft.com/#/licenses) | [Gerenciar assinaturas de aplicativos de terceiros](/microsoft-365/commerce/manage-saas-apps) |
| Auditar eventos de aplicativo do Teams no portal de conformidade do Microsoft Purview. | [Auditoria](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Atividades do Teams](audit-app-management-activities.md) |
| Os aplicativos podem receber permissões para sua organização e seus dados por três métodos: um administrador consente com o aplicativo para todos os usuários, um usuário dá consentimento ao aplicativo ou um administrador integra um aplicativo e habilita o acesso de autoatendimento ou atribui usuários diretamente ao aplicativo. Verifique as permissões do Graph para aplicativos. Verifique as permissões que os usuários forneceram ou que os administradores delegaram. | [Portal do Azure AD](https://aad.portal.azure.com/) | [Examinar as permissões concedidas aos aplicativos](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>Permitir e bloquear aplicativos

Como administrador, você controla o acesso a todos os tipos de aplicativos que são usados em todo o contexto por todos os usuários. O Teams fornece controles granulares para configurar o acesso para cada aplicativo e para cada usuário.

Para permitir um aplicativo, todas as configurações a seguir devem ser feitas. Para bloquear um aplicativo, bloqueie-o por meio de qualquer uma das configurações a seguir.

* [Configurações de aplicativo em toda a](manage-apps.md#manage-org-wide-app-settings) organização: use essa configuração para permitir o uso de aplicativos em sua organização. Você decide quais aplicativos específicos são usados.
* [Permitir um aplicativo individual](manage-apps.md#allow-and-block-apps): use essa configuração para permitir um aplicativo específico em sua organização. Você decide quais usuários podem usar o aplicativo.
* [Política de permissão](teams-app-permission-policies.md) do aplicativo: use políticas para permitir que todos ou permitir que usuários específicos usem um aplicativo. Você decide o acesso por usuário e por aplicativo.

A página Gerenciar aplicativos é onde você gerencia aplicativos individuais no nível da organização. A página exibe os aplicativos disponíveis e o status atual do aplicativo no nível da organização. Para permitir ou bloquear um aplicativo, siga estas etapas:

1. Entre no centro de administração do Teams e acesse aplicativos  > **do Teams****[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Localize um aplicativo e selecione-o.
1. Selecione a opção **Permitir** ou **Bloquear**.

Para permitir um aplicativo para usuários específicos, consulte [políticas de permissão do aplicativo](teams-app-permission-policies.md).

Quando um desenvolvedor publica um aplicativo na loja do Teams, alguns aplicativos podem precisar de um administrador para configurar o aplicativo. Antes que um administrador permita esse aplicativo, ele é mostrado como `Blocked by publisher` no centro de administração. Depois de seguir as diretrizes do editor para configurar o aplicativo, você pode disponibilizá-lo aos usuários permitindo-o.

## <a name="manage-org-wide-app-settings"></a>Gerenciar configurações de aplicativos em toda a organização

Use as configurações de aplicativo em toda a organização para controlar se os usuários com uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtêm a experiência personalizada do aplicativo de linha de frente, se os usuários podem instalar aplicativos de terceiros e se os usuários podem carregar ou interagir com aplicativos personalizados em sua organização.

> [!NOTE]
> Para saber como usar as configurações de aplicativo em toda a organização nas implantações da Nuvem da Comunidade Governamental do GCCH (High) do Microsoft 365 ou do DoD (Departamento de Defesa) do Teams, consulte Gerenciar políticas de permissão de aplicativo no [Teams](teams-app-permission-policies.md).

1. Na página **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)** , selecione **Configurações de aplicativo em toda a organização**. Você pode então definir as configurações desejadas no painel.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Captura de tela do painel configurações de aplicativos de toda a organização na página Gerenciar aplicativos":::

1. Em **Aplicativos personalizados**, habilite ou desabilite **Mostrar aplicativos personalizados**. Quando essa configuração está ativada, os usuários com uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtêm a experiência de aplicativo de linha de frente personalizada. Essa experiência fixa os aplicativos mais relevantes no Teams para os trabalhadores de linha de frente. Para saber mais, confira [Personalizar aplicativos do Teams para seus funcionários de linha de frente](pin-teams-apps-based-on-license.md).

    Esse recurso está disponível para licenças F. Outros tipos de licença terão suporte no futuro.
1. Em **Aplicativos de terceiros**, desabilite ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    * **Permitir aplicativos de terceiros**: controla se os usuários podem usar aplicativos de terceiros. Se você desativar essa configuração, os usuários não poderão instalar ou usar aplicativos de terceiros, e o status desses aplicativos será exibido como **Bloqueado em toda a organização** na tabela.

        > [!NOTE]
        > Quando os **Permitir aplicativos de terceiros** estão desativados, os [webhooks de saída](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ainda estão habilitados para todos os usuários, mas você pode controlá-los no nível do usuário permitindo ou bloqueando o aplicativo Webhook de Saída por meio de [políticas de permissão de aplicativo](teams-app-permission-policies.md). Observe que, se você tiver [políticas de permissão de aplicativo](teams-app-permission-policies.md) existentes para **aplicativos da Microsoft** que usam a configuração **Permitir aplicativos específicos e bloquear todos os outros** e quiser habilitar webhooks de saída para os usuários, adicione o aplicativo Webhook de Saída à lista.

        > [!NOTE]
        > Os usuários do Teams podem adicionar aplicativos ao hospedar reuniões ou chats com pessoas de outras organizações. Eles também podem usar aplicativos compartilhados por pessoas de outras organizações quando ingressarem em reuniões ou chats hospedados por essas organizações. As políticas de dados da organização do usuário de hospedagem, assim como as práticas de compartilhamento de dados de qualquer aplicativo de terceiros compartilhado pela organização desse usuário, serão aplicadas.

    * **Permitir novos aplicativos de terceiros publicados na loja por padrão**: isso controla se os novos aplicativos de terceiros publicados na loja de aplicativos Teams se tornam automaticamente disponíveis no Teams. Você só pode definir essa opção se permitir aplicativos de terceiros.

1. Em **Aplicativos personalizados**, desative ou ative **Permitir interação com aplicativos personalizados**. Essa configuração controla se os usuários podem interagir com aplicativos personalizados. Para saber mais, confira [Gerenciar políticas e configurações para aplicativos personalizados](teams-custom-app-policies-and-settings.md).

1. Selecione **Salvar**. As configurações entrarão em vigor após algumas horas.

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gerenciar configurações de aplicativos em toda a organização para o Microsoft 365 Government  

Em uma implantação do Microsoft 365 Government – GCC, GCCH e DoD, todos os aplicativos de terceiros são bloqueados por padrão. Os aplicativos de terceiros não estão disponíveis para nuvens GCCH e DOD. Além disso, na GCC, você verá a seguinte observação sobre o gerenciamento de aplicativos de terceiros na página de políticas de permissão de aplicativos no centro de administração do Microsoft Teams.

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="Captura de tela da política de permissão do aplicativo na GCCH e no DoD.":::

Use as configurações de aplicativos de toda a organização para controlar se os usuários podem instalar aplicativos de terceiros. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários.

<!---1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. 
--->

### <a name="for-gcc-clouds"></a>Para nuvens GCC

1. Na página **Aplicativos** >  do Teams **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**, selecione **Configurações de aplicativo em toda a organização**. Você pode então definir as configurações desejadas no painel.

   :::image type="content" source="media/app-permission-policies-gcc-org-wide.png" alt-text="Captura de tela que mostra as configurações do aplicativo em toda a organização no GCC.":::

1. Em **Aplicativos de terceiros**, desabilite ou ative essas configurações para controlar o acesso a aplicativos de terceiros:

    * **Permitir aplicativos de terceiros**: essa opção controla se os usuários podem usar aplicativos de terceiros. Se você desabilitar esta configuração, seus usuários não poderão instalar ou usar aplicativos de terceiros. Em uma implantação do Microsoft 365 Government – GCC e DoD no Teams, essa configuração está desativada por padrão.
    * **Permitir novos aplicativos de terceiros publicados na loja por padrão**: essa opção controla se os novos aplicativos de terceiros publicados na loja de aplicativos do Teams se tornam automaticamente disponíveis no Teams. Você só pode definir essa opção se permitir aplicativos de terceiros.

1. Em **Aplicativos bloqueados**, adicione os aplicativos que deseja bloquear em sua organização. Em uma implantação do Microsoft 365 Government – GCCH e DoD do Teams, todos os aplicativos de terceiros são adicionados a esta lista por padrão. Para qualquer aplicativo de terceiros que você deseja permitir em sua organização, remova o aplicativo desta lista de aplicativos bloqueados. Quando você bloqueia um aplicativo em toda a organização, o aplicativo é automaticamente bloqueado para todos os seus usuários, independentemente de ser permitido em qualquer política de permissão de aplicativo.

1. Selecione **Salvar** para que as configurações do aplicativo em toda a organização entrem em vigor.

Para permitir aplicativos de terceiros, edite e use a política global (padrão em toda a organização) ou crie e atribua uma política criada por administrador.

### <a name="for-gcch-and-dod-clouds"></a>Para nuvens GCCH e DoD

1. Entre no centro de administração do Teams e acesse **[políticas de permissão](https://admin.teams.microsoft.com/policies/app-permission)** **de aplicativos** >  do Teams.

1. Selecione **Configurações de aplicativo em toda a organização**. Em **Aplicativos bloqueados**, adicione os aplicativos que deseja bloquear em sua organização. Em uma implantação do Microsoft 365 Government – GCCH e DoD do Teams, todos os aplicativos de terceiros são adicionados a esta lista por padrão. Quando você bloqueia um aplicativo em toda a organização, o aplicativo é automaticamente bloqueado para todos os seus usuários, independentemente de ser permitido em qualquer política de permissão de aplicativo.

   :::image type="content" source="media/app-permission-policies-gcch-dod-org-wide.png" alt-text="Captura de tela das configurações de aplicativo em toda a organização na GCCH e no DoD.":::

1. Selecione **Salvar** para que as configurações do aplicativo em toda a organização entrem em vigor.

## <a name="related-article"></a>Artigo relacionado

* [Gerenciar solicitações de usuário para permitir aplicativos](user-requests-approve-apps.md).
