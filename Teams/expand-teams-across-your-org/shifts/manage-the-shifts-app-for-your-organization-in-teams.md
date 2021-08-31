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
description: Saiba como configurar e gerenciar o aplicativo Shifts no Teams para os funcionários de linha de frente em sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e58b7452ec3e89ded6f24da17490cf476885d72
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727830"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gerencie o aplicativo Turnos para sua organização no Microsoft Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi desativado. Estamos criando recursos StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo Shifts para o gerenciamento de cronogramas e recursos adicionais serão implantados com o tempo. O StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Todas as pessoas que tentarem abrir o StaffHub receberão uma mensagem direcionando-as para o download do Teams. Para saber mais, confira [O Microsoft StaffHub foi desativado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Visão geral do Turnos

O aplicativo Shifts no Microsoft Teams mantém os funcionários de linha de frente conectados e sincronizados. Ele foi criado primeiro para o gerenciamento rápido e eficaz de tempo e comunicação para as equipes. Os turnos permitem que os funcionários de linha de frente e seus gerentes usem seus dispositivos móveis para gerenciar agendas e manter contato.

- Os gerentes criam, atualizam e gerenciam cronogramas de turnos da equipe. Eles também podem enviar mensagens para uma pessoa ("há um derramamento no chão") ou para toda a equipe ("o gerente regional chega em 20 minutos"). Eles podem enviar documentos de política, boletins de notícias e vídeos.
- Os funcionários visualizam os próximos turnos rapidamente, podem ver quem mais está agendado para o dia, solicitar uma troca de turno, oferecer um turno e solicitar folgas.

É importante saber que Shifts atualmente não dá suporte a convidados. Isso significa que os convidados em uma equipe não podem ser adicionados ou usar escalas de turnos quando o acesso de Convidado estiver ativado no Teams. 

> [!Note]
> Para obter detalhes sobre os recursos do Turnos em diferentes plataformas, confira [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidade de Turnos

O Turnos está disponível em todas as SKUs corporativas onde o Teams está disponível.

## <a name="location-of-shifts-data"></a>Local dos dados de Turnos

Atualmente, os dados do Turnos estão armazenados no Azure, em datacenters na América do Norte, na Europa Ocidental e Ásia-Pacífico. Confira mais informações sobre onde os dados são armazenados em [Onde estão meus dados?](http://o365datacentermap.azurewebsites.net/)

## <a name="set-up-shifts"></a>Configurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar ou desabilitar o Turnos em sua organização

O Turnos é habilitado por padrão para todos os usuários do Teams em sua organização. Você pode desativar ou ativar o aplicativo no nível da organização na página [Gerenciar aplicativos](../../manage-apps.md) no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Na lista de aplicativos, siga um destes procedimentos:

    - Para desativar o Turnos para sua organização, pesquise o aplicativo Turnos, selecione-o e clique em **Bloquear**.
    - Para ativar o Turnos para sua organização, pesquise o aplicativo Turnos, selecione-o e clique em **Permitir**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilite ou desabilite o Turnos para usuários específicos em sua organização

Para permitir ou bloquear usuários específicos em sua organização de usar Turnos, certifique-se de que Shifts está ligado para sua organização na página [Gerenciar aplicativos.](../../manage-apps.md) Em seguida, crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Use a política de configuração do aplicativo FirstLineWorker para fixar Turnos Teams

As políticas de configuração de aplicativos permitem que você personalize o Teams para destacar os aplicativos que são mais importantes para os usuários em sua organização. Os aplicativos definidos em uma política são fixados na barra do aplicativo&mdash;na barra na lateral do cliente de área de trabalho do Teams e na parte inferior dos clientes móveis do Teams&mdash;onde os usuários podem acessá-los de forma rápida e fácil.
 
Teams inclui uma política interna de configuração de aplicativos FirstLineWorker que você pode atribuir aos funcionários de linha de frente em sua organização. Por padrão, a política inclui os aplicativos Atividade, Turnos, Chat e Chamada.

Para exibir **a** política FirstLineWorker, na navegação à esquerda do centro de administração Microsoft Teams, acesse Teams políticas de configuração  >  **do aplicativo.**

![Captura de tela da política de configuração do aplicativo FirstLineWorker.](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FirstLineWorker no Microsoft Teams de administração")

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Atribuir a política de configuração do aplicativo FirstLineWorker aos usuários

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Pesquisar o registro de auditoria para eventos do Turnos

**(em visualização)**

Você pode pesquisar no log de auditoria para exibir as atividades de Turnos na sua organização.  Para saber mais sobre como pesquisar no log de auditoria e ver uma lista de [atividades de Turnos](../../audit-log-events.md#shifts-in-teams-activities) que são registradas no log de auditoria, consulte [Pesquisar no log de auditoria por eventos no Teams](../../audit-log-events.md).

Antes de poder pesquisar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://protection.office.com). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="related-topics"></a>Tópicos relacionados

- [Ajuda de turnos para trabalhadores de linha de frente](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Atribuir políticas aos usuários no Microsoft Teams](../../assign-policies.md)
