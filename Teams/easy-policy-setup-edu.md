---
title: Assistente do teams for Education Policy para aplicar facilmente as políticas de aprendizado seguro
author: lanachin
ms.author: v-lanac
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
description: Saiba como usar o assistente de política do teams para educação para aplicar facilmente as políticas para alunos e professores para manter seu ambiente de aprendizagem seguro.
f1keywords: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d72ef20a8ae56fba67534944d229d01468531207
ms.sourcegitcommit: 80c1ec1d5a43b9259a4da6db3e462f6d4257bfa7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49564247"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Usar o assistente de políticas para educação para aplicar facilmente políticas para um ambiente de aprendizagem seguro

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Visão geral

O assistente de política do Microsoft Teams para educação simplifica o gerenciamento de políticas para alunos e professores. Use-o para aplicar com facilidade e rapidez o conjunto mais importante de políticas relevante para criar uma experiência de aprendizagem segura e produtiva.

As políticas no Teams permitem que você controle como as equipes se comparam ao seu ambiente e quais recursos estão disponíveis para os usuários. Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para mencionar alguns, e cada área de cada política pode ser personalizada para atender às necessidades da sua organização.

Para manter um ambiente de aprendizagem seguro e focado, é importante definir políticas para controlar o que os alunos podem fazer no Teams. Por exemplo, você pode usar políticas para controlar quem pode usar o chat privado e chamadas privadas, quem pode agendar reuniões e quais tipos de conteúdo podem ser compartilhados. Você também pode usar políticas para ativar os recursos do teams que enriquecem a experiência de aprendizagem.

As políticas devem ser ajustadas para estudantes e professores para manter a experiência de aprendizagem segura. As políticas para alunos precisam ser mais restritivas para reduzir o risco de receber níveis inadequados de acesso. Educadores e funcionários precisam de um conjunto separado de políticas que podem ser mais permissivos para permitir que eles sejam bem-sucedidos. Por exemplo, permita que educadores agendem reuniões e restrinjam os alunos de fazê-lo.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de tela do assistente":::

Este artigo descreve você sobre como executar o assistente.

> [!IMPORTANT]
> As políticas aplicadas pelo assistente atenderão às necessidades da maioria das equipes para clientes educacionais. O assistente ajusta a definição global (da organização em toda a organização) de um conjunto principal de políticas com configurações que recomendamos para a segurança do aluno e a aplica aos alunos. O assistente também cria e atribui um conjunto de políticas personalizadas a educadores e funcionários. A maioria das equipes de clientes educacionais não precisará usar outros métodos de atribuição de política após a execução deste assistente. Use outros métodos de atribuição de política *apenas* se quiser criar e gerenciar manualmente políticas para seus alunos, professores e funcionários.

## <a name="teams-for-education-policy-wizard"></a>Assistente de equipe para a política de educação

<a name="polwiz_intro"> </a>

O assistente aplica um conjunto de definições de política do núcleo para alunos e um conjunto separado de definições de políticas básicas para educadores e funcionários, com configurações adequadas para cada um deles. Veja o que acontece quando você executa o assistente.

O assistente configura políticas com base no tipo de instituição educacional (educação **primária ou secundária** ou **educação superior**). Você seleciona o tipo de instituição e o assistente faz o seguinte:

- **Alunos**: o assistente ajusta a definição da política global (padrão da organização) de cada área de cada política coberta pelo assistente com as novas configurações padrão adequadas para manter seus alunos seguros. Isso garante que seus alunos atuais e todos os novos alunos tenham o conjunto de políticas mais restritivo.
- **Professores e funcionários**: o assistente cria um conjunto de definições de política personalizadas para cada área da política coberta pelo assistente com as configurações adaptadas às necessidades dos educadores e da equipe. Em seguida, ele atribui as definições de política ao grupo de professores e à equipe que você escolher. Dessa forma, seus educadores e funcionários têm um conjunto de políticas permissivo para permitir que eles sejam bem-sucedidos.

Você só precisa executar o assistente uma vez. Novos alunos acessam automaticamente as definições da política global (padrão da organização) aplicadas pelo assistente e novas equipes que você adicionar ao grupo selecionado serão automaticamente atribuídas às políticas personalizadas.

