---
title: Gerenciar o aplicativo Shifts para sua organização
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
description: Saiba como configurar e gerenciar o aplicativo Shifts no Teams for Frontline Workers em sua organização.
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
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi retirado. Estamos criando recursos do StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo Shifts para gerenciamento de cronogramas e recursos adicionais serão incluídos ao longo do tempo. O StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-a para baixar o Teams. Para saber mais, confira [o Microsoft StaffHub foi retirado.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview-of-shifts"></a>Visão geral do Turnos

O aplicativo Turnos no Microsoft Teams mantém os Frontline Workers conectados e sincronizados. Ele foi criado em dispositivos móveis primeiro para gerenciamento e comunicação de tempo rápidos e eficazes para as equipes. O Turnos permite que os Trabalhadores da Linha de Frente e seus gerentes usem seus dispositivos móveis para gerenciar agendas e manter contato.

- Os gerentes criam, atualizam e gerenciam cronogramas de turnos para as equipes. Eles podem enviar mensagens para uma pessoa ("há um vazamento no chão") ou para toda a equipe ("o GERENTE regional chega em 20 minutos"). Eles também podem enviar documentos de política, boletins informativos e vídeos. 
- Os funcionários visualizam seus próximos turnos, veem quem mais está agendado para o dia, solicitam trocar ou oferecer um turno e solicitam folga. 

É importante saber que o Shifts atualmente não dá suporte a usuários convidados. Isso significa que os convidados de uma equipe não podem ser adicionados ou usar agendas de turnos quando o acesso de convidado está ligado no Teams. 

> [!Note]
> Para obter detalhes sobre os recursos do Shifts em diferentes plataformas, consulte os [recursos do Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>Disponibilidade de Turnos

O Turnos está disponível em todas as SKUs corporativas onde o Teams está disponível.

## <a name="location-of-shifts-data"></a>Localização dos dados do Turnos

No momento, os dados de turnos são armazenados no Azure em data centers na América do Norte, na Europa Ocidental e no Pacífico Asiático. Para saber mais sobre onde os dados são armazenados, consulte [Onde estão meus dados?](http://o365datacentermap.azurewebsites.net/)

## <a name="set-up-shifts"></a>Configurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar ou desabilitar o Shifts em sua organização

O Turnos é habilitado por padrão para todos os usuários do Teams em sua organização. Você pode desativar ou ativar o aplicativo no [](../../manage-apps.md) nível da organização na página Gerenciar aplicativos no Centro de administração do Microsoft Teams.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Na lista de aplicativos, faça uma das seguintes ações:

    - Para desativar o Shifts da sua organização, procure o aplicativo Shifts, selecione-o e selecione **Bloquear.**
    - Para ativar o Shifts para sua organização, procure o aplicativo Shifts, selecione-o e selecione **Permitir.**

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar ou desabilitar o Shifts para usuários específicos em sua organização

Para permitir ou bloquear que usuários específicos em sua organização usem o [](../../manage-apps.md) Shifts, certifique-se de que o Shifts está ligado para sua organização na página Gerenciar aplicativos e, em seguida, crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. Para saber mais, consulte [Gerenciar políticas de permissão do aplicativo no Teams.](../../teams-app-permission-policies.md)

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usar a política de configuração do aplicativo FrontlineWorker para fixar o Shifts no Teams

As políticas de configuração de aplicativos permitem personalizar o Teams para realçar os aplicativos mais importantes para os usuários em sua organização. Os aplicativos definidos em uma política são fixados na barra de aplicativos, na barra lateral do cliente de área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, onde os usuários podem acessá-los de forma rápida e &mdash; &mdash; fácil.
 
O Teams inclui uma política de configuração de aplicativo FrontlineWorker interna que você pode atribuir aos Trabalhadores de Linha de Frente em sua organização. Por padrão, a política inclui os aplicativos Atividade, Turnos, Chat e Chamada. 

Para exibir a política FrontlineWorker, na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de configuração do aplicativo **Teams.**  >  

![Captura de tela da política de configuração do aplicativo FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FrontlineWorker no Centro de administração do Microsoft Teams")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Atribuir a política de configuração do aplicativo FrontlineWorker aos usuários

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Pesquisar o log de auditoria para eventos do Shifts

**(em visualização)**

Você pode pesquisar no log de auditoria para exibir a atividade do Shifts em sua organização.  Para saber mais sobre como pesquisar no log de auditoria e ver uma lista de atividades do Turnos que estão [registradas](../../audit-log-events.md#shifts-in-teams-activities) no log de auditoria, consulte Pesquisar no log de auditoria para ver eventos no [Teams.](../../audit-log-events.md)

Antes de poder pesquisar o log de auditoria, primeiro você precisa ativar a auditoria no Centro de [Conformidade & Segurança.](https://protection.office.com) Para saber mais, confira Ativar ou desativar a pesquisa [de log de auditoria.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) Lembre-se de que os dados de auditoria só estão disponíveis a partir do ponto em que você a adotou a auditoria.

## <a name="related-topics"></a>Tópicos relacionados

- [Ajuda do Turnos para Trabalhadores da Linha de Frente](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Atribua políticas a seus usuários no Teams](../../assign-policies.md)
