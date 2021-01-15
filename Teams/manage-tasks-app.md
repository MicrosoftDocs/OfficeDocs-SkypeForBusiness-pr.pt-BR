---
title: Gerenciar o aplicativo Tarefas para sua organização no Microsoft Teams
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
description: Saiba como gerenciar o aplicativo Tarefas para usuários em sua organização.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba8c1129edbff492d09ea5c103c25c399fc4a58a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822731"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Gerenciar o aplicativo Tarefas para sua organização no Microsoft Teams

## <a name="overview-of-tasks"></a>Visão geral das tarefas

O aplicativo Tarefas traz uma experiência de gerenciamento de tarefas coeso para o Microsoft Teams, integrando tarefas individuais acionadas pelo [Microsoft To Do](https://todo.microsoft.com/tasks/) e tarefas de equipe acionadas pelo Planner em um só lugar. Os usuários podem acessar Tarefas como um aplicativo no lado esquerdo do Teams e como uma guia em um canal dentro de equipes individuais. **Minhas tarefas e** **planos compartilhados** em Tarefas permitem que os usuários visualizam e gerenciem todas as tarefas individuais e de equipe e priorizem seu trabalho. As tarefas estão disponíveis nos clientes móveis, da web e da área de trabalho do Teams. 

> [!NOTE]
> À medida que lançarmos a experiência tarefas em clientes da área de trabalho do Teams, o nome do aplicativo aparecerá inicialmente como **Planner** para os usuários. Em seguida, o nome será temporariamente alterado para Tarefas pelo Planner e Para **Fazer** e, posteriormente, ele será renomeado para **Tarefas.** Nos clientes móveis do Teams, os usuários sempre verão o nome do aplicativo como **Tarefas.** Pode haver um pequeno atraso na disponibilidade da experiência móvel depois que a experiência da área de trabalho está disponível.

   ![Captura de tela da exibição de lista de tarefas na lista do Teams](media/manage-tasks-app-tasks.png)

Para organizações que querem simplificar o gerenciamento de tarefas para Os Trabalhadores da Linha de Frente, as Tarefas também incluem recursos que permitem direcionar, publicar e controlar tarefas em escala em toda a Força de Trabalho da Linha de Frente. Por exemplo, a liderança corporativa e regional pode criar e publicar listas de tarefas direcionadas a locais relevantes, como lojas comerciais específicas, e acompanhar o progresso por meio de relatórios em tempo real. Os gerentes podem atribuir tarefas à equipe e atividades diretas dentro de seus locais, e os Trabalhadores de Linha de Frente têm uma lista priorizada de suas tarefas atribuídas em dispositivos móveis ou desktop. Para [habilitar](#task-publishing)a publicação de tarefas, primeiro você precisará configurar uma hierarquia de direcionamento de equipe para sua organização, que define como todas as equipes na hierarquia estão relacionadas umas às outras.

## <a name="what-you-need-to-know-about-tasks"></a>O que você precisa saber sobre tarefas

As tarefas estão disponíveis como um aplicativo e como uma guia em um canal. Tenha em mente que o aplicativo compreende tarefas individuais do To Do e tarefas de equipe do Planner, enquanto a guia mostra apenas tarefas de equipe.

Com Tarefas, os usuários podem obter uma experiência desktop, web e móvel. Se o Tasks estiver instalado no cliente da área de trabalho do Teams, os usuários também o verão em seus clientes móveis e da Web do Teams. A exceção são os usuários convidados. É importante saber que os convidados só podem acessar Tarefas como um aplicativo do cliente móvel do Teams. Os convidados verão as guias Tarefas nos clientes da Web e da área de trabalho do Teams.

**Minhas tarefas** mostram as tarefas individuais de um usuário. **Os planos compartilhados** mostram tarefas em que toda a equipe está trabalhando e inclui qualquer lista de tarefas adicionada como uma guia Tarefas a um canal. Observe o seguinte:

- As listas de tarefas que um usuário cria no aplicativo Tarefas também aparecerão nos clientes To Do desse usuário. Da mesma forma, as listas de tarefas que um usuário cria em To Do aparecerão em **Minhas tarefas** em Tarefas desse usuário. O mesmo vale para tarefas individuais.

- Qualquer guia Tarefas adicionada a um canal também aparecerá nos clientes do Planner. Quando um usuário cria um plano no Planner, o plano não aparece no aplicativo Tarefas ou planner, a menos que seja adicionado como uma guia a um canal. Quando um usuário adiciona uma nova guia Tarefas, ele pode criar uma nova lista ou planejar ou escolher uma existente.

## <a name="set-up-tasks"></a>Configurar Tarefas

> [!IMPORTANT]
> As configurações e políticas que você configurou para o Planner também serão aplicadas a Tarefas.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Habilitar ou desabilitar tarefas em sua organização

As tarefas são habilitadas por padrão para todos os usuários do Teams em sua organização. Você pode desativar ou ativar o aplicativo no [](manage-apps.md) nível da organização na página Gerenciar aplicativos no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Na lista de aplicativos, faça um dos seguintes:

    - Para desativar as tarefas da sua organização, pesquise o aplicativo Tarefas, selecione-o e clique em **Bloquear.**
    - Para ativar as tarefas da sua organização, pesquise o aplicativo Tarefas, selecione-o e clique em **Permitir**.

> [!NOTE]
> Se você não conseguir encontrar o aplicativo Tarefas, procure os nomes na primeira nota deste artigo. O aplicativo ainda pode estar em processo de renomeação.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Habilitar ou desabilitar tarefas para usuários específicos em sua organização

Para permitir ou impedir que usuários específicos em sua organização usem [](manage-apps.md) Tarefas, certifique-se de que As Tarefas estão tivas para sua organização na página Gerenciar aplicativos e, em seguida, crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. Para saber mais, confira [Gerenciar políticas de permissão de aplicativo no Teams.](teams-app-permission-policies.md)

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Usar uma política de configuração de aplicativo para fixar tarefas no Teams

As políticas de configuração de aplicativo permitem personalizar o Teams para realçar os aplicativos mais importantes para os usuários em sua organização. Os aplicativos definidos em uma política são fixados na barra de aplicativos na barra do lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, onde os usuários podem acessá-los de forma rápida e &mdash; &mdash; fácil.

Para fixar o aplicativo Tarefas para seus usuários, você pode editar a política global (padrão em toda a organização) ou criar e atribuir uma política de configuração de aplicativo personalizada. Para saber mais, confira [Gerenciar políticas de configuração de aplicativo no Teams.](teams-app-setup-policies.md)

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>Minhas tarefas de um usuário fica visível se o usuário estiver licenciado para o Exchange Online

Se você não quiser que um usuário veja **Minhas tarefas,** você pode o ocultar. Para fazer isso, [remova a licença do Exchange Online do usuário.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) É importante saber que, depois de remover uma licença do Exchange Online, o usuário não tem mais acesso à caixa de correio.  Os dados da caixa de correio são mantidos por 30 dias, após o qual os dados serão removidos e não poderão ser recuperados, a menos que a caixa de correio seja colocada em Espera Local ou Em [Litígio.](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

Não recomendamos isso para profissionais da informação, mas pode haver alguns cenários em que isso pode se aplicar, como para trabalhadores da linha de frente que não dependem de email.

## <a name="task-publishing"></a>Publicação de tarefas

Com a publicação de tarefas, sua organização pode publicar listas de tarefas direcionadas a locais específicos (equipes) em sua organização para definir e compartilhar um plano de trabalho a ser concluído nesses locais.

- As pessoas na equipe de publicação, como liderança corporativa ou regional, podem criar listas de tarefas e publicá-las em equipes específicas.<br>
    ![Captura de tela da publicação de tarefas](media/manage-tasks-app-publish.png)
- Os gerentes nas equipes de destinatários podem revisar as listas de tarefas publicadas e atribuir tarefas individuais aos membros da equipe.<br>
    ![Captura de tela da atribuição de uma tarefa](media/manage-tasks-app-assign.png)
- Os Trabalhadores da Linha de Frente têm uma experiência móvel simples para ver as tarefas atribuídas a eles. Eles podem anexar fotos para mostrar seu trabalho quando apropriado e marcar suas tarefas como concluídas.
- Os editores e gerentes podem exibir relatórios para ver o status de atribuição e conclusão de tarefas em cada nível, incluindo por local (equipe), lista de tarefas e tarefa individual.<br>
    ![Captura de tela de tarefas atribuídas em dispositivos móveis](media/manage-tasks-app-reporting.png)

Os usuários criam, gerenciam e publicam listas de tarefas na guia Listas **publicadas** no aplicativo Tarefas. Essa guia só será aberta para um usuário se [sua](#set-up-your-team-targeting-hierarchy) organização configurar uma hierarquia de direcionamento de equipe e o usuário estiver em uma equipe incluída na hierarquia. A hierarquia determina se o usuário pode publicar ou receber listas de tarefas e exibir relatórios de listas recebidas.

### <a name="example-scenario"></a>Cenário de exemplo

Aqui está um exemplo de como a publicação de tarefas funciona.

A Contoso está lançando uma nova promoção de distribuição e distribuição de produtos. Para manter uma experiência de marca consistente, eles precisam coordenar a execução consistente da lançamento em mais de 300 locais da loja.

A equipe de Marketing compartilha os detalhes da promoção e a lista correspondente de tarefas com o Gerente de Comunicações de Varejo. O Gerente de Comunicações de Varejo, que serve como o gatekeeper para lojas, revisa as informações, cria uma lista de tarefas para a promoção e cria uma tarefa para cada unidade de trabalho que precisa ser executada por cada um dos armazenamentos afetados. Quando a lista de tarefas estiver concluída, ela precisará selecionar os armazenamentos que devem concluir o trabalho. Nesse caso, a promoção só se aplica a lojas nos Estados Unidos que tenham um restaurante na loja. Em Tarefas, ela filtra a lista da loja com base no atributo de restaurante na loja, seleciona os locais correspondentes dos Estados Unidos na hierarquia e publica a lista de tarefas nessas lojas.

Os gerentes da Loja em cada local recebem uma cópia das tarefas publicadas e atribuem essas tarefas aos membros da equipe. Os gerentes podem usar a experiência tarefas para entender todo o trabalho necessário em sua loja. Eles também podem usar os filtros disponíveis para se concentrar em um conjunto específico de trabalho, como trabalho com vencimento hoje ou trabalho em uma área específica.

Os Trabalhadores da Linha de Frente em cada local da loja agora têm uma lista priorizada de seu trabalho em Tarefas em seu dispositivo móvel. Quando terminam uma tarefa, marcam-na concluída. Alguns podem até optar por carregar e anexar uma foto à tarefa para mostrar seu trabalho.

A sede da Contoso e os gerentes intermediários podem exibir relatórios para ver o status de atribuição e conclusão das tarefas em cada loja e entre lojas. Eles também podem detalhar uma tarefa específica para ver o status em diferentes lojas. À medida que a data de início se aproxima, eles podem detectar qualquer anormais e fazer check-in com suas equipes conforme necessário. Essa visibilidade permite que a Contoso melhore a eficiência da lançamento e forneça uma experiência mais consistente em suas lojas.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurar sua hierarquia de direcionamento de equipe

Para habilitar a publicação de tarefas em sua organização, você precisa primeiro configurar o esquema de direcionamento de equipe em um . Arquivo CSV. O esquema define como todas as equipes em sua hierarquia estão relacionadas umas às outras e os atributos usados para filtrar e selecionar equipes. Depois de criar o esquema, carregue-o no Teams para aplicá-lo à sua organização. Os membros da equipe de publicação, como o Gerente de Comunicações de Varejo no cenário de exemplo, podem filtrar equipes por hierarquia, atributos ou uma combinação de ambos para selecionar as equipes relevantes que devem receber as listas de tarefas e, em seguida, publicar as listas de tarefas para essas equipes.

Para etapas sobre como configurar sua hierarquia de direcionamento de equipe, consulte [Configurar sua hierarquia de direcionamento de equipe.](set-up-your-team-hierarchy.md)

## <a name="power-automate-and-graph-api"></a>Api do Power Automate e do Graph

As tarefas são compatíveis com o Power Automate for To Do e as APIs do Graph para Planner. Para saber mais, veja:

- [Visão geral da API de tarefas e planos do Planner](https://docs.microsoft.com/graph/planner-concept-overview)
- [Usando o Microsoft To Do com o Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
