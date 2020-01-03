---
title: Canais privados no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar canais privados no Microsoft Teams.
ms.openlocfilehash: 942070f9c77fb16895dd15e1920198f3604150f9
ms.sourcegitcommit: 9c743b267b46a475a7da51c0899467960421ad8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/02/2020
ms.locfileid: "40929557"
---
# <a name="private-channels-in-microsoft-teams"></a>Canais privados no Microsoft Teams

Os canais privados do Microsoft Teams criam espaços prioritários para colaboração em suas equipes. Somente os usuários da equipe que são proprietários ou membros do canal privado podem acessar o canal. Qualquer pessoa, incluindo convidados, pode ser adicionada como membro de um canal privado, desde que eles já sejam membros da equipe.

Você pode querer usar um canal privado se quiser limitar a colaboração para aqueles que precisam saber ou se você deseja facilitar a comunicação entre um grupo de pessoas atribuídas a um projeto específico, sem precisar criar uma equipe adicional para gerenciar.

Por exemplo, um canal privado é útil nestes cenários:

- Um grupo de pessoas em uma equipe precisa de um espaço prioritário para colaborar sem ter que criar uma equipe separada.
- Um subconjunto de pessoas em uma equipe precisa de um canal privado para discutir informações confidenciais, como orçamentos, insourcing, posicionamento estratégico e assim por diante.

Um ícone de cadeado indica um canal privado. Somente membros de canais particulares podem ver e participar de canais privados aos quais são adicionados.

