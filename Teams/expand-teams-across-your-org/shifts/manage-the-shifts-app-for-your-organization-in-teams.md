---
title: Gerenciar o aplicativo turnos para a sua organização
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Saiba como configurar e gerenciar o aplicativo turnos no Microsoft Teams para trabalhadores do Frontline em sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909085"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gerencie o aplicativo Turnos para sua organização no Microsoft Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [o Microsoft StaffHub foi desativado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Visão geral de turnos

O aplicativo turnos no Microsoft Teams mantém os funcionários do Frontline conectados e em sincronização. Ele foi criado para o seu celular primeiro para gerenciamento e comunicação de tempo rápido e eficiente para equipes. Turnos permite que os funcionários do Frontline e seus gerentes usem seus dispositivos móveis para gerenciar os cronogramas e manter contato.

- Gerentes criam, atualizam e gerenciam os cronogramas de turnos do teams. Eles podem enviar mensagens para uma pessoa ("há um derramamento na base") ou toda a equipe ("a GM regional é chegando em 20 minutos"). Eles também podem enviar documentos de política, boletins de notícias e vídeos. 
- Os funcionários visualizam seus próximos turnos, ver quem mais está agendado para o dia, solicitar a troca ou oferecer um turno e solicitar folga. 

É importante saber que os turnos atualmente não dão suporte a usuários convidados. Isso significa que os convidados de uma equipe não podem ser adicionados ou usar as agendas de turnos quando o acesso de convidado está ativado no Teams. 

> [!Note]
> Para obter detalhes sobre os recursos de turnos em diferentes plataformas, consulte [recursos do teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidade de turnos

Os turnos estão disponíveis em todos os SKUs corporativos nos quais o Microsoft Teams está disponível.

## <a name="location-of-shifts-data"></a>Local dos dados de turnos

Os dados de turnos atualmente estão armazenados no Azure em data centers na América do Norte, Europa Ocidental e Pacífico Asiático. Para obter mais informações sobre onde os dados são armazenados, confira [onde estão os meus dados](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurar turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar ou desabilitar turnos em sua organização

Os turnos são habilitados por padrão para todos os usuários do teams na sua organização. Você pode desativar ou ativar o aplicativo no nível da organização na página [gerenciar aplicativos](../../manage-apps.md) no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.
2. Na lista de aplicativos, execute uma das seguintes ações:

    - Para desativar os turnos da sua organização, procure o aplicativo turnos, selecione-o e, em seguida, selecione **Bloquear**.
    - Para ativar turnos para sua organização, procure o aplicativo turnos, selecione-o e, em seguida, selecione **permitir**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar ou desabilitar turnos para usuários específicos em sua organização

Para permitir ou bloquear usuários específicos em sua organização usando turnos, certifique-se de que os turnos estejam ativados para sua organização na página [gerenciar aplicativos](../../manage-apps.md) e crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](../../teams-app-permission-policies.md).

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usar a política de configuração do aplicativo FrontlineWorker para fixar mudanças em equipes

As políticas de configuração do aplicativo permitem que você personalize o Microsoft Teams para realçar os aplicativos que são mais importantes para os usuários da sua organização. Os aplicativos definidos em uma política são fixados na barra do aplicativo na &mdash; barra do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, &mdash; nos quais os usuários podem acessá-los de forma rápida e fácil.
 
O Teams inclui uma política interna de configuração de aplicativos do FrontlineWorker que você pode atribuir a trabalhadores do Frontline em sua organização. Por padrão, a política inclui os aplicativos atividade, turnos, chat e chamadas. 

Para exibir a política FrontlineWorker, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para políticas de configuração do aplicativo **Teams app**  >  .

![Captura de tela da política de configuração do aplicativo FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FrontlineWorker no centro de administração do Microsoft Teams")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Atribuir a política de configuração do aplicativo FrontlineWorker aos usuários

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Pesquisar eventos Shift do log de auditoria

**(em visualização)**

Você pode pesquisar o log de auditoria para exibir a atividade de turnos em sua organização.  Para saber mais sobre como Pesquisar no log de auditoria e ver uma lista de [atividades de turnos](../../audit-log-events.md#shifts-in-teams-activities) que são registradas no log de auditoria, consulte [Pesquisar o log de auditoria para eventos no Teams](../../audit-log-events.md).

Para que você possa Pesquisar no log de auditoria, primeiro ative a auditoria no [centro de conformidade do & de segurança](https://protection.office.com). Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Lembre-se de que os dados de auditoria estão disponíveis apenas no ponto em que você ativou a auditoria.

## <a name="related-topics"></a>Tópicos relacionados

- [Ajuda de turnos para trabalhadores do Frontline](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Atribuir políticas aos usuários no Microsoft Teams](../../assign-policies.md)
