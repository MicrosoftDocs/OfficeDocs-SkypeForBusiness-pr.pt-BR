---
title: Teams para Educação Assistente de Política para aplicar facilmente políticas para aprendizado seguro
author: cichur
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar o assistente de política Teams para Educação para aplicar facilmente políticas para alunos e educadores para manter seu ambiente de aprendizagem seguro.
f1keywords: ''
ms.openlocfilehash: de58471732304cf551d3c798f7f52a3bf9be1126
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605397"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Use o Assistente Teams para Educação política para aplicar facilmente políticas para um ambiente de aprendizado seguro

## <a name="overview"></a>Visão geral

O Microsoft Teams para Educação de Política simplifica o gerenciamento de políticas para seus alunos e educadores. Use-o para aplicar de forma fácil e rápida o conjunto mais importante de políticas relevantes para a criação de uma experiência de aprendizado segura e produtiva.

As políticas Teams permitir que você controle como Teams se comporta em seu ambiente e quais recursos estão disponíveis para os usuários. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para nomear alguns, e cada área de política pode ser personalizada para atender às necessidades da sua organização.

Para manter um ambiente de aprendizado seguro e focado, é importante definir políticas para controlar o que os alunos podem fazer Teams. Por exemplo, você pode usar políticas para controlar quem pode usar chat privado e chamada privada, quem pode agendar reuniões e quais tipos de conteúdo podem ser compartilhados. Você também pode usar políticas para ativar Teams recursos que enriquecem a experiência de aprendizado.

As políticas devem ser ajustadas para alunos e educadores manterem a experiência de aprendizado segura. As políticas para alunos precisam ser mais restritivas para reduzir o risco de receber níveis inadequados de acesso. Educadores e funcionários precisam de um conjunto separado de políticas que podem ser mais permissivas para permitir que eles sejam bem-sucedidos. Por exemplo, permitir que os educadores agendem reuniões e restrinjam os alunos a fazer isso.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de tela do assistente.":::

Este artigo explica como executar o assistente.

> [!IMPORTANT]
> As políticas aplicadas pelo assistente atenderão às necessidades da maioria dos Teams para Educação clientes. O assistente ajusta a definição Global (padrão em toda a organização) de um conjunto principal de políticas com configurações que recomendamos para a segurança do aluno e aplica-a aos alunos. O assistente também cria e atribui um conjunto de políticas personalizadas a educadores e funcionários. A maioria Teams para Educação clientes não precisarão usar outros métodos de atribuição de política após a execução deste assistente. Use outros métodos de atribuição de política *somente* se você quiser criar e gerenciar manualmente políticas para seus alunos, educadores e funcionários.

## <a name="teams-for-education-policy-wizard"></a>Teams para Educação Assistente de Política

<a name="polwiz_intro"> </a>

O assistente aplica um conjunto de definições de política básicas aos alunos e um conjunto separado de definições de política principais para educadores e funcionários, com configurações apropriadas para cada um. Veja o que acontece quando você executar o assistente.

O assistente configura políticas com base no tipo de instituição educacional ( Ensino Fundamental **ou Secundário** **ou Superior**). Você seleciona o tipo de instituição e o assistente faz o seguinte:

- **Alunos**: o assistente ajusta a definição de política Global (padrão em toda a organização) de cada área de política coberta pelo assistente com novas configurações padrão apropriadas para manter seus alunos seguros. Isso garante que seus alunos atuais e todos os novos alunos recebam o conjunto mais restritivo de políticas.
- **Educadores e** funcionários : o assistente cria um conjunto de definições de política personalizadas para cada área de política coberta pelo assistente com configurações adaptadas às necessidades de educadores e funcionários. Em seguida, ele atribui as definições de política ao grupo de educadores e funcionários escolhidos. Dessa forma, seus educadores e funcionários obterão um conjunto mais permissivo de políticas para permitir que eles sejam bem-sucedidos.

Você só precisa executar o assistente uma vez. Os novos alunos automaticamente têm as definições de política Global (padrão em toda a organização) aplicadas pelo assistente e pela nova equipe que você adiciona ao grupo selecionado são atribuídas automaticamente às políticas personalizadas.

