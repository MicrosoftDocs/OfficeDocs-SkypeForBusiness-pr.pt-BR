---
title: Gerenciar o aplicativo tarefas para sua organização no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: Saiba como gerenciar o aplicativo tarefas para usuários em sua organização.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cc477b9589aeebb8dcd486e7f85ca04daf6ff4d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909395"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Gerenciar o aplicativo tarefas para sua organização no Microsoft Teams

## <a name="overview-of-tasks"></a>Visão geral das tarefas

O aplicativo tarefas traz uma experiência coesa de gerenciamento de tarefas para o Microsoft Teams, integrando tarefas individuais da [Microsoft a fazer](https://todo.microsoft.com/tasks/) e tarefas da equipe com o Planner em um só lugar. Os usuários podem acessar as tarefas como um aplicativo no lado esquerdo do Teams e como uma guia em um canal dentro de equipes individuais. **Minhas tarefas** e **planos compartilhados** em tarefas permitem aos usuários exibir e gerenciar todas as tarefas individuais e da equipe e priorizar o trabalho delas. Tarefas está disponível em Teams desktop, Web e clientes móveis. 

> [!NOTE]
> Ao implantar a experiência de tarefas em clientes da área de trabalho do Teams, o nome do aplicativo aparecerá inicialmente como **planejador** para os usuários. O nome então mudará temporariamente para **tarefas pelo Planner e para fazer** e, posteriormente, será renomeado para **tarefas**. Em clientes móveis do Teams, os usuários sempre verão o nome do aplicativo como **tarefas**. Pode haver um pequeno atraso na disponibilidade da experiência móvel depois que a experiência da área de trabalho estiver disponível.

   ![Captura de tela do modo de exibição de lista de tarefas na lista de equipes](media/manage-tasks-app-tasks.png)

Para as organizações que desejam simplificar o gerenciamento de tarefas para trabalhadores do Frontline, as tarefas também incluem recursos que permitem direcionar, publicar e acompanhar tarefas em escala em toda a sua força de trabalho do Frontline. Por exemplo, a liderança corporativa e regional pode criar e publicar listas de tarefas direcionadas para locais relevantes, como lojas de varejo específicas e controlar o progresso por meio de relatórios em tempo real. Os gerentes podem atribuir tarefas a seus funcionários e atividades direcionadas em seus locais, e os funcionários do Frontline têm uma lista priorizada de suas tarefas atribuídas no celular ou na área de trabalho. Para habilitar a [publicação de tarefas](#task-publishing), primeiro você precisará configurar uma hierarquia de direcionamento de equipe para sua organização, que define como todas as equipes da hierarquia estão relacionadas umas às outras.

## <a name="what-you-need-to-know-about-tasks"></a>O que você precisa saber sobre tarefas

Tarefas está disponível como um aplicativo e uma guia em um canal. Lembre-se de que o aplicativo inclui tarefas individuais de tarefas pendentes e tarefas da equipe no Planner, enquanto a guia mostra somente tarefas da equipe.

Com as tarefas, os usuários obtêm uma experiência na área de trabalho, Web e celular. Se as tarefas estiverem instaladas no cliente da área de trabalho do Teams, os usuários também o verão em seus clientes Web e móveis do Microsoft Teams. A exceção são usuários convidados. É importante saber que os convidados só podem acessar as tarefas como um aplicativo no cliente móvel do teams. Os convidados verão as guias de tarefas nos clientes da área de trabalho da equipe e na Web.

**Minhas tarefas** mostra as tarefas individuais de um usuário. Os **planos compartilhados** mostram as tarefas em que a equipe inteira está trabalhando e inclui qualquer lista de tarefas adicionada como uma guia tarefas a um canal. Observe o seguinte:

- Listas de tarefas que um usuário cria no aplicativo tarefas também aparecerá em clientes para fazer isso para o usuário. Da mesma forma, as listas de tarefas que um usuário cria em tarefas pendentes serão exibidas em **minhas tarefas** em tarefas desse usuário. O mesmo se aplica às tarefas individuais.

- Qualquer guia tarefas que é adicionada a um canal também será exibida em clientes do Planner. Quando um usuário cria um plano no Planner, o plano não é mostrado no aplicativo tarefas ou Planner, a menos que seja adicionado como uma guia a um canal. Quando um usuário adiciona uma nova guia tarefas, ele pode criar uma nova lista ou plano ou escolher uma existente.

## <a name="set-up-tasks"></a>Configurar tarefas

> [!IMPORTANT]
> As configurações e políticas que você configurou para o Planner também serão aplicadas às tarefas.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Habilitar ou desabilitar tarefas em sua organização

Tarefas é habilitada por padrão para todos os usuários do teams em sua organização. Você pode desativar ou ativar o aplicativo no nível da organização na página [gerenciar aplicativos](manage-apps.md) no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos** .
2. Na lista de aplicativos, siga um destes procedimentos:

    - Para desativar as tarefas da sua organização, procure o aplicativo tarefas, selecione-a e clique em **Bloquear**.
    - Para ativar as tarefas da sua organização, procure o aplicativo tarefas, selecione-a e clique em **permitir**.

> [!NOTE]
> Se você não conseguir encontrar o aplicativo tarefas, procure os nomes na primeira anotação deste artigo. O aplicativo ainda pode estar em processo de ser renomeado.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Habilitar ou desabilitar tarefas para usuários específicos em sua organização

Para permitir ou bloquear usuários específicos em sua organização usando tarefas, verifique se a opção tarefas está ativada para sua organização na página [gerenciar aplicativos](manage-apps.md) e crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Usar uma política de configuração do aplicativo para fixar tarefas em equipes

As políticas de configuração do aplicativo permitem que você personalize o Microsoft Teams para realçar os aplicativos que são mais importantes para os usuários da sua organização. Os aplicativos que você define em uma política são fixados na barra do aplicativo &mdash; na barra do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, &mdash; onde os usuários podem acessá-los de forma rápida e fácil.

Para fixar o aplicativo tarefas para seus usuários, você pode editar a política global (padrão para toda a organização) ou criar e atribuir uma política de configuração de aplicativo personalizada. Para saber mais, consulte [gerenciar políticas de configuração de aplicativos no Microsoft Teams](teams-app-setup-policies.md).

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>As minhas tarefas de um usuário ficam visíveis se o usuário estiver licenciado para o Exchange Online

Se não quiser que um usuário veja **minhas tarefas**, você pode ocultá-la. Para fazer isso, [remova a licença do Exchange Online do usuário](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users). É importante saber que, após remover uma licença do Exchange Online, o usuário não tem mais acesso à sua caixa de correio.  Os dados de caixa de correio são mantidos por 30 dias, após o qual os dados serão removidos e não poderão ser recuperados, a menos que a caixa de correio seja colocada em [retenção in-loco ou em retenção de litígio](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds).

Não recomendamos isso para os operadores de informações, mas pode haver alguns cenários nos quais isso pode ser aplicado, como os funcionários do Frontline que não dependem do e-mail.

## <a name="task-publishing"></a>Publicação de tarefas

Com a publicação de tarefas, sua organização pode publicar listas de tarefas direcionadas para locais específicos (equipes) em sua organização para definir e compartilhar um plano de trabalho para ser concluído nesses locais.

- As pessoas na equipe de publicação, como a liderança corporativa ou regional, podem criar listas de tarefas e publicá-las em equipes específicas.<br>
    ![Captura de tela da publicação de tarefas](media/manage-tasks-app-publish.png)
- Os gerentes nas equipes do destinatário podem revisar as listas de tarefas publicadas e atribuir tarefas individuais a membros da equipe.<br>
    ![Captura de tela da atribuição de uma tarefa](media/manage-tasks-app-assign.png)
- Os funcionários do Frontline têm uma experiência móvel simples para ver as tarefas atribuídas a eles. Eles podem anexar fotos para mostrar seu trabalho quando apropriado e marcar suas tarefas como concluídas.
- Editores e gerentes podem exibir relatórios para ver o status de atribuição e conclusão de tarefas em cada nível, incluindo por local (equipe), lista de tarefas e tarefa individual.<br>
    ![Captura de tela de tarefas atribuídas em dispositivos móveis](media/manage-tasks-app-reporting.png)

Os usuários criam, gerenciam e publicam listas de tarefas na guia **listas publicadas** do aplicativo tarefas. Essa guia só será mostrada para um usuário se a sua organização [Configurar uma hierarquia de direcionamento de equipe](#set-up-your-team-targeting-hierarchy) e o usuário estiver em uma equipe incluída na hierarquia. A hierarquia determina se o usuário pode publicar ou receber listas de tarefas e exibir relatórios para listas recebidas.

### <a name="example-scenario"></a>Cenário de exemplo

Aqui está um exemplo de como funciona a publicação de tarefas.

A Contoso está lançando um novo takeout de alimentos e uma promoção de entrega. Para manter uma experiência de marca consistente, é preciso coordenar a execução consistente da distribuição em mais de 300 locais da loja.

A equipe de marketing compartilha os detalhes da promoção e a lista de tarefas correspondente com o Retail Communications Manager. O Gerenciador de comunicações de revenda, que serve como o gatekeeper para lojas, revisa as informações, cria uma lista de tarefas para a promoção e, em seguida, cria uma tarefa para cada unidade de trabalho que precisa ser executada por cada um dos repositórios afetados. Quando a lista de tarefas é concluída, ela precisa selecionar as lojas que devem concluir o trabalho. Nesse caso, a promoção só se aplica às lojas nos Estados Unidos que têm um restaurante na loja. Em tarefas, ela filtra a lista da loja com base no atributo de restaurante na loja, seleciona os locais correspondentes nos Estados Unidos na hierarquia e, em seguida, publica a lista de tarefas para essas lojas.

Os gerentes da loja em cada local recebem uma cópia das tarefas publicadas e atribui essas tarefas aos membros da equipe. Os gerentes podem usar a experiência de tarefas para compreender todo o trabalho necessário em sua loja. Eles também podem usar os filtros disponíveis para se concentrar em um conjunto específico de trabalho, como o trabalho devido hoje ou trabalhar em uma determinada área.

Os funcionários do Frontline em cada local da loja agora têm uma lista priorizada do trabalho nas tarefas em tarefas em seu dispositivo móvel. Quando eles terminarem uma tarefa, eles o marcarão como concluídos. Alguns podem até mesmo optar por carregar e anexar uma foto à tarefa para mostrar seus trabalhos.

Matrizes da Contoso e gerentes intermediários podem exibir relatórios para ver o status de atribuição e conclusão de tarefas em cada loja e em lojas. Eles também podem fazer uma busca detalhada em uma tarefa específica para ver o status dentro de diferentes lojas. À medida que a data de lançamento fica mais próxima, elas podem detectar anormalidades e fazer check-in com suas equipes, conforme necessário. Essa visibilidade permite que a contoso aprimore a eficiência da distribuição e ofereça uma experiência mais consistente entre suas lojas.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurar sua hierarquia de direcionamento de equipe

Para habilitar a publicação de tarefas em sua organização, você precisa primeiro configurar o esquema de direcionamento da equipe em um. Arquivo CSV. O esquema define como todas as equipes em sua hierarquia estão relacionadas umas às outras e os atributos usados para filtrar e selecionar equipes. Depois de criar o esquema, carregue-o no Teams para aplicá-lo à sua organização. Os membros da equipe de publicação, como o Gerenciador de comunicações de revenda no cenário de exemplo, podem, em seguida, filtrar equipes por hierarquia, atributos ou uma combinação de ambos para selecionar as equipes relevantes que devem receber as listas de tarefas e, em seguida, publicar as listas de tarefas nessas equipes.

Para ver as etapas sobre como configurar sua hierarquia de direcionamento de equipe, consulte [configurar sua hierarquia de direcionamento de equipe](set-up-your-team-hierarchy.md).

## <a name="power-automate-and-graph-api"></a>API do gráfico e automatização de energia

As tarefas dão suporte à automatização de energia para APIs do to do e do Graph para Planner. Para saber mais, veja:

- [Visão geral da API de planos e tarefas do Planner](https://docs.microsoft.com/graph/planner-concept-overview)
- [Usar o Microsoft para fazer com o Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