> [!NOTE]
> Consulte [políticas aplicadas pelo assistente](#policies-applied-by-the-wizard) para obter uma lista detalhada de definições de política aplicadas pelo assistente.

Agora, vamos começar!

## <a name="run-the-wizard"></a>Executar o assistente

<a name="polwiz_run"> </a>

Siga estas etapas para executar o assistente. 

1. Se você não tem experiência com o Microsoft Teams, o assistente é iniciado automaticamente. Caso contrário, você pode iniciar o assistente a qualquer momento a partir do painel. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **painel** e, em seguida, na **configuração de política fácil para um ambiente de aprendizagem seguro** , selecione **configuração rápida**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de tela do assistente no painel":::

2. Selecione seu tipo de instituição educacional (educação **primária ou secundária** ou **educação superior**) e, em seguida, clique em **Avançar**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de tela da página no Assistente para selecionar o tipo de instituição":::

3. Procure e selecione um grupo que contenha seus professores e funcionários e clique em **Avançar**. Se você ainda não tiver grupos configurados para seus professores e funcionários, [crie um grupo](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)e execute o assistente novamente. <br/><br/>No momento, você só pode selecionar um grupo. Educadores e funcionários do grupo que você selecionar receberão [um conjunto de políticas personalizadas](#policies-applied-by-the-wizard) adaptado às suas necessidades. Lembre-se de que esse conjunto de políticas é separado das políticas aplicadas aos alunos.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Captura de tela da página no Assistente para selecionar o grupo professor e equipe":::

4. Revise suas seleções.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Captura de tela da página no Assistente para revisar seleções":::

5. Selecione **aplicar** para aplicar as alterações. Isso pode levar alguns minutos para ser concluído.<br/><br/>As definições globais da política (padrão para toda a organização) são aplicadas imediatamente aos alunos. Para seus professores e funcionários, pode levar até 48 horas para que as políticas personalizadas sejam atribuídas a cada membro do grupo selecionado, dependendo do tamanho do grupo. Isso acontece em segundo plano depois que você concluir esta etapa com êxito.
6. Você está de acordo com o seu jeito, mas ainda não está pronto! Há mais alguns pontos a serem considerados. Em seguida, Confira as etapas na seção o [que fazer depois de executar o assistente](#what-to-do-after-running-the-wizard) deste artigo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Captura de tela da página no Assistente para as próximas etapas":::

## <a name="what-to-do-after-running-the-wizard"></a>O que fazer depois de executar o assistente

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Etapa 1: remover atribuições de política existentes que entram em conflito com políticas aplicadas pelo assistente

> [!IMPORTANT]
> **Conclua esta etapa somente se você tiver políticas existentes atribuídas a alunos ou professores e pessoas *antes* de executar o assistente**. Se você é iniciante no Teams e não tem nenhuma política existente além das políticas criadas pelo assistente, pule isso e vá para a etapa 2.

No Teams, para uma determinada área de política, uma política pode ser aplicada a um usuário das seguintes maneiras:

- Atribuição direta ao usuário
- Atribuição a um grupo do qual o usuário é membro
- Se o usuário não estiver diretamente atribuído a uma política ou não for membro de qualquer grupo que tenha sido atribuído a uma política, o usuário automaticamente Obtém a política global (padrão para toda a organização)

Se houver mais de uma dessas atribuições de política para um usuário, o Microsoft Teams usa a seguinte ordem para determinar qual atribuição de política entra em vigor. Para obter mais informações, consulte [qual política tem prioridade?](assign-policies.md#which-policy-takes-precedence) e [regras de precedência](assign-policies.md#precedence-rules).

|Atribuições de política de um usuário|Política que entra em vigor |
|---------|---------|
|Política atribuída ao grupo: não<br/>Política atribuída diretamente a um usuário: não    |Política padrão global (de toda a organização)      |
|Política atribuída ao grupo: não<br/>Política atribuída diretamente a um usuário: Sim    |Política atribuída diretamente ao usuário         |
|Política atribuída ao grupo: Sim<br/>Política atribuída diretamente a um usuário: Sim     |Política atribuída diretamente ao usuário         |
|Política atribuída ao grupo: Sim<br/>Política atribuída diretamente a um usuário: não     |Política atribuída ao grupo<br/><br/>Se o usuário for membro de vários grupos e cada grupo tiver atribuído uma política da mesma área de política, a política que tem a classificação de [atribuição de grupo](assign-policies.md#group-assignment-ranking) mais alta tem efeito.       |

Devido a essa ordem, as políticas criadas pelo assistente não entrarão em vigor se um usuário tiver atribuições diretas ou atribuições de grupo existentes. Isso significa que você terá que remover as atribuições de política existentes do usuário para que a política aplicada pelo assistente entre em vigor.

Para cada [área de política aplicada pelo assistente](#policies-applied-by-the-wizard), faça o seguinte:

- Remova todas as atribuições diretas e atribuições de grupos existentes de seus alunos para que a definição de política global (padrão para toda a organização) aplicada pelo assistente entre em vigor.
- Remova quaisquer tarefas diretas conflitantes dos educadores e da equipe para que a definição de política personalizada criada pelo assistente entre em vigor. Use a tabela acima para determinar os cenários que se aplicam a você. <br/><br/>Lembre-se de que o assistente atribui políticas aos seus professores e grupo de equipe usando uma [classificação de atribuição de grupo](assign-policies.md#group-assignment-ranking) 1, que é a classificação mais alta. Se o grupo educador e equipe tiver uma política existente da mesma área de política atribuída a ele, essa política existente será movida para uma classificação menor e a política atribuída pelo assistente entrará em vigor.

[Saiba mais](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sobre como remover políticas diretamente atribuídas aos usuários.

Por exemplo, você atribuiu uma política de reunião diretamente a educadores e seus alunos têm a política global de reunião (padrão para toda a organização). Nesse cenário, remova a política de reunião à qual você atribuiu diretamente a educadores para que a definição de política personalizada para a política de reunião criada pelo assistente seja efetivada. Você não precisa fazer nada com a política de reunião global existente (padrão para toda a organização) para alunos, pois não há outras políticas de reunião em conflito com ela.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Etapa 2: verificar medidas adicionais que você pode tomar para a segurança do aluno

O assistente ajusta automaticamente e aplica [essas políticas](#policies-applied-by-the-wizard). Há algumas medidas adicionais que você pode tomar com base nas necessidades da sua instituição para ficar seguro.

Veja como [manter os alunos seguros ao usar o Teams for Distance Learning](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) para obter recomendações de segurança adicional.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Etapa 3: verificar atualizações de política no centro de mensagens

Atualmente, o assistente aplica nossas políticas recomendadas quando você a executa. É importante saber que, conforme novas políticas são disponibilizadas no Teams, as configurações globais (padrão para toda a organização) para a segurança do aluno não são adicionadas automaticamente pelo assistente. Esta funcionalidade estará disponível em uma versão futura.

Até que essa funcionalidade esteja disponível, marque a [central de mensagens](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (no centro de administração do Microsoft 365) com frequência para manter-se atualizado sobre novas políticas e configurações de política no Teams. À medida que novos recursos ficarem disponíveis, talvez seja necessário atualizar manualmente suas políticas para manter seu ambiente de aprendizagem seguro.

## <a name="make-changes-in-the-wizard"></a>Fazer alterações no assistente

<a name="polwiz_change"> </a>

Se precisar fazer alterações depois de executar o assistente, você poderá executá-lo novamente e alterar suas seleções.

1. No painel de navegação esquerdo do centro de administração do Microsoft Teams, vá até **painel** e, em seguida, na **configuração de política fácil para um bloco de ambiente de aprendizagem seguro** , selecione **alterar**.
2. Aqui, continue em cada página do assistente para fazer as alterações. Você pode alterar o tipo de instituição, o grupo de educadores e a equipe à qual deseja atribuir políticas ou ambos.

A tabela a seguir resume o que acontece quando você faz uma alteração no assistente.

|Tipo de alteração  |Comportamento da política  |
|---------|---------|
|Alterar o tipo de instituição educacional e os professores e o grupo de equipe    |<ul><li>**Alunos**: as definições globais da política (padrão para toda a organização) baseadas no novo tipo de instituição educacional são aplicadas aos alunos.</li><li>**Professores e funcionários**: um conjunto de definições de política personalizadas com base no novo tipo de instituição educacional é criado e atribuído ao novo grupo professor e equipe. As definições de política personalizadas anteriores são removidas do grupo educador e da equipe anteriores.</li></ul>    |
|Alterar apenas o tipo de instituição educacional    |<ul><li>**Alunos**: as definições globais da política (padrão para toda a organização) baseadas no novo tipo de instituição educacional são aplicadas aos alunos.</li><li>**Educadores e funcionários**: um conjunto de definições de política personalizadas com base no novo tipo de instituição educacional é criado e atribuído ao grupo educador e equipe. As definições de política personalizadas criadas para o tipo de instituição educacional anterior são removidas do grupo educador e equipe.</li></ul>         |
|Alterar apenas o grupo educador e equipe   |<ul><li>**Alunos**: nenhuma alteração nas definições da política global (padrão para toda a organização) aplicada a alunos.</li><li>**Educadores e funcionários**: as definições de política personalizadas são atribuídas ao novo grupo educador e à equipe e removidas do grupo educador e da equipe anterior.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Políticas aplicadas pelo assistente

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Áreas de política

Aqui estão as áreas de política e os nomes de política correspondentes incluídos no assistente. Para encontrar essas políticas, vá para o centro de administração do Microsoft Teams e, em seguida, no painel de navegação esquerdo, vá para cada página da área de política.

#### <a name="students"></a>[**Alunos**](#tab/students/)

|Área da política  |Nome da política primária ou secundária |Nome da política de educação mais alta  |
|---------|---------|---------|
|Políticas do Teams    |Global (padrão para toda a organização)         |Global (padrão para toda a organização)           |
|Políticas de reunião    |Global (padrão para toda a organização)           |Global (padrão para toda a organização)           |
|Políticas de eventos ao vivo     |Global (padrão para toda a organização)          |  Global (padrão para toda a organização)          |
|Política de configuração do aplicativo     |Global (padrão para toda a organização)           |Global (padrão para toda a organização)           |
|Política de permissão do aplicativo    |Global (padrão para toda a organização)           |Global (padrão para toda a organização)           |
|Políticas de mensagens     |Global (padrão para toda a organização)           |Global (padrão para toda a organização)           |
|Políticas de chamada    |Global (padrão para toda a organização)           |Global (padrão para toda a organização)           |

#### <a name="educators-and-staff"></a>[**Educadores e funcionários**](#tab/educators/)

|Área da política  |Nome da política primária ou secundária |Nome da política de educação mais alta |
|---------|---------|---------|
|Políticas do Teams   |Educadores primários ou secundários e pessoal-equipes         |Educadores e funcionários de ensino mais altos-equipes         |
|Políticas de reunião    |Educadores primários ou secundários e funcionários-reunião         |Educadores e funcionários de ensino mais altos – reunião         |
|Políticas de eventos ao vivo   | Educadores primários ou secundários e eventos ao vivo da equipe         |Educadores de ensino mais altos e eventos ao vivo         |
|Políticas de mensagens    |Educadores primários ou secundários e pessoal-mensagens         | Educadores e funcionários de ensino mais altos-mensagens         |
|Políticas de chamada    |Educadores primários ou secundários e chamadas para a equipe         |Educadores de ensino mais altos e chamadas de equipe         |

* * *

### <a name="policy-settings"></a>Configurações de política

Aqui está um resumo das configurações aplicadas pelo Assistente para cada área de política.

#### <a name="students"></a>[**Alunos**](#tab/student-settings/)

Aqui está uma lista das definições de política global (padrão para toda a organização) ajustadas pelo assistente e aplicadas aos alunos.

|Área da política |Subárea  |Configuração de política  |Primário ou secundário |Ensino mais alto |
|---------|---------|---------|---------|---------|
|Políticas do Teams   |         |Criar canais privados         |Desativado       |Ativado|
|Política de reuniões    |Geral         |Permitir reunir agora em canais         |Desativado      |Ativado|
|  |        |Permitir o suplemento do Outlook         |Desativado       |Ativado|
|  |        |Permitir agendamento de reunião de canal        |Desativado      |Ativado|
|  |        |Permitir agendamento de reuniões particulares       |Desativado      |Ativado|
|  |Áudio & vídeo        |Permitir transcrição        |Ativado       |Ativado|
|  |        |Permitir gravação na nuvem         |Desativado      |Ativado|
|  |        |Modo para áudio IP       |Áudio de saída e entrada habilitado        |Áudio de saída e entrada habilitado|
|  |        |Modo para vídeo de IP         |Vídeo de saída e de entrada habilitado     |Vídeo de saída e de entrada habilitado|
|  |       |Permitir vídeo IP         |Ativado         |Ativado|
|  |       |Permitir streaming NDI         |Desativado         |Desativado|
|  |       |Taxa de bits de mídia (KBS)         |50.000         |50.000|
|  |Compartilhamento de conteúdo       |Modo de compartilhamento de tela         |Tela inteira         |Tela inteira|
|  |       |Permitir que um participante conceda ou solicite o controle         |Ativado         |Ativado|
|  |       |Permitir que um participante externo conceda ou solicite controle         |Ativado         |Ativado|
|  |       |Permitir compartilhamento do PowerPoint        |Ativado         |Ativado|
|  |       |Permitir quadro de comunicações         |Ativado         |Ativado|
|  |       |Permitir anotações compartilhadas         |Ativado        |Ativado|
|  |Participantes & convidados       |Permitir que as pessoas anônimas iniciem uma reunião       |Desativado         |Ativado|
|  |       |Funções que têm direitos de apresentador em reuniões        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Admitir pessoas automaticamente        |EveryoneInCompany|EveryoneInCompany|
|  |       |Permitir que os usuários de discagem ignorem o lobby        |Desativado         |Desativado|
|  |       |Permitir reunião agora em reuniões privadas        |Desativado         |Ativado|
|  |       |Habilitar legendas dinâmicas       |Desabilitado, mas o usuário pode substituir         |Desabilitado, mas o usuário pode substituir|
|  |       |Permitir chat em reuniões         |Ativado         |Ativado|
|  |Modo de filtros de vídeo       |VideoFiltersMode         |BlurandDefaultBackgrounds|Filtros|
|  |Relatório de presença de reunião       |AllowEngagementReport         |Desativado         |Ativado|
|Políticas de eventos ao vivo  |       |Permitir agendamento         |Desativado         |Desativado|
|  |       |Permitir transcrição para participantes          |Ativado       |Ativado|
|  |       |Quem pode ingressar eventos ao vivo agendados        |Todos na organização        |Todos na organização|
|  |       |Quem pode gravar um evento         |Ativa         |Ativa|
|Políticas de mensagens  |       |Os proprietários podem excluir as mensagens enviadas         |Desativado|Ativado|
|  |       |Excluir mensagens enviadas         |Desativado         |Ativado|
|  |       |Editar mensagens enviadas         |Desativado         |Ativado|
|  |       |Confirmações de leitura         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |Chat         |Desativado         |Ativado|
|  |       |Usar o Giphys em conversas         |Desativado         |Ativado|
|  |       |Classificação de conteúdo Giphy         |Estrito        |Estrito|
|  |       |Usar o memes em conversas         |Ativado         |Ativado|
|  |       |Usar adesivos nas conversas         |Ativado         |Ativado|
|  |       |Permitir visualizações de URL        |Ativado         |Ativado|
|  |       |Traduzir mensagens         |Ativado         |Ativado|
|  |       |Permitir leitura avançada para exibição de mensagens        |Ativado      |Ativado|
|  |       |Enviar mensagens urgentes usando as notificações de prioridade  |Desativado         |Ativado|
|  |       |Criar mensagens de voz         |Permitido em chats e canais         |Permitido em chats e canais|
|  |       |Em dispositivos móveis, exiba os canais favoritos acima dos chats recentes     |Habilitado         |Habilitado|
|  |       |Remover usuários de chats em grupo         |Desativado         |Ativado|
|  |       |Respostas sugeridas         |Ativado         |Ativado|
|Política de permissão do aplicativo  |       |Aplicativos da Microsoft         |Bloquear aplicativos específicos e permitir que todos os outros > faça a conversa bloqueada         |Permitir todos os aplicativos|
|  |       |Aplicativos de terceiros         |Permitir todos os aplicativos         |Permitir todos os aplicativos|
|  |       |Aplicativos personalizados         |Permitir todos os aplicativos         |Permitir todos os aplicativos|
|Política de configuração do aplicativo  |           |Carregar aplicativos personalizados           |Desativado         |Desativado|
|  |       |Permitir fixação do usuário |Ativado         |Ativado|
|  |       |Aplicativos instalados         |Nenhum         |Nenhum|
|  |       |Aplicativos fixos         |Atividade, calendário, equipes         |Atividade, chats, equipes, calendário, chamadas, arquivo
|Políticas de chamada  |       |Fazer chamadas privadas         |Desativado        |Ativado|
|  |       |Encaminhamento de chamadas e toque simultâneo para as pessoas em sua organização         |Desativado         |Ativado|
|  |       |Encaminhamento de chamadas e toque simultâneo para números de telefone externos         |Desativado         |Ativado|
|  |       |O correio de voz está disponível para fazer roteamento de chamadas de entrada         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |As chamadas recebidas podem ser roteadas para grupos de chamadas         |Desativado        |Ativado|
|  |       |Permitir Delegação para chamadas de entrada e de saída         |Desativado         |Ativado|
|  |       |Impedir que a chamada seja ignorada e enviar chamadas por meio da PSTN        |Desativado         |Desativado|
|  |       |Ocupado em ocupado está disponível durante uma chamada         |Desativado         |Desativado|
|  |       |Permitir chamada PSTN na Web         |Desativado         |Ativado|

#### <a name="educators-and-staff"></a>[**Educadores e funcionários**](#tab/educator-settings/)

Aqui está uma lista das definições de política personalizadas atribuídas aos professores e ao grupo de equipe que você escolhe no assistente.  

|Área da política |Subárea  |Configuração de política  |Primário ou secundário |Ensino mais alto |
|---------|---------|---------|---------|---------|
|Políticas do Teams   |         |Criar canais privados         |Ativado       |Ativado|
|Política de reuniões    |Geral         |Permitir reunir agora em canais         |Ativado      |Ativado|
|  |        |Permitir o suplemento do Outlook         |Ativado       |Ativado|
|  |        |Permitir agendamento de reunião de canal        |Ativado      |Ativado|
|  |        |Permitir agendamento de reuniões particulares       |Ativado      |Ativado|
|  |Áudio & vídeo        |Permitir transcrição        |Ativado       |Ativado|
|  |        |Permitir gravação na nuvem         |Ativado      |Ativado|
|  |        |Modo para áudio IP       |Áudio de saída e entrada habilitado        |Áudio de saída e entrada habilitado|
|  |        |Modo para vídeo de IP         |Vídeo de saída e de entrada habilitado     |Vídeo de saída e de entrada habilitado|
|  |       |Permitir vídeo IP         |Ativado         |Ativado|
|  |       |Permitir streaming NDI         |Desativado         |Desativado|
|  |       |Taxa de bits de mídia (KBS)         |50.000         |50.000|
|  |Compartilhamento de conteúdo       |Modo de compartilhamento de tela         |Tela inteira         |Tela inteira|
|  |       |Permitir que um participante conceda ou solicite o controle         |Ativado         |Ativado|
|  |       |Permitir que um participante externo conceda ou solicite controle         |Ativado         |Ativado|
|  |       |Permitir compartilhamento do PowerPoint        |Ativado         |Ativado|
|  |       |Permitir quadro de comunicações         |Ativado         |Ativado|
|  |       |Permitir anotações compartilhadas         |Ativado        |Ativado|
|  |Participantes & convidados       |Permitir que as pessoas anônimas iniciem uma reunião       |Ativado        |Ativado|
|  |       |Funções que têm direitos de apresentador em reuniões        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Admitir pessoas automaticamente        |Organizadorsó|Organizadorsó|
|  |       |Permitir que os usuários de discagem ignorem o lobby        |Desativado         |Desativado|
|  |       |Permitir reunião agora em reuniões privadas        |Ativado         |Ativado|
|  |       |Habilitar legendas dinâmicas       |Desabilitado, mas o usuário pode substituir         |Desabilitado, mas o usuário pode substituir|
|  |       |Permitir chat em reuniões         |Ativado         |Ativado|
|  |Modo de filtros de vídeo       |VideoFiltersMode         |Filtros|Filtros|
|  |Relatório de presença de reunião       |AllowEngagementReport         |Ativado         |Ativado|
|Políticas de eventos ao vivo  |       |Permitir agendamento         |Ativado         |Ativado|
|  |       |Permitir transcrição para participantes          |Ativado       |Ativado|
|  |       |Quem pode ingressar eventos ao vivo agendados        |Todos na organização        |Todos na organização|
|  |       |Quem pode gravar um evento         |Sempre gravar         |Sempre gravar|
|Políticas de mensagens  |       |Os proprietários podem excluir as mensagens enviadas         |Ativado|Ativado|
|  |       |Excluir mensagens enviadas         |Ativado         |Ativado|
|  |       |Editar mensagens enviadas         |Ativado         |Ativado|
|  |       |Confirmações de leitura         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |Chat         |Ativado         |Ativado
|  |       |Usar o Giphys em conversas         |Ativado        |Ativado|
|  |       |Classificação de conteúdo Giphy         |Estrito        |Estrito|
|  |       |Usar o memes em conversas         |Ativado         |Ativado|
|  |       |Usar adesivos nas conversas         |Ativado         |Ativado|
|  |       |Permitir visualizações de URL        |Ativado         |Ativado|
|  |       |Traduzir mensagens         |Ativado         |Ativado|
|  |       |Permitir leitura avançada para exibição de mensagens        |Ativado      |Ativado|
|  |       |Enviar mensagens urgentes usando as notificações de prioridade  |Ativado         |Ativado|
|  |       |Criar mensagens de voz         |Permitido em chats e canais         |Permitido em chats e canais|
|  |       |Em dispositivos móveis, exiba os canais favoritos acima dos chats recentes     |Habilitado         |Habilitado|
|  |       |Remover usuários de chats em grupo         |Ativado        |Ativado|
|  |       |Respostas sugeridas         |Ativado         |Ativado|
|Políticas de chamada  |       |Fazer chamadas privadas         |Ativado       |Ativado|
|  |       |Encaminhamento de chamadas e toque simultâneo para as pessoas em sua organização         |Ativado        |Ativado|
|  |       |Encaminhamento de chamadas e toque simultâneo para números de telefone externos         |Ativado        |Ativado|
|  |       |O correio de voz está disponível para fazer roteamento de chamadas de entrada         |Controlado pelo usuário         |Controlado pelo usuário|
|  |       |As chamadas recebidas podem ser roteadas para grupos de chamadas         |Ativado        |Ativado|
|  |       |Permitir Delegação para chamadas de entrada e de saída         |Ativado         |Ativado|
|  |       |Impedir que a chamada seja ignorada e enviar chamadas por meio da PSTN        |Desativado         |Desativado|
|  |       |Ocupado em ocupado está disponível durante uma chamada         |Desativado         |Desativado|
|  |       |Permitir chamada PSTN na Web         |Ativado      |Ativado|

* * *

## <a name="related-topics"></a>Tópicos relacionados

- [Políticas de equipe e pacotes de política para educação](policy-packages-edu.md)
- [Atribuir políticas a grandes conjuntos de usuários na sua escola](batch-group-policy-assignment-edu.md)
- [Mantendo os alunos seguros ao usar o Microsoft Teams para aprendizado à distância](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