Além disso, sempre que um novo recurso for adicionado ao Teams, o valor padrão apropriado eDU relevante da política para esse recurso será adicionado automaticamente ao global (padrão em toda a organização) sem exigir qualquer intervenção do administrador. Isso ajuda a garantir que as políticas corretas sejam realizadas para manter os alunos seguros e engajados.

> [!NOTE]
> Consulte [Políticas aplicadas pelo assistente](#policies-applied-by-the-wizard) para ver uma lista detalhada das definições de política aplicadas pelo assistente.

Agora, vamos começar!

## <a name="run-the-wizard"></a>Executar o assistente

<a name="polwiz_run"> </a>

Siga estas etapas para executar o assistente.

1. Se você for novo no Teams, o assistente será iniciado automaticamente. Caso contrário, você pode iniciar o assistente a qualquer momento a partir do painel. Na navegação à esquerda do centro de administração do Microsoft Teams,  vá para Home **e,** em seguida, na configuração de política Fácil para um painel de ambiente de aprendizado seguro, selecione **Configuração rápida**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de tela do assistente no painel.":::

2. Selecione seu tipo de instituição educacional (**Ensino Fundamental** ou Secundário ou Superior **)** e selecione **Próximo**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de tela da página no assistente para selecionar tipo de instituição.":::

3. Pesquise e selecione um grupo que contém seus educadores e funcionários e selecione **Próximo**. Se você ainda não tiver grupos definidos para seus [](/microsoft-365/admin/create-groups/create-groups)educadores e funcionários, crie um grupo e execute o assistente de novo. <br/><br/>Atualmente, você só pode selecionar um grupo. Educadores e funcionários no grupo selecionado receberão um [conjunto de políticas](#policies-applied-by-the-wizard) personalizadas adaptadas às suas necessidades. Lembre-se de que esse conjunto de políticas é separado das políticas aplicadas aos alunos.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Captura de tela do assistente de página para selecionar educador e grupo de funcionários.":::

4. Revise suas seleções.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Captura de tela do assistente de página para revisar seleções.":::

5. Selecione **Aplicar** para aplicar suas alterações. Isso pode levar alguns minutos para ser concluído.<br/><br/>As definições de política Global (padrão em toda a organização) são imediatamente aplicadas aos alunos. Para seus educadores e funcionários, pode levar algumas horas para que as políticas personalizadas sejam atribuídas a cada membro do grupo selecionado, dependendo do tamanho do grupo. Isso acontece em segundo plano, depois que você concluir com êxito esta etapa.
6. Você está a caminho, mas ainda não terminou! Há mais algumas coisas a considerar. Em seguida, confira as etapas na seção [O que fazer após a execução da](#what-to-do-after-running-the-wizard) seção assistente deste artigo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Captura de tela do assistente de página no para as próximas etapas.":::

## <a name="what-to-do-after-running-the-wizard"></a>O que fazer depois de executar o assistente

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Etapa 1: Remover atribuições de política existentes que conflitam com políticas aplicadas pelo assistente

> [!IMPORTANT]
> Conclua esta etapa somente se você tiver políticas existentes atribuídas a alunos ou educadores e **funcionários *antes* de ter o assistente.** Se você for novo no Teams e não tiver nenhuma política existente além das políticas criadas pelo assistente, ignore isso e vá para a etapa 2.

Em Teams, para uma determinada área de política, uma política pode ser aplicada a um usuário das seguintes maneiras:

- Atribuição direta ao usuário
- Atribuição a um grupo de que o usuário é membro
- Se o usuário não receber diretamente uma política ou não for membro de nenhum grupo atribuído a uma política, o usuário obtém automaticamente a política Global (padrão em toda a organização)

Se mais de uma dessas atribuições de política existirem para um usuário, Teams a ordem a seguir para determinar qual atribuição de política entra em vigor. Para obter mais informações, [consulte Qual política tem precedência ou](policy-assignment-overview.md#which-policy-takes-precedence) regras de [precedência para grupos](assign-policies-users-and-groups.md#precedence-rules).

|Atribuições de política de um usuário|Política que entra em vigor |
|---------|---------|
|Política atribuída ao grupo: Não<br/>Política atribuída diretamente ao usuário: Não    |Política padrão global (em toda a organização)      |
|Política atribuída ao grupo: Não<br/>Política atribuída diretamente ao usuário: Sim    |Política atribuída diretamente ao usuário         |
|Política atribuída ao grupo: Sim<br/>Política atribuída diretamente ao usuário: Sim     |Política atribuída diretamente ao usuário         |
|Política atribuída ao grupo: Sim<br/>Política atribuída diretamente ao usuário: Não     |Política atribuída ao grupo<br/><br/>Se o usuário for membro de vários grupos e cada grupo tiver uma política da mesma área de política, a política com a classificação de atribuição de grupo mais alta [entra](assign-policies-users-and-groups.md#group-assignment-ranking) em vigor.       |

Devido a essa ordem, as políticas criadas pelo assistente não tomarão efeito se um usuário tiver atribuições diretas ou atribuições de grupo existentes. Isso significa que você terá que remover as atribuições de política existentes do usuário para que a política aplicada pelo assistente entre em vigor.

Para cada [área de política aplicada pelo assistente,](#policies-applied-by-the-wizard)faça o seguinte:

- Remova todas as atribuições diretas e atribuições de grupo existentes de seus alunos para que a definição de política Global (padrão em toda a organização) aplicada pelo assistente entre em vigor.
- Remova quaisquer atribuições diretas conflitantes para seus educadores e funcionários para que a definição de política personalizada criada pelo assistente entre em vigor. Use a tabela acima para determinar os cenários que se aplicam a você. <br/><br/>Lembre-se de que o assistente atribui políticas aos seus educadores e grupo de funcionários usando [uma](assign-policies-users-and-groups.md#group-assignment-ranking) classificação de atribuição de grupo de 1, que é a classificação mais alta. Se seus educadores e grupo de funcionários tiver uma política existente da mesma área de política atribuída a ela, essa política existente será movida para uma classificação mais baixa e a política atribuída pelo assistente entra em vigor.

[Saiba mais](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sobre como remover políticas atribuídas diretamente aos usuários.

Por exemplo, você atribuiu uma política de reunião diretamente aos educadores e seus alunos têm a política de reunião Global (padrão em toda a organização). Nesse cenário, remova a política de reunião que você atribuiu diretamente aos educadores para que a definição de política personalizada para a política de reunião criada pelo assistente entre em vigor. Você não precisa fazer nada com a política de reunião global (padrão em toda a organização) para os alunos porque nenhuma outra política de reunião entra em conflito com ela.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Etapa 2: Verifique se há medidas adicionais que você pode tomar para garantir a segurança do aluno

O assistente ajusta e aplica essas [políticas automaticamente.](#policies-applied-by-the-wizard) Existem poucas medidas adicionais, que você pode querer tomar com base nas necessidades da sua instituição para se manter segura.

Consulte [Mantendo os alunos seguros ao usar Teams para aprendizagem a distância](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) para obter recomendações de segurança adicionais.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Etapa 3: Verificar o Centro de Mensagens para atualizações de política

Atualmente, o assistente aplica nossas políticas recomendadas ao executar. É importante saber que, à medida que novas políticas se tornam disponíveis no Teams, as configurações Globais (padrão em toda a organização) para segurança do aluno são atualizadas automaticamente pelo assistente. 

Mas verifique o [Centro](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) de Mensagens (no Centro de administração do Microsoft 365) com frequência para se manter atualizado sobre os novos recursos e suas políticas e configurações de política no Teams. 

## <a name="make-changes-in-the-wizard"></a>Fazer alterações no assistente

<a name="polwiz_change"> </a>

Se você precisar fazer alterações depois de executar o assistente, poderá re runá-lo e alterar suas seleções.

1. Na navegação à esquerda do centro de administração do Microsoft Teams,  vá para Home **e,** em seguida, na configuração de política Fácil para um painel de ambiente de aprendizado seguro, selecione **Alterar**.
2. A partir daqui, continue por cada página do assistente para fazer suas alterações. Você pode alterar o tipo de instituição, o grupo de educadores e funcionários aos quais deseja atribuir políticas ou ambos.

A tabela a seguir resume o que acontece quando você faz uma alteração no assistente.

|Tipo de alteração  |Comportamento da política  |
|---------|---------|
|Alterar o tipo de instituição educacional e os educadores e o grupo de funcionários    |<ul><li>**Alunos**: As definições de política global (padrão em toda a organização) com base no novo tipo de instituição educacional são aplicadas aos alunos.</li><li>**Educadores e funcionários**: um conjunto de definições de política personalizadas com base no novo tipo de instituição educacional é criado e atribuído ao novo educador e grupo de funcionários. As definições de política personalizadas anteriores são removidas dos educadores anteriores e do grupo de funcionários.</li></ul>    |
|Alterar apenas o tipo de instituição educacional    |<ul><li>**Alunos**: As definições de política global (padrão em toda a organização) com base no novo tipo de instituição educacional são aplicadas aos alunos.</li><li>**Educadores e** funcionários : um conjunto de definições de política personalizadas com base no novo tipo de instituição educacional é criado e atribuído aos educadores e ao grupo de funcionários. As definições de política personalizadas criadas para o tipo de instituição educacional anterior são removidas dos educadores e do grupo de funcionários.</li></ul>         |
|Alterar apenas os educadores e o grupo de funcionários   |<ul><li>**Alunos**: Nenhuma alteração nas definições de política Global (padrão em toda a organização) aplicadas aos alunos.</li><li>**Educadores e funcionários**: As definições de política personalizadas são atribuídas aos novos educadores e ao grupo de funcionários e removidas dos educadores anteriores e do grupo de funcionários.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Políticas aplicadas pelo assistente

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Áreas de política

Aqui estão as áreas de política e os nomes de política correspondentes cobertos pelo assistente. Para encontrar essas políticas, vá para o centro de administração Microsoft Teams e, na navegação à esquerda, vá para cada página de área de política.

#### <a name="students"></a>[**Alunos**](#tab/students/)

|Área de política  |Nome da política primária ou secundária |Nome da política de ensino superior  |
|---------|---------|---------|
|Políticas do Teams    |Global (padrão em toda a organização)         |Global (padrão em toda a organização)           |
|Políticas de reunião    |Global (padrão em toda a organização)           |Global (padrão em toda a organização)           |
|Políticas de eventos ao vivo     |Global (padrão em toda a organização)          |  Global (padrão em toda a organização)          |
|Política de configuração de aplicativo     |Global (padrão em toda a organização)           |Global (padrão em toda a organização)           |
|Política de permissão do aplicativo    |Global (padrão em toda a organização)           |Global (padrão em toda a organização)           |
|Políticas de mensagens     |Global (padrão em toda a organização)           |Global (padrão em toda a organização)           |
|Políticas de chamada    |Global (padrão em toda a organização)           |Global (padrão em toda a organização)           |

#### <a name="educators-and-staff"></a>[**Educadores e funcionários**](#tab/educators/)

|Área de política  |Nome da política primária ou secundária |Nome da política de ensino superior |
|---------|---------|---------|
|Políticas do Teams   |Educadores e funcionários primários ou secundários - Teams         |Professores e Funcionários do Ensino Superior - Teams         |
|Políticas de reunião    |Educadores e funcionários primários ou secundários - Reunião         |Professores e Funcionários do Ensino Superior - Reunião         |
|Políticas de eventos ao vivo   | Educadores e Funcionários Primários ou Secundários - Eventos ao vivo         |Professores e Funcionários do Ensino Superior - Eventos ao vivo         |
|Políticas de mensagens    |Professores e funcionários primários ou secundários - Mensagens         | Professores e Funcionários do Ensino Superior - Mensagens         |
|Políticas de chamada    |Professores e funcionários primários ou secundários - Chamada         |Educadores e Funcionários de Educação Superior - Chamada         |

* * *

### <a name="policy-settings"></a>Configurações de política

Aqui está um resumo das configurações aplicadas pelo assistente para cada área de política.

#### <a name="students"></a>[**Alunos**](#tab/student-settings/)

Aqui está uma lista das definições de política Global (padrão em toda a organização) ajustadas pelo assistente e aplicadas aos alunos.

|Área de política |Sub-área  |Configuração de política  |Primário ou Secundário |Ensino superior |
|---------|---------|---------|---------|---------|
|Políticas do Teams   |         |Criar canais privados         |Desabilitado       |Habilitado|
|Política de reuniões    |Geral         |Permitir Reunir agora nos canais         |Desabilitado      |Habilitado|
|  |        |Permitir o suplemento do Outlook         |Desabilitado       |Habilitado|
|  |        |Permitir o agendamento de reunião do canal        |Desabilitado      |Habilitado|
|  |        |Permitir o agendamento de reuniões particulares       |Desabilitado      |Habilitado|
|  |        |Permitir registro de reunião              |Habilitado       |Habilitado|
|  |        |Who pode se registrar    |Todos na organização      |Todos na organização|
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
|  |       |Who pode gravar um evento         |Always         |Always|
|Políticas de mensagens  |       |Os proprietários podem excluir as mensagens enviadas         |Desabilitado|Habilitado|
|  |       |Apagar mensagens enviadas         |Desabilitado         |Habilitado|
|  |       |Editar mensagens enviadas         |Desabilitado         |Habilitado|
|  |       |Confirmação de leitura         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |Chat         |Desabilitado         |Habilitado|
|  |       |Usar Giphys em conversas         |Desabilitado         |Habilitado|
|  |       |Classificação de conteúdo Giphy         |Estrito        |Estrito|
|  |       |Usar Memes em conversas         |Habilitado         |Habilitado|
|  |       |Usar Adesivos em conversas         |Habilitado         |Habilitado|
|  |       |Permitir visualizações de URL        |Habilitado         |Habilitado|
|  |       |Traduzir mensagens         |Habilitado         |Habilitado|
|  |       |Permitir leitor imersivo para exibir mensagens        |Habilitado      |Habilitado|
|  |       |Envie mensagens urgentes usando notificações prioritárias  |Desabilitado         |Habilitado|
|  |       |Criar mensagens de voz         |Permitido em chats e canais         |Permitido em chats e canais|
|  |       |Em dispositivos móveis, exibe canais favoritos acima de chats recentes     |Habilitado         |Habilitado|
|  |       |Remover usuários de chats em grupo         |Desabilitado         |Habilitado|
|Política de permissão do aplicativo  |       |Aplicativos da Microsoft         |Bloquear aplicativos específicos e permitir que todos os outros > Walkie Talkie bloqueados         |Permitir todos os aplicativos|
|  |       |Aplicativos de terceiros         |Permitir todos os aplicativos         |Permitir todos os aplicativos|
|  |       |Aplicativos personalizados         |Permitir todos os aplicativos         |Permitir todos os aplicativos|
|Política de configuração de aplicativo  |           |Upload aplicativos personalizados           |Desabilitado         |Desabilitado|
|  |       |Permitir o pinamento do usuário |Habilitado         |Habilitado|
|  |       |Aplicativos instalados         |Nenhum         |Nenhum|
|  |       |Aplicativos fixados         |Atividade, Calendário, Teams         |Atividade, Chats, Teams, Calendário, Chamada, Arquivo
|Políticas de chamada  |       |Fazer chamadas privadas         |Desabilitado        |Habilitado|
|  |       |Encaminhamento de chamada e toque simultâneo para pessoas em sua organização         |Desabilitado         |Habilitado|
|  |       |Encaminhamento de chamadas e toque simultâneo para números de telefone externos         |Desabilitado         |Habilitado|
|  |       |A caixa postal está disponível para roteamento de chamadas de entrada         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |Chamadas de entrada podem ser roteados para grupos de chamadas         |Desabilitado        |Habilitado|
|  |       |Permitir delegação para chamadas de entrada e saída         |Desabilitado         |Habilitado|
|  |       |Impedir o desvio de chamada e enviar chamadas por meio da PSTN        |Desabilitado         |Desabilitado|
|  |       |O ocupado ocupado está disponível quando em uma chamada         |Desabilitado         |Desabilitado|
|  |       |Permitir chamada PSTN web         |Desabilitado         |Habilitado|

#### <a name="educators-and-staff"></a>[**Educadores e funcionários**](#tab/educator-settings/)

Aqui está uma lista das definições de política personalizadas atribuídas aos educadores e ao grupo de funcionários que você escolhe no assistente.  

|Área de política |Sub-área  |Configuração de política  |Primário ou Secundário |Ensino superior |
|---------|---------|---------|---------|---------|
|Políticas do Teams   |         |Criar canais privados         |Habilitado       |Habilitado|
|Política de reuniões    |Geral         |Permitir Reunir agora nos canais         |Habilitado      |Habilitado|
|  |        |Permitir o suplemento do Outlook         |Habilitado       |Habilitado|
|  |        |Permitir o agendamento de reunião do canal        |Habilitado      |Habilitado|
|  |        |Permitir o agendamento de reuniões particulares       |Habilitado      |Habilitado|
|  |        |Permitir registro de reunião              |Habilitado       |Habilitado|
|  |        |Who pode se registrar    |Todos na organização      |Todos na organização|
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
|  |       |Who pode gravar um evento         |Sempre gravar         |Sempre gravar|
|Políticas de mensagens  |       |Os proprietários podem excluir as mensagens enviadas         |Habilitado|Habilitado|
|  |       |Apagar mensagens enviadas         |Habilitado         |Habilitado|
|  |       |Editar mensagens enviadas         |Habilitado         |Habilitado|
|  |       |Confirmação de leitura         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |Chat         |Habilitado         |Habilitado
|  |       |Usar Giphys em conversas         |Habilitado        |Habilitado|
|  |       |Classificação de conteúdo Giphy         |Estrito        |Estrito|
|  |       |Usar Memes em conversas         |Habilitado         |Habilitado|
|  |       |Usar Adesivos em conversas         |Habilitado         |Habilitado|
|  |       |Permitir visualizações de URL        |Habilitado         |Habilitado|
|  |       |Traduzir mensagens         |Habilitado         |Habilitado|
|  |       |Permitir leitor imersivo para exibir mensagens        |Habilitado      |Habilitado|
|  |       |Envie mensagens urgentes usando notificações prioritárias  |Habilitado         |Habilitado|
|  |       |Criar mensagens de voz         |Permitido em chats e canais         |Permitido em chats e canais|
|  |       |Em dispositivos móveis, exibe canais favoritos acima de chats recentes     |Habilitado         |Habilitado|
|  |       |Remover usuários de chats em grupo         |Habilitado        |Habilitado|
|Políticas de chamada  |       |Fazer chamadas privadas         |Habilitado       |Habilitado|
|  |       |Encaminhamento de chamada e toque simultâneo para pessoas em sua organização         |Habilitado        |Habilitado|
|  |       |Encaminhamento de chamadas e toque simultâneo para números de telefone externos         |Habilitado        |Habilitado|
|  |       |A caixa postal está disponível para roteamento de chamadas de entrada         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |Chamadas de entrada podem ser roteados para grupos de chamadas         |Habilitado        |Habilitado|
|  |       |Permitir delegação para chamadas de entrada e saída         |Habilitado         |Habilitado|
|  |       |Impedir o desvio de chamada e enviar chamadas por meio da PSTN        |Desabilitado         |Desabilitado|
|  |       |O ocupado ocupado está disponível quando em uma chamada         |Desabilitado         |Desabilitado|
|  |       |Permitir chamada PSTN web         |Habilitado      |Habilitado|

* * *

## <a name="related-topics"></a>Tópicos relacionados

- [Políticas do Teams e pacotes de políticas para Educação](policy-packages-edu.md)
- [Atribuir políticas a grandes conjuntos de usuários em sua escola](batch-group-policy-assignment-edu.md)
- [Manter os alunos seguros durante o uso Teams para aprendizagem à distância](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
