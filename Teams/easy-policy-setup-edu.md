---
title: Assistente de Política do Teams para Educação para aplicar facilmente políticas de aprendizagem segura
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: shajohri, angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar o assistente de política do Teams for Education para aplicar políticas facilmente para alunos e educadores para manter seu ambiente de aprendizagem seguro.
f1keywords: ''
ms.openlocfilehash: 1ea7fb684bce3d59063f1a258d0db37fb75a4681
ms.sourcegitcommit: 95b85926d67cbf3159f58d9083d5813cc29074f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790415"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Usar o Assistente de Política do Teams para Educação para aplicar facilmente políticas para um ambiente de aprendizagem seguro

## <a name="overview"></a>Visão Geral

O Assistente de Política do Microsoft Teams para Educação simplifica o gerenciamento de políticas para seus alunos e educadores. Use-o para aplicar de forma fácil e rápida o conjunto mais importante de políticas relevantes à criação de uma experiência de aprendizagem segura e produtiva.

As políticas no Teams permitem controlar como o Teams se comporta em seu ambiente e quais recursos estão disponíveis para os usuários. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar alguns, e cada área de política pode ser personalizada para atender às necessidades da sua organização.

Para manter um ambiente de aprendizagem seguro e focado, é importante definir políticas para controlar o que os alunos podem fazer no Teams. Por exemplo, você pode usar políticas para controlar quem pode usar chat privado e chamada privada, quem pode agendar reuniões e quais tipos de conteúdo podem ser compartilhados. Você também pode usar políticas para ativar recursos do Teams que enriquecem a experiência de aprendizagem.

As políticas devem ser ajustadas para alunos e educadores para manter a experiência de aprendizagem segura. As políticas para os alunos precisam ser mais restritivas para reduzir o risco de receber níveis inadequados de acesso. Educadores e funcionários precisam de um conjunto separado de políticas que podem ser mais permissivas para permitir que eles sejam bem-sucedidos. Por exemplo, permita que os educadores agendem reuniões e restrinjam os alunos de fazê-lo.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de tela do assistente":::

Este artigo explica como executar o assistente.

> [!IMPORTANT]
> As políticas aplicadas pelo assistente atenderão às necessidades da maioria dos clientes do Teams for Education. O assistente ajusta a definição Global (padrão em toda a organização) de um conjunto principal de políticas com configurações que recomendamos para a segurança do aluno e aplica-a aos alunos. O assistente também cria e atribui um conjunto de políticas personalizadas a educadores e funcionários. A maioria dos clientes do Teams for Education não precisará usar outros métodos de atribuição de política após executar este assistente. Use outros métodos de atribuição de política *somente* se você quiser criar e gerenciar manualmente políticas para seus alunos, educadores e funcionários.

## <a name="teams-for-education-policy-wizard"></a>Assistente de Política do Teams para Educação

<a name="polwiz_intro"> </a>

O assistente aplica um conjunto de definições de política principais aos alunos e um conjunto separado de definições de política principais para educadores e funcionários, com configurações apropriadas para cada um. Veja o que acontece quando você executar o assistente.

O assistente configura políticas com base no tipo de instituição de ensino **(Ensino** Fundamental ou Médio **ou Superior).** Você seleciona o tipo da instituição e o assistente faz o seguinte:

- **Alunos:** O assistente ajusta a definição de política Global (padrão em toda a organização) de cada área de política coberta pelo assistente com novas configurações padrão apropriadas para manter seus alunos seguros. Isso garante que seus alunos atuais e todos os novos alunos recebam o conjunto mais restritivo de políticas.
- **Educadores e** funcionários: o assistente cria um conjunto de definições de política personalizadas para cada área de política coberta pelo assistente com configurações personalizadas para as necessidades de educadores e funcionários. Em seguida, ele atribui as definições de política ao grupo de educadores e funcionários que você escolher. Dessa forma, seus educadores e funcionários obterão um conjunto mais permissivo de políticas para que eles sejam bem-sucedidos.

Você só precisa executar o assistente uma vez. Os novos alunos automaticamente têm as definições de política Global (padrão em toda a organização) aplicadas pelo assistente e a nova equipe que você adicionar ao grupo selecionado recebe automaticamente as políticas personalizadas.