![Captura de tela de canais privados em uma equipe](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>O que você precisa saber sobre canais particulares

Atualmente, os canais privados dão suporte a conectores e guias (exceto Stream, Planner e Forms). Estamos trabalhando com o suporte total a aplicativos para canais privados, incluindo extensões de mensagens e bots.

Cada equipe pode ter no máximo 30 canais privados e cada canal privado pode ter no máximo 250 Membros. O limite do canal privado de 30 é além do limite de canal padrão do 200 por equipe.

> [!NOTE]
> Estamos constantemente adicionando recursos a canais privados, portanto, volte para as informações mais atualizadas sobre aplicativos, reuniões de canal e dimensionamento de canais privados para grandes equipes.

## <a name="when-to-create-a-private-channel"></a>Quando criar um canal privado

Para determinar se um canal privado é adequado, considere as seguintes perguntas sobre quem precisa trabalhar em conjunto e o que é a colaboração.

|Já existe uma equipe com essas pessoas como membros da equipe?  |Este trabalho precisa ser mantido particular de outras pessoas?  |Há vários tópicos distintos a serem discutidos?  |Recomendação  |
|---------|---------|---------|---------|
|Sim      |Sim          |Sim         |Crie um canal privado na equipe existente ou considere a criação de canais particulares dedicados para cada tópico.         |
|Sim     |Sim         |Não         |Criar um canal privado na equipe existente.         |
|Sim     |Não         |Não         |Crie um canal na equipe existente.         |
|Não     |Não         |Não         |Considere a criação de uma nova equipe.         |
|Não     |Não         |Sim         |Considere a criação de uma nova equipe e, em seguida, dependendo da confidencialidade de cada tópico, considere a criação de canais padrão separados ou privados para cada tópico.         |
|Não     |Sim         |Não         |Crie uma nova equipe ou crie um novo canal privado em uma equipe existente.         |

Quando um canal privado é criado, ele é vinculado à equipe pai e não pode ser movido para uma equipe diferente. Além disso, os canais privados não podem ser convertidos em canais padrão e vice-versa.

## <a name="private-channel-creation-and-membership"></a>Criação e Associação de canal privado

### <a name="who-can-create-private-channels"></a>Quem pode criar canais privados?

Por padrão, qualquer proprietário da equipe ou membro da equipe pode criar um canal privado. Os convidados não podem criá-los. A capacidade de criar canais privados pode ser gerenciada no nível da equipe e no nível da organização:

- Na guia **configurações** de uma equipe, os proprietários da equipe podem desativar ou ativar a capacidade de os Membros criarem canais privados.
- Como administrador, você pode usar [políticas](teams-policies.md) para controlar quais usuários da sua organização podem criar canais privados.

A pessoa que cria um canal privado é o proprietário do canal privado e somente o proprietário do canal privado pode adicionar ou remover pessoas diretamente dela. Um proprietário de canal privado pode adicionar qualquer membro da equipe a um canal privado que ele criou, incluindo convidados. Os membros de um canal privado têm um espaço de conversa seguro e, quando novos membros são adicionados, eles podem ver todas as conversas (mesmo conversas antigas) nesse canal privado.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>O que acontece quando um membro da equipe sai ou é removido de uma equipe?

Se um membro da equipe sair ou for removido de uma equipe, esse usuário também deixará ou será removido de todos os canais particulares da equipe. Se o usuário for adicionado novamente à equipe, ele deverá ser adicionado novamente aos canais privados da equipe.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>O que acontece quando um proprietário de canal privado é removido de um canal privado?

Um proprietário de canal privado não pode ser removido por meio do cliente do Teams, se for o último proprietário de um ou mais canais particulares.

Se um proprietário de canal privado deixar sua organização ou se for removido do grupo do Office 365 associado à equipe, um membro do canal privado será automaticamente promovido para ser o proprietário do canal privado.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>O que os proprietários da equipe e os membros da equipe podem ver em um canal privado?

Os proprietários da equipe podem ver os nomes de todos os canais privados na equipe e também podem excluir qualquer canal privado da equipe. (Um canal privado excluído pode ser restaurado dentro de 30 dias depois que ele é excluído). Os proprietários da equipe não podem ver os arquivos em um canal privado ou na lista de conversas e membros de um canal privado, a menos que eles sejam membros desse canal privado.

A tabela a seguir mostra quem pode ver o que em um canal privado.

|Item  |O proprietário da equipe pode ver |Os membros da equipe podem ver |
|---------|---------|---------|
|Nome e descrição    |Todos os canais privados na equipe         |Somente os canais particulares aos quais são adicionados         |
|Conversas e guias     |Somente quando adicionado ao canal privado         |Somente quando adicionado ao canal privado         |
|Arquivos e conteúdo    |Somente quando adicionado ao canal privado        |Somente quando adicionado ao canal privado         |
|Proprietário do canal privado    |Todos os canais privados na equipe        |Somente quando adicionado ao canal privado         |
|Carimbo de data/hora da última atividade  |Todos os canais privados na equipe       |Somente quando adicionado ao canal privado         |

## <a name="manage-private-channels"></a>Gerenciar canais privados

A tabela a seguir descreve quais ações os proprietários, membros e convidados podem fazer em canais privados.

|Ação  |Proprietário da equipe|Membro da equipe|Convidado da equipe|Proprietário do canal privado|Membro do canal privado|Convidado de canal privado|
|---------|---------|---------|---------|---------|---------|---------|
|Criar canal privado|Sim<sup>1</sup>|Sim<sup>1, 2</sup>|Não|N/D|N/D|N/D|
|Excluir canal privado|Sim|Não|Não|Sim|Não|Não|
|Sair do canal privado|N/D|N/D|N/D|Sim<sup>3</sup>|Sim|Sim |
|Editar canal privado|Não|N/D|N/D|Sim|Não|Não|
|Restaurar o canal privado excluído|Sim|Não|Não|Sim|Não|Não|
|Adicionar membros|Não|N/D|N/D|Sim|Não|Não|
|Editar configurações|Não|N/D|N/D|Sim|Não|Não|
|Gerenciar guias e aplicativos|Não|N/D|N/D|Sim<sup>4</sup>|Sim<sup>5</sup>|Não|

<sup>1</sup> pressupondo que a política que você, o administrador configurou permite que o usuário crie canais privados.<br>
<sup>2</sup> cada equipe tem uma configuração que os proprietários da equipe podem ativar ou desativar para permitir que os membros da equipe criem canais privados. Os proprietários da equipe sempre podem criar canais privados.<br>
<sup>3</sup> pressupondo que o proprietário do canal privado não seja o último proprietário do canal. <br>
<sup>4</sup> exige que a equipe tenha um aplicativo instalado para que um canal privado o use.<br>
<sup>5</sup> os proprietários de canal privado podem configurar isso.

### <a name="manage-private-channel-membership-and-settings"></a>Gerenciar associações e configurações de canal privado

Cada canal privado tem suas próprias configurações, incluindo a capacidade de adicionar e remover membros, adicionar guias e @mentioning para todo o canal. Essas configurações são independentes das configurações da equipe pai. Quando um canal privado é criado, ele herda as configurações da equipe pai, após a qual suas configurações podem ser alteradas independentemente das configurações da equipe pai.

O proprietário do canal privado pode clicar em **gerenciar canal**e, em seguida, usar as guias **Membros** e **configurações** para adicionar ou remover membros e editar configurações.  

![Captura de tela das configurações do canal privado](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Gerenciar o ciclo de vida de canais privados

Consulte [gerenciar o ciclo de vida de canais privados no Teams](private-channels-life-cycle-management.md) para obter orientação sobre como gerenciar o ciclo de vida de canais privados em sua organização. Isso inclui como controlar se os usuários em sua organização podem criar canais privados, como criar um canal privado em nome de um proprietário de equipe, como obter uma lista de todas as mensagens de canal privado para fins de arquivamento e auditoria e outras tarefas de gerenciamento.  

## <a name="private-channel-sharepoint-sites"></a>Sites do SharePoint de canal privado

Cada canal privado tem seu próprio conjunto de sites do SharePoint otimizado para compartilhamento de arquivos e provisionamento rápido. O conjunto de sites separado serve para garantir que o acesso a arquivos de canais privados seja restrito somente a membros do canal privado, em comparação com o site de equipe, onde os proprietários da equipe têm acesso a todos os ativos dentro do conjunto de sites. Esses conjuntos de sites são criados com uma biblioteca de documentos por padrão e podem ser facilmente aprimorados para um conjunto de sites com recursos completos por meio da [interface de gerenciamento de sites](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Cada conjunto de sites é criado na mesma região geográfica que o conjunto de sites da equipe pai. Estes sites leves têm uma ID de modelo Personalizada, "TEAMCHANNEL # 0", para facilitar o gerenciamento por meio do PowerShell e da API do Graph.  Por design, eles não ficam visíveis no centro de administração do SharePoint.

Para acomodar um número maior de conjuntos de sites por locatário, o limite aumentou de 500.000 para 2 milhões. Um conjunto de sites de canal privado sincroniza a classificação de dados e herda as permissões de acesso de convidado do conjunto de sites da equipe pai.  A associação ao proprietário do conjunto de sites e aos grupos de membros são mantidas em sincronia com a associação do canal privado no Microsoft Teams. Todas as alterações na associação de grupos de proprietários ou membros no SharePoint Online serão revertidas para a associação de canal privado em quatro horas automaticamente. Em cenários em que certos usuários precisam acessar documentos sem precisar acessar mensagens de canal privado, adicione-os ao grupo visitantes do site ou a um novo grupo separado de proprietários e membros.

O Teams gerencia o ciclo de vida do conjunto de sites do SharePoint do canal privado. Se o conjunto de sites for excluído fora do Teams, um trabalho em segundo plano restaura o site dentro de quatro horas, desde que o canal privado ainda esteja ativo. Se o site for excluído e excluído com o disco rígido, um novo conjunto de sites será provisionado para o canal privado.

Se um canal privado ou uma equipe que contém um canal privado for restaurado, os conjuntos de sites serão restaurados. Se um conjunto de sites de canal privado for restaurado e estiver além da janela de exclusão de software de 30 dias do canal privado, o conjunto de sites funcionará como um conjunto de sites autônomo.

## <a name="private-channel-message-compliance-records"></a>Registros de conformidade de mensagens de canal privado

Os registros de mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo. Os títulos dos registros são formatados para indicar o canal privado do qual foram enviados.

Para obter mais informações sobre como executar uma pesquisa de descoberta eletrônica para mensagens de canal privado, consulte [descoberta eletrônica de canais privados](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Considerações sobre o acesso em canais privados

Quando um novo bloco de anotações do OneNote é criado em um canal privado, usuários adicionais ainda podem obter acesso ao bloco de anotações porque o comportamento é o mesmo que compartilhar o acesso a qualquer outro item em um site do SharePoint de canal privado com um usuário.

Se um usuário tiver acesso a um bloco de anotações em um canal privado pelo SharePoint, remover o usuário da equipe ou canal privado não removerá o acesso do usuário ao bloco de anotações.

Se um bloco de anotações existente for adicionado como uma guia a um canal privado, o acesso ao canal privado não será alterado. Isso significa o seguinte:

- Nem todo mundo no canal privado terá acesso ao bloco de anotações por padrão. Isso ocorre porque eles podem não ter acesso ao local em que o bloco de anotações está hospedado, como outro site de equipe do SharePoint.
- Os usuários que não são membros do canal privado podem ver o bloco de anotações.  

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral de equipes e canais no Teams](teams-channels-overview.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar a API do Microsoft Graph para trabalhar com o Microsoft Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
