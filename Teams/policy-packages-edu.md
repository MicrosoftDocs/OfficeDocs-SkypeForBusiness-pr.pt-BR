---
title: Políticas do Microsoft Teams e pacotes de políticas para administradores EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: Saiba mais sobre políticas em uma configuração EDU ou educacional e como usar e gerenciar pacotes de políticas no Microsoft Teams.
ms.openlocfilehash: f8bda2fc5741b9575fa2eabc786b7e565a86f2ea
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262468"
---
# <a name="teams-policies-and-policy-packages-for-education"></a>Políticas do Teams e Pacotes de Políticas para Educação

> [!NOTE]
> Para obter um conhecimento amplo sobre políticas no Microsoft Teams, analise [Atribuir políticas a usuários no Microsoft Teams](assign-policies.md).

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a>Administradores: Introdução ao gerenciamento de política do Microsoft Teams

O Microsoft Teams permite que os usuários realizem ações como participar de reuniões online ou eventos ao vivo, conversar, fazer chamadas e usar aplicativos. Definir as políticas de administração corretas do Microsoft Teams é uma etapa crítica para garantir que o Teams seja um ambiente de aprendizado seguro para os alunos. Como administrador, você pode usar políticas para controlar os recursos do Teams que estão disponíveis para os usuários em sua instituição educacional.  Na maioria dos casos, as políticas devem ser ajustadas para estudantes e professores para que o ambiente seja seguro.  

Aqui está uma lista das principais áreas de políticas que você encontrará no Microsoft Teams. Para saber mais sobre as políticas em cada área e os recursos que eles controlam, use os links a seguir:

- [Reuniões](meeting-policies-in-teams.md)
- [Eventos ao vivo](teams-live-events/configure-teams-live-events.md)
- [Chamadas](teams-calling-policy.md) 
- [Mensagens](messaging-policies-in-teams.md)
- [Teams](teams-policies.md)
- [Permissões de aplicativo](teams-app-permission-policies.md)

:::image type="content" source="media/edu-admin-center-users.png" alt-text="Captura de tela do usuário com políticas aplicadas.":::

Você pode gerenciar todas as políticas do Teams no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) entrando com suas credenciais de administrador.

### <a name="where-to-find-microsoft-teams-policies"></a>Onde encontrar as políticas do Microsoft Teams

Depois de fazer logon no centro de administração do Teams, você poderá acessar as configurações de políticas de qualquer área do Teams que você precisa gerenciar, clicando na opção de política na navegação à esquerda do centro de administração do Teams. Incluímos uma captura de tela do local das políticas de mensagens.

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Local da política de mensagens no centro de administração do Teams.":::

### <a name="how-to-create-and-update-a-policy-definition"></a>Como criar e atualizar uma definição de política

Antes de atribuir políticas a usuários, você precisa primeiro adicionar e criar suas definições de políticas para cada área de recursos com o Teams.

> [!NOTE]
> Recomendamos que você configure diferentes definições de políticas para alunos e educadores.

Por padrão, cada novo usuário (aluno ou educador) receberá a definição de política Global (padrão em toda a organização) para cada área de recursos. Recomendamos o uso da política global (padrão para toda a organização) para o seu conjunto mais estrito de definições de política. Na maioria dos casos, esse conjunto de políticas estrita será mais apropriado para os alunos. Usar a definição de política global (padrão para toda a organização), dessa maneira garantirá que os novos usuários terão restrições ao serem adicionadas ao seu locatário. Para aderir à essas diretrizes, recomendamos que você siga essas etapas:

1. Crie uma definição de política personalizada para cada área de recursos do Teams com valores de política que se ajustem às suas necessidades (sem isso, os educadores terão o mesmo acesso restrito que seus alunos, conforme definido na definição de política global (padrão para toda a organização)).

1. Atribua essas novas definições de política personalizada aos seus educadores.

1. Edite as definições de política global (padrão para toda a organização) para cada área de recurso com valores apropriados para seus alunos.

1. As definições de política global (padrão para toda a organização) serão aplicadas aos seus alunos, desde que não tenham nenhuma outra definição de política atribuída.