> [!NOTE]
> Consulte [Políticas aplicadas pelo assistente para](#policies-applied-by-the-wizard) ver uma lista detalhada de definições de política aplicadas pelo assistente.

Agora, vamos começar!

## <a name="run-the-wizard"></a>Executar o assistente

<a name="polwiz_run"> </a>

Siga estas etapas para executar o assistente.

1. Se você for novo no Teams, o assistente será iniciado automaticamente. Caso contrário, você pode iniciar o assistente a qualquer momento no painel. Na navegação à esquerda do Centro de administração do Microsoft  Teams, vá para Painel **e,** em seguida, na configuração de política Fácil para um painel de ambiente de aprendizagem seguro, selecione **Configuração rápida.**

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de tela do assistente no painel":::

2. Selecione o tipo da instituição de ensino **(ensino fundamental** ou **médio** ou superior) e selecione **Próximo.**

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de tela da página no assistente para selecionar o tipo de instituição":::

3. Pesquise e selecione um grupo que contenha seus professores e funcionários e selecione **Próximo.** Se você ainda não tiver nenhum grupo definido para [](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)seus educadores e funcionários, crie um grupo e execute o assistente de novo. <br/><br/>Atualmente, você só pode selecionar um grupo. Professores e funcionários do grupo selecionado receberão um conjunto de [políticas](#policies-applied-by-the-wizard) personalizadas adaptadas às suas necessidades. Lembre-se de que esse conjunto de políticas é separado das políticas aplicadas aos alunos.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Captura de tela da página no assistente para selecionar educador e grupo de funcionários":::

4. Revise suas seleções.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Captura de tela da página no assistente para revisar seleções":::

5. Selecione **Aplicar** para aplicar suas alterações. Isso pode levar alguns minutos para ser concluído.<br/><br/>As definições de política global (padrão em toda a organização) são imediatamente aplicadas aos alunos. Para seus educadores e funcionários, pode levar algumas horas para que as políticas personalizadas sejam atribuídas a cada membro do grupo que você selecionou, dependendo do tamanho do grupo. Isso acontece em segundo plano, depois que você conclui esta etapa com êxito.
6. Você está a caminho, mas ainda não terminou! Há mais algumas coisas a considerar. Em seguida, confira as etapas na seção O que fazer depois de [executar a seção assistente](#what-to-do-after-running-the-wizard) deste artigo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Captura de tela da página no assistente para as próximas etapas":::

## <a name="what-to-do-after-running-the-wizard"></a>O que fazer depois de executar o assistente

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Etapa 1: remover atribuições de política existentes que estão em conflito com as políticas aplicadas pelo assistente

> [!IMPORTANT]
> **Conclua esta etapa somente se você tiver políticas existentes atribuídas a alunos, educadores e funcionários *antes* de ter sido o assistente.** Se você for novo no Teams e não tiver outras políticas existentes além das políticas criadas pelo assistente, pule essa etapa e vá para a etapa 2.

No Teams, para uma determinada área de política, uma política pode ser aplicada a um usuário das seguintes maneiras:

- Atribuição direta ao usuário
- Atribuição a um grupo do que o usuário é membro
- Se o usuário não receber uma política diretamente ou não for membro de nenhum grupo que atribuiu uma política, o usuário automaticamente obtém a política Global (padrão de toda a organização)

Se mais de uma dessas atribuições de política existirem para um usuário, o Teams usará a seguinte ordem para determinar qual atribuição de política entra em vigor. Para saber mais, confira [Qual política tem precedência?](assign-policies.md#which-policy-takes-precedence) e [Regras de Precedência.](assign-policies.md#precedence-rules)

|Atribuições de política de um usuário|Política que entra em vigor |
|---------|---------|
|Política atribuída ao grupo: Não<br/>Política atribuída diretamente ao usuário: Não    |Política padrão global (em toda a organização)      |
|Política atribuída ao grupo: Não<br/>Política atribuída diretamente ao usuário: Sim    |Política atribuída diretamente ao usuário         |
|Política atribuída ao grupo: Sim<br/>Política atribuída diretamente ao usuário: Sim     |Política atribuída diretamente ao usuário         |
|Política atribuída ao grupo: Sim<br/>Política atribuída diretamente ao usuário: Não     |Política atribuída ao grupo<br/><br/>Se o usuário for membro de vários grupos e cada grupo tiver uma política da mesma área de política, a política que tiver a classificação de atribuição de grupo mais alta [terá](assign-policies.md#group-assignment-ranking) efeito.       |

Por causa dessa ordem, as políticas criadas pelo assistente não vigorarão se um usuário tiver atribuições diretas ou atribuições de grupo existentes. Isso significa que você terá que remover as atribuições de política existentes do usuário para que a política aplicada pelo assistente entre em vigor.

Para cada [área de política aplicada pelo assistente,](#policies-applied-by-the-wizard)faça o seguinte:

- Remova todas as atribuições diretas e atribuições de grupo existentes de seus alunos para que a definição de política Global (padrão de toda a organização) aplicada pelo assistente entre em vigor.
- Remova todas as atribuições diretas conflitantes para seus educadores e funcionários para que a definição de política personalizada criada pelo assistente entre em vigor. Use a tabela acima para determinar os cenários que se aplicam a você. <br/><br/>Lembre-se de que o assistente atribui políticas aos professores e ao grupo de funcionários usando [uma](assign-policies.md#group-assignment-ranking) classificação de atribuição de grupo de 1, que é a classificação mais alta. Se seus educadores e grupo de funcionários tiver uma política existente da mesma área de política atribuída a ele, essa política existente será movida para uma classificação mais baixa e a política atribuída pelo assistente terá efeito.

[Saiba mais](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sobre como remover políticas atribuídas diretamente aos usuários.

Por exemplo, você atribuiu uma política de reunião diretamente aos educadores e seus alunos têm a política de reunião Global (padrão de toda a organização). Nesse cenário, remova a política de reunião atribuída diretamente aos educadores para que a definição de política personalizada para a política de reunião criada pelo assistente entre em vigor. Você não precisa fazer nada com a política de reunião global (padrão em toda a organização) para os alunos porque nenhuma outra política de reunião entra em conflito com ela.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Etapa 2: verifique se há medidas adicionais que podem ser tomadas para a segurança do aluno

O assistente ajusta e aplica essas [políticas automaticamente.](#policies-applied-by-the-wizard) Há algumas medidas adicionais que talvez você queira tomar com base nas necessidades de sua instituição para se manter segura.

Veja [Como manter os alunos seguros ao usar o Teams para aprendizagem à distância](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) para obter recomendações de segurança adicionais.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Etapa 3: Verificar se há atualizações de política no Centro de Mensagens

Atualmente, o assistente aplica nossas políticas recomendadas quando você o executar. É importante saber que, à medida que novas políticas se tornam disponíveis no Teams, as configurações globais (padrão de toda a organização) para a segurança do aluno não são adicionadas automaticamente pelo assistente. Esse recurso estará disponível em uma versão futura.

Até que esse recurso fique disponível, verifique o Centro de Mensagens [(no](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) Centro de administração do Microsoft 365) com frequência para se manter atualizado sobre novas políticas e configurações de política no Teams. À medida que novos recursos se tornam disponíveis, talvez seja preciso atualizar manualmente suas políticas para manter seu ambiente de aprendizagem seguro.

## <a name="make-changes-in-the-wizard"></a>Fazer alterações no assistente

<a name="polwiz_change"> </a>

Se precisar fazer alterações depois de executar o assistente, execute-o e altere suas seleções.

1. Na navegação à esquerda do Centro de administração do Microsoft  Teams, vá para Painel **e,** em seguida, na configuração de política Fácil para um painel de ambiente de aprendizagem seguro, selecione **Alterar.**
2. A partir daqui, continue em cada página do assistente para fazer suas alterações. Você pode alterar o tipo da instituição, o grupo de educadores e funcionários ao qual deseja atribuir políticas ou ambos.

A tabela a seguir resume o que acontece quando você faz uma alteração no assistente.

|Tipo de alteração  |Comportamento da política  |
|---------|---------|
|Alterar o tipo da instituição de ensino, os educadores e o grupo de funcionários    |<ul><li>**Alunos:** as definições de política global (padrão em toda a organização) com base no novo tipo de instituição de ensino são aplicadas aos alunos.</li><li>**Educadores e funcionários:** um conjunto de definições de política personalizada com base no novo tipo de instituição de ensino é criado e atribuído ao novo educador e grupo de funcionários. As definições de política personalizada anteriores são removidas dos professores e do grupo de funcionários anteriores.</li></ul>    |
|Alterar apenas o tipo de instituição de ensino    |<ul><li>**Alunos:** as definições de política global (padrão em toda a organização) com base no novo tipo de instituição de ensino são aplicadas aos alunos.</li><li>**Educadores e funcionários:** um conjunto de definições de política personalizada com base no novo tipo de instituição de ensino é criado e atribuído aos educadores e ao grupo de funcionários. As definições de política personalizada criadas para o tipo de instituição de ensino anterior são removidas dos educadores e do grupo de funcionários.</li></ul>         |
|Alterar somente os educadores e o grupo de funcionários   |<ul><li>**Alunos:** nenhuma alteração nas definições de política Global (padrão em toda a organização) aplicadas aos alunos.</li><li>**Educadores e funcionários:** as definições de política personalizada são atribuídas aos novos educadores e grupo de funcionários e removidas dos professores e do grupo de funcionários anteriores.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Políticas aplicadas pelo assistente

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Áreas de política

Aqui estão as áreas de política e os nomes de política correspondentes cobertos pelo assistente. Para encontrar essas políticas, vá para o Centro de administração do Microsoft Teams e, na navegação à esquerda, vá para cada página da área de política.

#### <a name="students"></a>[**Estudantes**](#tab/students/)

|Área de política  |Nome da política primária ou secundária |Nome da política de ensino superior  |
|---------|---------|---------|
|Políticas do Teams    |Global (padrão de toda a organização)         |Global (padrão de toda a organização)           |
|Políticas de reunião    |Global (padrão de toda a organização)           |Global (padrão de toda a organização)           |
|Políticas de eventos ao vivo     |Global (padrão de toda a organização)          |  Global (padrão de toda a organização)          |
|Política de configuração de aplicativo     |Global (padrão de toda a organização)           |Global (padrão de toda a organização)           |
|Política de permissão do aplicativo    |Global (padrão de toda a organização)           |Global (padrão de toda a organização)           |
|Políticas de mensagens     |Global (padrão de toda a organização)           |Global (padrão de toda a organização)           |
|Políticas de chamada    |Global (padrão de toda a organização)           |Global (padrão de toda a organização)           |

#### <a name="educators-and-staff"></a>[**Educadores e funcionários**](#tab/educators/)

|Área de política  |Nome da política primária ou secundária |Nome da política de ensino superior |
|---------|---------|---------|
|Políticas do Teams   |Professores e Funcionários Primários ou Secundários – Teams         |Professores e Funcionários do Ensino Superior - Teams         |
|Políticas de reunião    |Professores e Funcionários Primários ou Secundários - Reunião         |Professores e Funcionários do Ensino Superior - Reunião         |
|Políticas de eventos ao vivo   | Professores e funcionários primários ou secundários – eventos ao vivo         |Professores e Funcionários do Ensino Superior - Eventos ao vivo         |
|Políticas de mensagens    |Professores e Funcionários Primários ou Secundários - Mensagens         | Professores e Funcionários do Ensino Superior - Mensagens         |
|Políticas de chamada    |Professores e Funcionários Primários ou Secundários - Chamada         |Professores e Funcionários do Ensino Superior - Chamada         |

* * *

### <a name="policy-settings"></a>Configurações de política

Aqui está um resumo das configurações aplicadas pelo assistente para cada área de política.

#### <a name="students"></a>[**Estudantes**](#tab/student-settings/)

Aqui está uma lista das definições de política Global (padrão em toda a organização) ajustadas pelo assistente e aplicadas aos alunos.

|Área de política |Subá area  |Configuração de política  |Principal ou Secundário |Ensino superior |
|---------|---------|---------|---------|---------|
|Políticas do Teams   |         |Criar canais privados         |Desabilitado       |Habilitado|
|Política de reuniões    |Geral         |Permitir Reunir agora nos canais         |Desabilitado      |Habilitado|
|  |        |Permitir o suplemento do Outlook         |Desabilitado       |Habilitado|
|  |        |Permitir o agendamento de reunião do canal        |Desabilitado      |Habilitado|
|  |        |Permitir o agendamento de reuniões particulares       |Desabilitado      |Habilitado|
|  |Vídeo & áudio        |Permitir transcrição        |Habilitado       |Habilitado|
|  |        |Permitir gravação na nuvem         |Desabilitado      |Habilitado|
|  |        |Modo de áudio IP       |Áudio de saída e entrada habilitado        |Áudio de saída e entrada habilitado|
|  |        |Modo de vídeo IP         |Vídeo de saída e entrada habilitado     |Vídeo de saída e entrada habilitado|
|  |       |Permitir vídeo IP         |Habilitado         |Habilitado|
|  |       |Permitir streaming de NDI         |Desabilitado         |Desabilitado|
|  |       |Taxa de bits de mídia (Kbs)         |50.000         |50.000|
|  |Compartilhamento de conteúdo       |Modo de compartilhamento de tela         |Tela inteira         |Tela inteira|
|  |       |Permitir que um participante conceda ou solicite o controle         |Habilitado         |Habilitado|
|  |       |Permitir que um participante externo conceda ou solicite o controle         |Habilitado         |Habilitado|
|  |       |Permitir compartilhamento do PowerPoint        |Habilitado         |Habilitado|
|  |       |Permitir o quadro de comunicações         |Habilitado         |Habilitado|
|  |       |Permitir notas compartilhadas         |Habilitado        |Habilitado|
|  |Participantes & convidados       |Permitir que pessoas anônimas iniciem uma reunião       |Desabilitado         |Habilitado|
|  |       |Funções que têm direitos de apresentador em reuniões        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Aceitar pessoas automaticamente        |EveryoneInCompany|EveryoneInCompany|
|  |       |Permitir que os usuários de acesso telefônico ignorem o lobby        |Desabilitado         |Desabilitado|
|  |       |Permitir Reunir Agora em reuniões particulares        |Desabilitado         |Habilitado|
|  |       |Habilitar legendas ao vivo       |Desabilitado, mas o usuário pode substituir         |Desabilitado, mas o usuário pode substituir|
|  |       |Permitir chat em reuniões         |Habilitado         |Habilitado|
|Políticas de eventos ao vivo  |       |Permitir agendamento         |Desabilitado         |Desabilitado|
|  |       |Permitir transcrição para participantes          |Habilitado       |Habilitado|
|  |       |Quem pode ingressar eventos ao vivo agendados        |Todos na organização        |Todos na organização|
|  |       |Quem pode gravar um evento         |Sempre         |Sempre|
|Políticas de mensagens  |       |Os proprietários podem excluir as mensagens enviadas         |Desabilitado|Habilitado|
|  |       |Apagar mensagens enviadas         |Desabilitado         |Habilitado|
|  |       |Editar mensagens enviadas         |Desabilitado         |Habilitado|
|  |       |Recibos de leitura         |Usuário controlado         |Usuário controlado|
|  |       |Chat         |Desabilitado         |Habilitado|
|  |       |Usar Giphys em conversas         |Desabilitado         |Habilitado|
|  |       |Classificação de conteúdo Giphy         |Estrito        |Estrito|
|  |       |Usar Memes em conversas         |Habilitado         |Habilitado|
|  |       |Usar adesivos em conversas         |Habilitado         |Habilitado|
|  |       |Permitir visualizações de URL        |Habilitado         |Habilitado|
|  |       |Traduzir mensagens         |Habilitado         |Habilitado|
|  |       |Permitir leitura imersiva para exibir mensagens        |Habilitado      |Habilitado|
|  |       |Enviar mensagens urgentes usando notificações de prioridade  |Desabilitado         |Habilitado|
|  |       |Criar mensagens de voz         |Permitido em chats e canais         |Permitido em chats e canais|
|  |       |Em dispositivos móveis, exibir canais favoritos acima de chats recentes     |Habilitado         |Habilitado|
|  |       |Remover usuários de chats em grupo         |Desabilitado         |Habilitado|
|Política de permissão do aplicativo  |       |Aplicativos da Microsoft         |Bloquear aplicativos específicos e permitir que todos os > Walkie Talkie bloqueados         |Permitir todos os aplicativos|
|  |       |Aplicativos de terceiros         |Permitir todos os aplicativos         |Permitir todos os aplicativos|
|  |       |Aplicativos personalizados         |Permitir todos os aplicativos         |Permitir todos os aplicativos|
|Política de configuração de aplicativo  |           |Carregar aplicativos personalizados           |Desabilitado         |Desabilitado|
|  |       |Permitir a pinagem do usuário |Habilitado         |Habilitado|
|  |       |Aplicativos instalados         |Nenhum         |Nenhum|
|  |       |Aplicativos fixados         |Atividade, Calendário, Teams         |Atividade, Chats, Equipes, Calendário, Chamada, Arquivo
|Políticas de chamada  |       |Fazer chamadas privadas         |Desabilitado        |Habilitado|
|  |       |Encaminhamento de chamada e toque simultâneo para as pessoas em sua organização         |Desabilitado         |Habilitado|
|  |       |Encaminhamento de chamadas e toque simultâneo para números de telefone externos         |Desabilitado         |Habilitado|
|  |       |A caixa postal está disponível para roteamento de chamadas de entrada         |Usuário controlado         |Usuário controlado|
|  |       |As chamadas de entrada podem ser roteada para grupos de chamadas         |Desabilitado        |Habilitado|
|  |       |Permitir delegação para chamadas de entrada e saída         |Desabilitado         |Habilitado|
|  |       |Impedir o bypass de chamada tarifada e enviar chamadas pelo PSTN        |Desabilitado         |Desabilitado|
|  |       |Ocupado está disponível quando está em uma chamada         |Desabilitado         |Desabilitado|
|  |       |Permitir chamada PSTN Web         |Desabilitado         |Habilitado|

#### <a name="educators-and-staff"></a>[**Educadores e funcionários**](#tab/educator-settings/)

Aqui está uma lista das definições de política personalizada atribuídas aos educadores e grupo de funcionários que você escolhe no assistente.  

|Área de política |Subá area  |Configuração de política  |Principal ou Secundário |Ensino superior |
|---------|---------|---------|---------|---------|
|Políticas do Teams   |         |Criar canais privados         |Habilitado       |Habilitado|
|Política de reuniões    |Geral         |Permitir Reunir agora nos canais         |Habilitado      |Habilitado|
|  |        |Permitir o suplemento do Outlook         |Habilitado       |Habilitado|
|  |        |Permitir o agendamento de reunião do canal        |Habilitado      |Habilitado|
|  |        |Permitir o agendamento de reuniões particulares       |Habilitado      |Habilitado|
|  |Vídeo & áudio        |Permitir transcrição        |Habilitado       |Habilitado|
|  |        |Permitir gravação na nuvem         |Habilitado      |Habilitado|
|  |        |Modo de áudio IP       |Áudio de saída e entrada habilitado        |Áudio de saída e entrada habilitado|
|  |        |Modo de vídeo IP         |Vídeo de saída e entrada habilitado     |Vídeo de saída e entrada habilitado|
|  |       |Permitir vídeo IP         |Habilitado         |Habilitado|
|  |       |Permitir streaming de NDI         |Desabilitado         |Desabilitado|
|  |       |Taxa de bits de mídia (Kbs)         |50.000         |50.000|
|  |Compartilhamento de conteúdo       |Modo de compartilhamento de tela         |Tela inteira         |Tela inteira|
|  |       |Permitir que um participante conceda ou solicite o controle         |Habilitado         |Habilitado|
|  |       |Permitir que um participante externo conceda ou solicite o controle         |Habilitado         |Habilitado|
|  |       |Permitir compartilhamento do PowerPoint        |Habilitado         |Habilitado|
|  |       |Permitir o quadro de comunicações         |Habilitado         |Habilitado|
|  |       |Permitir notas compartilhadas         |Habilitado        |Habilitado|
|  |Participantes & convidados       |Permitir que pessoas anônimas iniciem uma reunião       |Habilitado        |Habilitado|
|  |       |Funções que têm direitos de apresentador em reuniões        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Aceitar pessoas automaticamente        |OrganizerOnly|OrganizerOnly|
|  |       |Permitir que os usuários de acesso telefônico ignorem o lobby        |Desabilitado         |Desabilitado|
|  |       |Permitir Reunir Agora em reuniões particulares        |Habilitado         |Habilitado|
|  |       |Habilitar legendas ao vivo       |Desabilitado, mas o usuário pode substituir         |Desabilitado, mas o usuário pode substituir|
|  |       |Permitir chat em reuniões         |Habilitado         |Habilitado|
|Políticas de eventos ao vivo  |       |Permitir agendamento         |Habilitado         |Habilitado|
|  |       |Permitir transcrição para participantes          |Habilitado       |Habilitado|
|  |       |Quem pode ingressar eventos ao vivo agendados        |Todos na organização        |Todos na organização|
|  |       |Quem pode gravar um evento         |Gravar sempre         |Gravar sempre|
|Políticas de mensagens  |       |Os proprietários podem excluir as mensagens enviadas         |Habilitado|Habilitado|
|  |       |Apagar mensagens enviadas         |Habilitado         |Habilitado|
|  |       |Editar mensagens enviadas         |Habilitado         |Habilitado|
|  |       |Recibos de leitura         |Usuário controlado         |Usuário controlado|
|  |       |Chat         |Habilitado         |Habilitado
|  |       |Usar Giphys em conversas         |Habilitado        |Habilitado|
|  |       |Classificação de conteúdo Giphy         |Estrito        |Estrito|
|  |       |Usar Memes em conversas         |Habilitado         |Habilitado|
|  |       |Usar adesivos em conversas         |Habilitado         |Habilitado|
|  |       |Permitir visualizações de URL        |Habilitado         |Habilitado|
|  |       |Traduzir mensagens         |Habilitado         |Habilitado|
|  |       |Permitir leitura imersiva para exibir mensagens        |Habilitado      |Habilitado|
|  |       |Enviar mensagens urgentes usando notificações de prioridade  |Habilitado         |Habilitado|
|  |       |Criar mensagens de voz         |Permitido em chats e canais         |Permitido em chats e canais|
|  |       |Em dispositivos móveis, exibir canais favoritos acima de chats recentes     |Habilitado         |Habilitado|
|  |       |Remover usuários de chats em grupo         |Habilitado        |Habilitado|
|Políticas de chamada  |       |Fazer chamadas privadas         |Habilitado       |Habilitado|
|  |       |Encaminhamento de chamada e toque simultâneo para as pessoas em sua organização         |Habilitado        |Habilitado|
|  |       |Encaminhamento de chamadas e toque simultâneo para números de telefone externos         |Habilitado        |Habilitado|
|  |       |A caixa postal está disponível para roteamento de chamadas de entrada         |Usuário controlado         |Usuário controlado|
|  |       |As chamadas de entrada podem ser roteada para grupos de chamadas         |Habilitado        |Habilitado|
|  |       |Permitir delegação para chamadas de entrada e saída         |Habilitado         |Habilitado|
|  |       |Impedir o bypass de chamada tarifada e enviar chamadas pelo PSTN        |Desabilitado         |Desabilitado|
|  |       |Ocupado está disponível quando está em uma chamada         |Desabilitado         |Desabilitado|
|  |       |Permitir chamada PSTN Web         |Habilitado      |Habilitado|

* * *

## <a name="related-topics"></a>Tópicos relacionados

- [Pacotes de políticas e políticas do Teams para Educação](policy-packages-edu.md)
- [Atribuir políticas a grandes conjuntos de usuários em sua escola](batch-group-policy-assignment-edu.md)
- [Manter os alunos seguros ao usar o Teams para aprendizagem à distância](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
