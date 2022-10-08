---
title: Gerenciar o aplicativo Tasks para sua organização no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
audience: admin
description: Aprenda a gerenciar o aplicativo Tasks para usuários em sua organização.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.openlocfilehash: 74b67a71f8b93f5f0ed898ef186beede056ec31a
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047111"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Gerenciar o aplicativo Tasks para sua organização no Microsoft Teams

## <a name="overview-of-tasks"></a>Visão geral do Tasks

O aplicativo Tasks oferece uma experiência de gerenciamento de tarefas coesa para o Microsoft Teams, integrando tarefas individuais desenvolvidas pelo [Microsoft To Do](https://todo.microsoft.com/tasks/) e tarefas da equipe desenvolvidas pelo Planner em um só lugar. Os usuários podem acessar o Tarefas como um aplicativo no lado esquerdo do Teams e como uma guia em um canal dentro de equipes individuais. Com **minhas tarefas e** **planos compartilhados**, os usuários podem exibir e gerenciar todas as suas tarefas individuais e de equipe e priorizar seu trabalho. O Tasks está disponível em clientes de área de trabalho, web e dispositivos móveis do Teams.

> [!NOTE]
> À medida que implementamos a experiência de tarefas nos clientes de área de trabalho do Teams, o nome do aplicativo aparecerá inicialmente como **Planejador** para os usuários. O nome será alterado temporariamente para **Tasks pelo Planner e To Do** e, posteriormente, será renomeado para **Tasks**. Em clientes móveis do Teams, os usuários sempre verão o nome do aplicativo como **Tasks**. Pode haver um pequeno atraso na disponibilidade da experiência móvel depois que a experiência na área de trabalho estiver disponível.

:::image type="content" source="media/manage-tasks-app-tasks.png" alt-text="Captura de tela da exibição de lista de tarefas." lightbox="media/manage-tasks-app-tasks.png":::

Para organizações que desejam otimizar o gerenciamento de tarefas para os Trabalhadores da Linha de Frente, o Tasks também inclui recursos que permitem direcionar, publicar e rastrear tarefas em escala em toda a Força de Trabalho da Linha de Frente. Por exemplo, a liderança corporativa e regional pode criar e publicar listas de tarefas direcionadas a locais relevantes, como lojas de varejo específicas, e monitorar o progresso por meio de relatórios em tempo real. Os gerentes podem atribuir tarefas a seus funcionários e atividades diretas em seus locais, e os Trabalhadores de Linha de Frente têm uma lista priorizada de suas tarefas atribuídas no dispositivo móvel ou área de trabalho. Para [habilitar a publicação](#task-publishing) de tarefas, primeiro configure uma hierarquia de direcionamento de equipe para sua organização, que define como todas as equipes na hierarquia estão relacionadas entre si.

## <a name="what-you-need-to-know-about-tasks"></a>O que você precisa saber sobre o Tasks

O Tasks está disponível como um aplicativo e como uma guia em um canal. O aplicativo mostra tarefas individuais de Tarefas Pendentes e tarefas de equipe do Planner. A guia mostra apenas as tarefas da equipe.

Com o Tasks, os usuários obtêm uma experiência de desktop, web e celular. Se o Tasks estiver instalado no cliente de área de trabalho do Teams, os usuários também o verão em seus clientes da Web e móveis do Teams. A exceção são convidados. É importante saber que os convidados só podem acessar o Tasks como um aplicativo do cliente móvel do Teams. Os convidados verão as guias do Tasks na área de trabalho do Teams e nos clientes da web.

**Minhas tarefas** mostra as tarefas individuais de um usuário. **Planos compartilhados** mostram tarefas nas quais toda a equipe está trabalhando e inclui qualquer lista de tarefas adicionada como uma guia do Tasks a um canal. Observe as seguintes relações entre tarefas no Tasks, To Do e Planner:

- As listas de tarefas que um usuário cria no aplicativo Tarefas também aparecerão nos clientes Tarefas desse usuário. Da mesma forma, as listas de tarefas que um usuário cria no To Do aparecerão em **Minhas tarefas** no Tasks para esse usuário. O mesmo se aplica a tarefas individuais.

- Qualquer guia do Tasks adicionada a um canal também aparecerá nos clientes do Planner. Quando um usuário cria um plano no Planner, o plano não é mostrado no aplicativo Tarefas ou Planner, a menos que seja adicionado como uma guia a um canal. Quando um usuário adiciona uma nova guia do Tasks, ele pode criar uma nova lista ou plano ou escolher um existente.

## <a name="set-up-tasks"></a>Configurar Tasks

> [!IMPORTANT]
> As configurações e políticas que você configurou para o Planner também se aplicam ao Tasks.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Habilitar ou desabilitar o Tasks em sua organização

O Tasks é habilitado por padrão para todos os usuários do Teams em sua organização. Você pode desabilitar ou ligar o aplicativo no nível da organização na página [Gerenciar aplicativos](manage-apps.md) no centro de administração do Microsoft Teams.

1. No painel à esquerda do Centro de administração do Microsoft Teams, acesse **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Na lista de aplicativos, siga um destes procedimentos:

    - Para desativar as Tarefas da sua organização, pesquise o aplicativo Tarefas, selecione-o e selecione **Bloquear**.
    - Para ativar as Tarefas da sua organização, pesquise o aplicativo Tarefas, selecione-o e selecione **Permitir**.

> [!NOTE]
> Se você não conseguir localizar o aplicativo Tasks, procure os nomes na primeira nota deste artigo. O aplicativo ainda pode estar sendo renomeado.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Habilite ou desabilite o Tasks para usuários específicos em sua organização

Para permitir ou impedir que usuários específicos em sua organização usem o Tasks, certifique-se de que o Tasks esteja ativado para sua organização na página [Gerenciar aplicativos](manage-apps.md) e, em seguida, crie uma política de permissão de aplicativo personalizada e atribua-a esses usuários. Para saber mais, confira [Gerenciar políticas de permissão de aplicativo no Teams](teams-app-permission-policies.md).

### <a name="pin-tasks-to-teams"></a>Fixar tarefas no Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-tasks-and-other-apps-to-teams"></a>Usar a experiência de aplicativo de linha de frente personalizada para fixar tarefas e outros aplicativos no Teams

A experiência de aplicativo de linha de frente personalizada no Teams fixa os aplicativos mais relevantes no Teams para usuários que têm uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Os aplicativos fixados incluem Tarefas, Walkie Talkie, Turnos e Aprovações. Por padrão, esse recurso está ativado, oferecendo aos funcionários da linha de frente uma experiência integrada e adaptada às suas necessidades.

Os aplicativos são fixados na barra de aplicativos , a barra ao lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, em que os usuários podem facilmente accessá-los.

Para saber mais, incluindo como a experiência funciona com as políticas de aplicativo definidas por você, confira Personalizar aplicativos [do Teams para seus funcionários da linha de frente](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Use uma política de configuração de aplicativo para fixar o Tasks ao Teams

As políticas de configuração de aplicativo permitem que você personalize o Teams para fixar aplicativos que são mais importantes para seus usuários em seus usuários.

Para fixar o aplicativo Tasks para seus usuários, você pode editar a política global (Padrão em toda a organização) ou criar e atribuir uma política de configuração de aplicativo personalizada. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>Minhas tarefas de um usuário são visíveis se o usuário for licenciado para Exchange Online

Se não quiser que um usuário veja **Minhas tarefas**, você pode ocultá-lo. Para ocultar **minhas tarefas**, [remova a licença de Exchange Online usuário](/microsoft-365/admin/manage/remove-licenses-from-users). É importante saber que, depois de remover uma licença do Exchange Online, o usuário não tem mais acesso à caixa de correio.  Os dados da caixa de correio são retidos por 30 dias, após os quais os dados serão removidos e não podem ser recuperados, a menos que a caixa de correio seja colocada em [Bloqueio In-loco ou Retenção de Litígio ](/exchange/security-and-compliance/in-place-and-litigation-holds).

Não recomendamos remover uma licença do Exchange Online para operadores de informações, mas pode haver alguns cenários em que você pode ocultar Minhas tarefas dessa  maneira, como para trabalhadores de linha de frente que não dependem de email.

## <a name="task-publishing"></a>Publicação de tarefas

Com a publicação de tarefas, sua organização pode publicar listas de tarefas direcionadas a locais específicos (equipes) em sua organização para definir e compartilhar um plano de trabalho a ser concluído nesses locais.

- Pessoas na equipe de publicação, como lideranças corporativas ou regionais, podem criar listas de tarefas e publicá-las para equipes específicas.

    :::image type="content" source="media/manage-tasks-app-publish.png" alt-text="Captura de tela da publicação de tarefas." lightbox="media/manage-tasks-app-publish.png":::
- Os gerentes nas equipes destinatárias podem analisar as listas de tarefas publicadas e atribuir tarefas individuais aos membros da equipe.
    :::image type="content" source="media/manage-tasks-app-assign.png" alt-text="Captura de tela da atribuição de uma tarefa." lightbox="media/manage-tasks-app-assign.png":::
- Os funcionários da linha de frente têm uma experiência móvel simples para ver as tarefas atribuídas a eles. Eles podem anexar fotos para mostrar seu trabalho quando apropriado e marcar suas tarefas como concluídas.
- Editores e gerentes podem visualizar relatórios para ver a atribuição e o status de conclusão de tarefas em cada nível, incluindo por local (equipe), lista de tarefas e tarefa individual.
    :::image type="content" source="media/manage-tasks-app-reporting.png" alt-text="Captura de tela das tarefas publicadas." lightbox="media/manage-tasks-app-reporting.png":::

Os usuários criam, gerenciam e publicam listas de tarefas na guia **Listas publicadas** do aplicativo Tasks. Essa guia só é exibida para um usuário se sua organização[configurar uma hierarquia de segmentação de equipe](#set-up-your-team-targeting-hierarchy) e o usuário estiver em uma equipe incluída na hierarquia. A hierarquia determina se o usuário pode publicar ou receber listas de tarefas e visualizar relatórios de listas recebidas.

### <a name="example-scenario"></a>Cenário de exemplo

Aqui está um exemplo de como funciona a publicação de tarefas.

A Contoso está lançando uma nova promoção de comida para viagem e entrega. Para manter uma experiência de marca consistente, eles precisam coordenar a execução consistente do lançamento em mais de 300 lojas.

A equipe de Marketing compartilha os detalhes da promoção e a lista de tarefas correspondente com o Gerente de Comunicações de Varejo. O Gerente de Comunicações de Varejo, que atua como o gatekeeper para lojas, revisa as informações. Em seguida, eles criam uma lista de tarefas para a promoção e criam uma tarefa para cada unidade de trabalho que os repositórios afetados precisam executar. Quando a lista de tarefas for concluída, eles precisarão selecionar os repositórios que devem concluir o trabalho. Nesse caso, a promoção só se aplica a lojas nos Estados Unidos que tenham um restaurante interno. Em Tarefas, eles filtram a lista de lojas com base no atributo de restaurante na loja, selecionam os locais de Estados Unidos correspondentes na hierarquia e publicam a lista de tarefas nessas lojas.

Os gerentes do Microsoft Store em cada local recebem uma cópia das tarefas publicadas e atribuem essas tarefas aos membros de sua equipe. Os gerentes podem usar a experiência do Tasks para entender todo o trabalho necessário em sua loja. Eles também podem usar os filtros disponíveis para se concentrar em um conjunto específico de trabalho, como o trabalho com vencimento hoje ou o trabalho em uma área específica.

Trabalhadores da linha de Frente em cada local da loja agora têm uma lista priorizada de seu trabalho no Tasks em seus dispositivos móveis. Quando terminam uma tarefa, eles a marcam como concluída. Eles podem até optar por carregar e anexar uma foto à tarefa para mostrar seu trabalho.

A sede da Contoso e os gerentes intermediários podem exibir relatórios para ver a atribuição e o status de conclusão de tarefas em cada loja e entre as lojas. Eles também podem fazer drill down em uma tarefa específica para ver o status em diferentes lojas. Conforme a data de lançamento se aproxima, eles podem detectar qualquer anormalidade e verificar com suas equipes conforme necessário. Essa visibilidade permite que a Contoso melhore a eficiência da distribuição e forneça uma experiência mais consistente em suas lojas.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configure a hierarquia de segmentação de sua equipe

Para habilitar a publicação de tarefas em sua organização, você deve primeiro configurar o esquema de segmentação de sua equipe em um arquivo .CSV. O esquema define como todas as equipes em sua hierarquia estão relacionadas entre si e também define os atributos que podem ser usados para filtrar e selecionar equipes. Depois de criar o esquema, carregue-o no Teams para aplicá-lo à sua organização. Os membros da equipe de publicação, como o Gerente de Comunicações de Varejo no cenário de exemplo, podem filtrar as equipes por hierarquia, atributos ou uma combinação de ambos para selecionar as equipes relevantes que devem receber as listas de tarefas e, em seguida, publicar as listas de tarefas para essas equipes.

Para obter as etapas sobre como configurar a hierarquia de segmentação de sua equipe, consulte [Configurar a hierarquia de segmentação de sua equipe](set-up-your-team-hierarchy.md).

## <a name="power-automate-and-graph-api"></a>API Power Automate e Graph

O Tasks oferece suporte ao Power Automate para Tarefas Pendentes e APIs de Gráfico para Planner. Para saber mais, veja:

- [Visão geral da API de planos e tarefas do planejador](/graph/planner-concept-overview)
- [Usando a Microsoft To-Do para fazer com o Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
