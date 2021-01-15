---
title: Gerenciar o aplicativo Turnos para sua organização
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
description: Saiba como configurar e gerenciar o aplicativo Turnos no Teams para Trabalhadores da Linha de Frente em sua organização.
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
ms.openlocfilehash: dc6f3047a74fda332e945558a243f40b714e8730
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821131"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gerencie o aplicativo Turnos para sua organização no Microsoft Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi retirado. Estamos criando recursos do StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo Turnos para gerenciamento de agendamento e recursos adicionais serão incluídos ao longo do tempo. O StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub é exibida uma mensagem direcionando-a para baixar o Teams. Para saber mais, confira [o Microsoft StaffHub foi retirado.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview-of-shifts"></a>Visão geral das turnos

O aplicativo Shifts no Microsoft Teams mantém os Trabalhadores da Linha de Frente conectados e em sincronia. Ele foi criado primeiro para o gerenciamento rápido e eficaz de tempo e comunicação para equipes. As turnos permitem que os trabalhadores da linha de frente e seus gerentes usem seus dispositivos móveis para gerenciar agendas e manter contato.

- Os gerentes criam, atualizam e gerenciam as agendas de turno para as equipes. Eles podem enviar mensagens para uma pessoa ("há um vazamento no chão") ou toda a equipe ("o GM regional está chegando em 20 minutos"). Eles também podem enviar documentos de política, boletins de notícias e vídeos. 
- Os funcionários visualizam seus próximos turnos, podem ver quem mais está agendado para o dia, solicitar a troca ou oferta de um turno e solicitar folga. 

É importante saber que o Shifts atualmente não dá suporte a usuários convidados. Isso significa que os convidados em uma equipe não podem ser adicionados ou usar agendamentos de turno quando o acesso de convidado é ligado no Teams. 

> [!Note]
> Para obter detalhes sobre os recursos shifts em diferentes plataformas, consulte [os recursos do Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>Disponibilidade de turnos

Turnos estão disponíveis em todas as SKUs corporativas onde o Teams está disponível.

## <a name="location-of-shifts-data"></a>Localização dos dados shifts

Atualmente, os dados de turnos são armazenados no Azure em data centers na América do Norte, Europa Ocidental e Pacífico Asiático. Para obter mais informações sobre onde os dados são armazenados, consulte [Onde estão meus dados?](http://o365datacentermap.azurewebsites.net/)

## <a name="set-up-shifts"></a>Configurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar ou desabilitar Turnos em sua organização

As turnos são habilitadas por padrão para todos os usuários do Teams em sua organização. Você pode desativar ou ativar o aplicativo no [](../../manage-apps.md) nível da organização na página Gerenciar aplicativos no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Na lista de aplicativos, faça um dos seguintes:

    - Para desativar os Turnos da sua organização, pesquise o aplicativo Turnos, selecione-o e clique em **Bloquear.**
    - Para ativar turnos para sua organização, pesquise o aplicativo Turnos, selecione-o e clique em **Permitir**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar ou desabilitar Turnos para usuários específicos em sua organização

Para permitir ou impedir que usuários específicos em sua organização usem Turnos, certifique-se de que Shifts está ligado para sua organização na página Gerenciar aplicativos e, em seguida, crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. [](../../manage-apps.md) Para saber mais, confira [Gerenciar políticas de permissão de aplicativo no Teams.](../../teams-app-permission-policies.md)

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usar a política de configuração do aplicativo FirstlineWorker para fixar turnos no Teams

As políticas de configuração de aplicativo permitem personalizar o Teams para realçar os aplicativos mais importantes para os usuários em sua organização. Os aplicativos definidos em uma política são fixados na barra de aplicativos na barra do lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, onde os usuários podem acessá-los com rapidez e &mdash; &mdash; facilidade.
 
O Teams inclui uma política interna de configuração de aplicativo FirstlineWorker que você pode atribuir aos Trabalhadores da Linha de Frente em sua organização. Por padrão, a política inclui os aplicativos Atividade, Turnos, Chat e Chamada. 

Para exibir a política FirstlineWorker, na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de aplicativos  >  **do** Teams.

![Captura de tela da política de configuração do aplicativo FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FirstlineWorker no centro de administração do Microsoft Teams")

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Atribuir a política de configuração de aplicativo FirstlineWorker aos usuários

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Pesquisar o log de auditoria para eventos Shifts

**(em visualização)**

Você pode pesquisar o log de auditoria para exibir a atividade shifts em sua organização.  Para saber mais sobre como pesquisar o log de auditoria e ver uma lista das atividades shifts que estão [registradas](../../audit-log-events.md#shifts-in-teams-activities) no log de auditoria, consulte Pesquisar o log de auditoria para eventos [no Teams](../../audit-log-events.md).

Antes de poder pesquisar o log de auditoria, primeiro você precisa ativar a auditoria no Centro de Conformidade & [Segurança.](https://protection.office.com) Para saber mais, confira Ativar ou desativar a pesquisa [de log de auditoria.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) Lembre-se de que os dados de auditoria só estão disponíveis a partir do momento em que você a adotou a auditoria.

## <a name="related-topics"></a>Tópicos relacionados

- [Ajuda de turnos para trabalhadores da linha de frente](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Atribuir políticas aos usuários no Microsoft Teams](../../assign-policies.md)
