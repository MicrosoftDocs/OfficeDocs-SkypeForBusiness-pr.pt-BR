---
title: Gerenciar o aplicativo Turnos para sua organização
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Saiba como configurar e gerenciar o aplicativo Shifts no Teams para os funcionários de linha de frente em sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dd40888ec8f1f7c5c05c3f5a2bf5a867ece93a65
ms.sourcegitcommit: 10bee789272e648ea1e93d7d7c27ec645d0a8bdd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2022
ms.locfileid: "62918874"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gerencie o aplicativo Turnos para sua organização no Microsoft Teams

## <a name="overview-of-shifts"></a>Visão geral do Turnos

O aplicativo Shifts no Microsoft Teams mantém os funcionários de linha de frente conectados e sincronizados. Ele foi criado primeiro para o gerenciamento rápido e eficaz de tempo e comunicação para as equipes. Os turnos permitem que os funcionários de linha de frente e seus gerentes usem seus dispositivos móveis para gerenciar agendas e manter contato.

- Os gerentes criam, atualizam e gerenciam cronogramas de turnos da equipe. Eles também podem enviar mensagens para uma pessoa ("há um derramamento no chão") ou para toda a equipe ("o gerente regional chega em 20 minutos"). Eles podem enviar documentos de política, boletins de notícias e vídeos.
- Os funcionários visualizam os próximos turnos rapidamente, podem ver quem mais está agendado para o dia, solicitar uma troca de turno, oferecer um turno e solicitar folgas.

É importante saber que shifts atualmente não suportam convidados. Isso significa que os convidados em uma equipe não podem ser adicionados ou usar escalas de turnos quando o acesso de Convidado estiver ativado no Teams.

> [!Note]
> Para obter detalhes sobre os recursos do Turnos em diferentes plataformas, confira [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidade de Turnos

O Turnos está disponível em todas as SKUs corporativas onde o Teams está disponível.

## <a name="location-of-shifts-data"></a>Local dos dados de Turnos

Atualmente, os dados do Turnos estão armazenados no Azure, em datacenters na América do Norte, na Europa Ocidental e Ásia-Pacífico. Confira mais informações sobre onde os dados são armazenados em [Onde estão meus dados?](http://o365datacentermap.azurewebsites.net/)

## <a name="shifts-data"></a>Desloca dados

Para saber mais sobre onde os dados shifts são armazenados e retenção, recuperação e criptografia de dados shifts, consulte [Perguntas frequentes](shifts-data-faq.md) sobre os dados shifts.

## <a name="set-up-shifts"></a>Configurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar ou desabilitar o Turnos em sua organização

O Turnos é habilitado por padrão para todos os usuários do Teams em sua organização. Você pode desativar ou ativar o aplicativo no nível da organização na página [Gerenciar aplicativos](../../manage-apps.md) no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Na lista de aplicativos, pesquise o aplicativo Shifts, selecione-o e alterne a alternância **Status** para **Bloqueado** ou **Permitido**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilite ou desabilite o Turnos para usuários específicos em sua organização

Para permitir ou bloquear usuários específicos em sua organização de usar Turnos, certifique-se de que Shifts está ligado para sua organização na página [Gerenciar aplicativos](../../manage-apps.md) . Em seguida, crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](../../teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Use uma política de configuração de aplicativo para fixar Turnos Teams

As políticas de configuração de aplicativos permitem que você personalize o Teams para destacar os aplicativos que são mais importantes para os usuários em sua organização. Os aplicativos definidos em uma política são fixados na barra do aplicativo&mdash;na barra na lateral do cliente de área de trabalho do Teams e na parte inferior dos clientes móveis do Teams&mdash;onde os usuários podem acessá-los de forma rápida e fácil.

Você pode criar uma [política de configuração de aplicativo](../../teams-app-setup-policies.md) personalizada adicionando o aplicativo Shifts e [atribuindo a política](../../assign-policies-users-and-groups.md) aos usuários. Ou você pode usar a política de configuração de aplicativo que faz parte dos pacotes de política do Frontline Worker e do Gerenciador de Linha de Frente.

Um [pacote de política](../../manage-policy-packages.md) no Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir a usuários que têm funções semelhantes em sua organização. O conjunto de políticas nos pacotes de política do Frontline Worker and Frontline Manager inclui uma política de configuração de aplicativo que fixa o aplicativo Shifts e outros aplicativos que suportam atividades de comunicação e colaboração para essa função.

Recomendamos usar os pacotes de política do Frontline Worker and Frontline Manager à medida que eles simplificam, simplificam e ajudam a fornecer consistência ao gerenciar políticas para sua força de trabalho de linha de frente.

## <a name="search-the-audit-log-for-shifts-events"></a>Pesquisar o registro de auditoria para eventos do Turnos

**(em visualização)**

Você pode pesquisar no log de auditoria para exibir as atividades de Turnos na sua organização.  Para saber mais sobre como pesquisar no log de auditoria e ver uma lista de [atividades de Turnos](../../audit-log-events.md#shifts-in-teams-activities) que são registradas no log de auditoria, consulte [Pesquisar no log de auditoria por eventos no Teams](../../audit-log-events.md).

Antes de poder pesquisar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://protection.office.com). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="related-topics"></a>Tópicos relacionados

- [Turnos do Teams](../shifts-for-teams-landing-page.md)
- [Ajuda de turnos para trabalhadores de linha de frente](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Conectores de turnos](shifts-connectors.md)
- [Atribuir políticas aos usuários no Microsoft Teams](../../policy-assignment-overview.md)