Para criar ou editar definições de política, vá para a área de recursos da política na qual deseja trabalhar (por exemplo, políticas de Mensagens). Selecione **Adicionar** para criar uma nova definição de política personalizada. Para alterar uma definição de política existente, selecione **Editar**.

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="Fechar a seção de políticas de mensagens com uma exibição do botão Adicionar.":::

Se você optar por adicionar ou editar uma definição de política, você será levado a uma exibição que lista todas as opções de política relacionadas a essa área de política. Use esta lista para selecionar quais valores você deseja definir em sua definição de política.

![Uma página com as opções de política relacionadas à área de política que você escolheu.](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> Não se esqueça de selecionar **Salvar** antes de sair da página.

### <a name="assigning-policy-definitions"></a>Atribuindo definições de política 
Há vários métodos que você pode usar para atribuir definições de política aos seus usuários. Cada método tem suas próprias vantagens e desvantagens, que serão diferentes dependendo das necessidades exclusivas da instituição.  

Na maioria dos casos, recomendamos que você use a atribuição de política de grupo para atribuir políticas aos seus usuários. Esse método permite um programa de política mais rápido e mais simples.  Quando um usuário é adicionado a um grupo que tem uma definição de política atribuída a ele, o novo usuário herda automaticamente as políticas do grupo.  Isso permite o gerenciamento simplificado de políticas quando grandes quantidades de usuários são adicionados e removidos do ambiente, por exemplo, no início e no final de um termo escolar.  

Para as grandes organizações, também recomendamos uma atribuição de política em lote, que é adaptada para casos em que você precisa atribuir políticas a grandes conjuntos de usuários. Para saber mais sobre esses métodos de programa, confira [Atribuir políticas a grandes conjuntos de usuários na escola](batch-group-policy-assignment-edu.md).

Se você tiver uma instituição menor ou precisar atualizar as configurações individuais de política de um aluno ou professor, siga as instruções abaixo.  

> [!IMPORTANT]
> As atribuições de política determinadas no nível de usuário individual substituem quaisquer políticas de grupo atribuídas ao usuário. Certifique-se de que você esteja usando atribuições de política individuais quando quiser substituir as configurações da política de grupo. 

#### <a name="how-to-assign-a-policy-definition-to-a-user"></a>Como atribuir uma definição de política a um usuário

> [!NOTE]
> A atribuição de uma definição de política pode demorar um pouco para se propagar para todos os usuários e clientes. Você pode fazer isso quando as contas de usuário forem criadas pela primeira vez no Azure/M365 e sempre que um novo aluno ingressa na instituição educacional.


Depois que sua definição de política for criada ou atualizada, você poderá atribuí-la a um usuário, selecionando **Gerenciar usuários** na página de políticas, pesquisando o usuário desejado e aplicando a política.

![Painel Gerenciar usuários, no lado direito, na parte superior da página Políticas de mensagens.](media/edu-manage-users-pane.png)

Você também pode atribuir uma política a um usuário, navegando até **Usuários**, selecionando o usuário para o qual deseja atualizar as políticas, selecionando **Políticas**, e, em seguida, **Editar**. A partir daí, você pode selecionar a definição de política que deseja atribuir ao usuário para cada área de recursos.

![Edite o painel de políticas do usuário, no lado direito da página Políticas atribuídas.](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a>Pacotes de política no Microsoft Teams
> [!NOTE]
> Para obter mais informações, confira [Gerenciar pacotes de políticas no Microsoft Teams](manage-policy-packages.md) para obter instruções passo a passo sobre como atribuir um único usuário a um pacote, atribuir pacotes em massa para até 5000 usuários e gerenciar e atualizar as políticas vinculadas a cada pacote.

Um pacote de políticas no Teams coleta políticas predefinidas e configurações de políticas que você aprendeu e estão descritas acima e as atribui a usuários com funções semelhantes em sua instituição. Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas. Em prática normal, você atribui a cada um de seus usuários um pacote de políticas e redefine as políticas em cada pacote conforme necessário para atender às necessidades desse grupo de usuários. Quando você atualiza as configurações em um pacote, todos os usuários atribuídos a esse pacote são alterados como uma atualização em massa.

As instituições educacionais em geral têm muitos usuários com necessidades únicas, dependendo em parte da idade e maturidade dos estudantes. Por exemplo, você pode conceder aos educadores e funcionários acesso total ao Microsoft Teams, mas deseja limitar os recursos do Microsoft Teams para que os alunos incentivem um ambiente de aprendizado seguro e focado. Você pode usar pacotes de políticas para personalizar as configurações com base nas necessidades de diferentes coortes na comunidade da sua instituição educacional.

> [!IMPORTANT] 
> Nossa principal recomendação é usar a definição de política global (padrão para toda a organização) para estudantes em vez de um pacote de política. Isso garante que os novos usuários nas organizações sempre tenham o conjunto de políticas mais estrito apropriado para os alunos. Se essa recomendação não atender às necessidades da sua instituição, um dos pacotes de política do aluno abaixo poderá ser uma boa alternativa. 

Assim como a lista de políticas anteriormente neste artigo, os pacotes de políticas predefinem as políticas para:

- Reuniões
- Eventos ao vivo
- Chamadas
- Mensagens
- Permissões de aplicativos

No momento, o Microsoft Teams inclui os seguintes pacotes de políticas:

|Nome do pacote listado no centro de Administração do Microsoft Teams |Melhor usado para  |Descrição |
|:--- |:--- |:--- |
|**Education_Teacher**| Educadores e funcionários| Use esse conjunto de políticas e configurações de políticas para conceder aos educadores e funcionários de sua organização acesso total a chat, chamadas e reuniões por meio do Microsoft Teams. |
|**Education_PrimaryStudent**| Alunos do ensino fundamental  | Os alunos mais jovens do ensino fundamental da sua instituição podem precisar de mais limites no Microsoft Teams. Use esse conjunto de políticas e configurações de políticas para limitar recursos como criação e gerenciamento de reuniões, gerenciamento de chat e chamadas privadas. |
|**Education_SecondaryStudent**| Alunos do ensino médio | Os alunos do ensino médio da sua instituição podem precisar de mais limites no Microsoft Teams. Use esse conjunto de políticas e configurações de políticas para limitar recursos como criação e gerenciamento de reuniões, gerenciamento de chat e chamadas privadas. |
|**Education_HigherEducationStudent**| Alunos do ensino superior | Os alunos do ensino superior dentro da sua intuição podem precisar de menos limites do que os alunos mais jovens, mas algumas limitações podem ser recomendadas. Você pode usar esse conjunto de políticas e configurações de políticas para conceder acesso a chats, chamadas e reuniões em sua organização, mas limite como os alunos usam o Microsoft Teams com participantes externos. |
|**Education_PrimaryTeacher_RemoteLearning**| Educadores e funcionários | Cria um conjunto de políticas que se aplicam aos professores primários para maximizar a segurança e a colaboração dos alunos ao usar o aprendizado remoto. |
|**Education_PrimaryStudent_RemoteLearning**| Alunos do ensino fundamental| Cria um conjunto de políticas que se aplicam aos alunos do ensino fundamental para maximizar a segurança e a colaboração dos alunos ao usarem o aprendizado remoto.
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="Página de pacotes de políticas com a lista de pacotes de política à sua escolha.":::

Cada política individual recebe o nome do pacote de políticas, para que você possa identificar políticas vinculadas a um pacote de políticas. Por exemplo, quando você atribui o pacote de políticas Education_Teacher a educadores em sua instituição educacional, uma política chamada Education_Teacher é criada para cada política no pacote.

![Captura de tela do pacote de política Education_Teacher](media/policy-packages-education_teacher.png)

> [!NOTE]
> Se você decidir que os educadores e a equipe de suporte administrativo precisam de políticas diferentes, poderá redefinir um pacote existente: identifique um pacote que não esteja usando no momento e altere as configurações para que sejam apropriadas para esse grupo. Você pode ter que anotar qual grupo tem qual pacote, mas esse é o único impedimento para a redefinição de um pacote.

## <a name="policies-that-should-be-assigned-for-student-safety"></a>Políticas que devem ser atribuídas à segurança do estudante
Para obter mais informações sobre as etapas necessárias para proteger os alunos em seu ambiente, reveja cuidadosamente [Manter os alunos seguros enquanto usam o Teams para aprendizagem à distância](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).
