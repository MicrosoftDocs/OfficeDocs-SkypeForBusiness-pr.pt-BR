---
title: Gerenciar os aplicativos Microsoft Power Platform no centro de administração do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar o acesso a aplicativos personalizados criados na plataforma de alimentação da Microsoft no centro de administração do Microsoft Teams.
ms.openlocfilehash: 5675083c3a7b0aaea2fb053609cbf7da800dbe42
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753566"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar os aplicativos Microsoft Power Platform no centro de administração do Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicativos da plataforma de energia da Microsoft no Teams

Este artigo oferece uma visão geral de como gerenciar os aplicativos da [plataforma de energia da Microsoft](https://powerplatform.microsoft.com/) no centro de administração do Microsoft Teams.

> [!NOTE]
> Este artigo se aplica a aplicativos personalizados criados por Makers em sua organização usando aplicativos avançados ou agentes de energia virtual. Esses aplicativos personalizados são adicionados automaticamente ao Teams. Este artigo não se aplica ao aplicativo de aplicativos de energia ou ao aplicativo de agentes de energia virtual que são instalados na página de aplicativos ou fixos para o Microsoft Teams por meio de uma política de configuração de aplicativo. Você gerencia esses aplicativos da mesma forma que faria para qualquer outro aplicativo na página [gerenciar aplicativos](manage-apps.md) , usando [políticas de permissão do aplicativo](teams-app-permission-policies.md)e políticas de configuração do [aplicativo](teams-app-setup-policies.md).

Os [aplicativos de energia](https://powerapps.microsoft.com) são um ambiente de desenvolvimento de aplicativos de código e sem código baixo que os facilitadores da sua organização podem usar para criar aplicativos personalizados que se conectam aos seus dados corporativos. [Os agentes de energia virtual](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) são um ambiente de construção sem código-código para que Makers criem bots avançados. Com a integração dos aplicativos da plataforma Microsoft Power ao Microsoft Teams, as organizações podem simplificar processos de negócios, atender às mudanças nas necessidades dos negócios com mais rapidez para aumentar a colaboração e criar e compartilhar soluções personalizadas para serem mais produtivas.  

Os aplicativos da plataforma de alimentação da Microsoft criados por Makers em sua organização são adicionados automaticamente ao Teams. Os Makers podem controlar quem pode acessar o aplicativo usando o [recurso de compartilhamento em aplicativos de energia](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) e o [recurso de compartilhamento em agentes de energia virtual](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).

Quando um aplicativo da plataforma de energia da Microsoft é criado ou compartilhado, os usuários podem exibi-lo e instalá-lo na página de aplicativos indo para o ** *nome de sua organização***  >  **criado por seus colegas**. (Pode levar alguns minutos depois que um aplicativo é criado ou compartilhado para que o aplicativo seja exibido aqui).

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de tela da página de aplicativos, mostrando os aplicativos da plataforma de energia da Microsoft listados em criado por seus colegas":::

Um usuário verá um aplicativo **criado por seus colegas** se o aplicativo atender a uma das seguintes condições.

|Aplicativos de energia |Agentes de energia virtual  |
|---------|---------|
|<ul><li>O usuário criou o aplicativo.</li><li>O aplicativo foi compartilhado diretamente com o usuário.</li><li>O usuário usou recentemente o aplicativo. </li></ul>| <ul><li>O usuário criou o bot.</li><li>O bot pertence a uma equipe da qual o usuário é membro. </li></ul>        |

Os usuários instalam os aplicativos da plataforma de alimentação da Microsoft da mesma forma que instalam qualquer outro aplicativo de equipe. Lembre-se de que os usuários só podem instalar aplicativos no contexto para o qual tenham permissões, por exemplo, uma equipe que eles possuem, um chat do qual eles fazem parte ou seu escopo pessoal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar o acesso aos aplicativos Microsoft Power Platform no centro de administração do Microsoft Teams

Como administrador, você pode controlar se os aplicativos da plataforma de energia da Microsoft são listados em **criados por seus colegas** na página aplicativos no Microsoft Teams. Você pode bloquear coletivamente ou permitir todos os aplicativos criados em aplicativos de energia ou todos os aplicativos criados em agentes de energia virtual no nível da organização na página [gerenciar aplicativos](manage-apps.md) ou para usuários específicos usando [políticas de permissão do aplicativo](teams-app-permission-policies.md).

Os aplicativos de **energia compartilhados** e os aplicativos de **aplicativos de agente virtual de energia compartilhada** na loja de aplicativos da sua organização representam todos os aplicativos criados nessa plataforma específica. Se você bloquear um ou ambos os aplicativos no nível da organização ou para usuários específicos, esses usuários não poderão ver nenhum aplicativo dessas plataformas **criadas por seus colegas** e não poderão instalá-los no Microsoft Teams.  

Lembre-se de que você pode controlar o acesso a todos os aplicativos criados em aplicativos de energia e agentes virtuais de energia, mas não pode permitir ou bloquear aplicativos individuais. Os Makers decidem quem pode acessar os aplicativos criados por meio do recurso de compartilhamento dentro dos aplicativos de energia e dos agentes virtuais de energia. Se um criador compartilhou um aplicativo criado em agentes de energia virtual com um usuário e você bloqueou os **aplicativos de agentes virtuais de energia** para esse usuário, o usuário não poderá ver ou instalar aplicativos dessa plataforma no Microsoft Teams.

Se um usuário tiver permissão para acessar os aplicativos de aplicativos avançados ou agentes virtuais de energia e você impedir que o usuário acesse aplicativos de uma ou ambas as plataformas, o usuário ainda poderá acessar e usar os aplicativos Microsoft Power Platforms instalados antes de bloquear o aplicativo ou aplicativos. No entanto, o usuário não pode mais ver ou instalar qualquer aplicativo dessas plataformas **incorporadas por seus colegas**.

> [!NOTE]
> A configuração **permitir interação com aplicativos personalizados** do aplicativo de grande porte na página [gerenciar aplicativos](manage-apps.md) se aplica a todos em sua organização e controla se eles podem interagir com aplicativos personalizados. As configurações de aplicativo de toda a organização governam o comportamento para todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Por padrão, essa configuração está ativada. Se essa configuração estiver desativada, os usuários da sua organização não poderão ver ou instalar aplicativos personalizados, incluindo aplicativos da plataforma de energia da Microsoft. Para saber mais, consulte [gerenciar configurações de aplicativo de toda a organização](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir ou bloquear aplicativos da plataforma de energia da Microsoft para sua organização

Por padrão, os **aplicativos de energia compartilhada** e os **aplicativos de agente virtual de energia compartilhada** são permitidos para todos os usuários do teams em sua organização. Você pode bloqueá-los ou permiti-los no nível da organização na página [gerenciar aplicativos](manage-apps.md) do centro de administração do Microsoft Teams.  

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**. Você deve ser administrador global ou administrador do teams Service para acessar a página.
2. Na lista de aplicativos, siga um destes procedimentos:

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos, mostrando os aplicativos compartilhados da plataforma de energia da Microsoft":::

    - Para bloquear aplicativos criados em aplicativos de energia ou agentes de energia virtual para todos os usuários em sua organização, procure por **aplicativos de energia compartilhados** ou **aplicativos de agente virtual de energia compartilhados**, selecione-o e clique em **Bloquear**.
    - Para permitir que aplicativos criados em aplicativos de energia ou agentes virtuais de energia para todos os usuários de sua organização, procure por **aplicativos de energia compartilhados** ou **aplicativos de agente virtual de energia compartilhados**, selecione-o e clique em **permitir**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir ou bloquear aplicativos da plataforma de energia da Microsoft para usuários específicos

Para permitir ou bloquear usuários específicos em sua organização de acessarem aplicativos criados em aplicativos de poder ou agentes de energia virtual, crie e atribua uma ou mais [políticas de permissão de aplicativo](teams-app-permission-policies.md)personalizadas. 

Por exemplo, para bloquear usuários específicos que acessam aplicativos criados em aplicativos de energia, crie uma política de permissão de aplicativo personalizada para bloquear os **aplicativos de energia compartilhados**e atribuir a política a esses usuários.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de tela do exemplo de política de permissão de aplicativo personalizada com aplicativos de energia compartilhados bloqueados":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar logs de auditoria para investigar a atividade de instalação do Microsoft Power Platform

Você pode usar logs de auditoria para Teams para investigar eventos em que os usuários instalaram aplicativos da plataforma Microsoft Power da seção **compilada por seus colegas** da página aplicativos no Microsoft Teams. Para fazer isso, [pesquise o log de auditoria](https://docs.microsoft.com/microsoftteams/audit-log-events) para o evento app Teams **instalado** (na operação **AppInstalled** ) para um usuário ou conjunto de usuários. Para localizar aplicativos instalados de **criados por seus colegas**, procure o valor **TemplatedInstance** na propriedade **AppDistributionMode** nos detalhes de um determinado registro. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de tela do valor TemplatedInstance na propriedade AppDistributionMode":::

> [!NOTE]
> Você pode exportar registros de auditoria em formato CSV para facilitar a filtragem.

## <a name="related-topics"></a>Tópicos relacionados

- [Compartilhar um aplicativo de tela em aplicativos de energia](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Compartilhar seu bot com outros usuários](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Gerenciar aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Publicar um aplicativo personalizado enviado por meio da API de envio do aplicativo Teams](submit-approve-custom-apps.md)
