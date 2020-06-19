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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar e gerenciar canais privados no Microsoft Teams.
ms.openlocfilehash: 54fd36bd78f1d9ea263fe3e79a3d12a08741c389
ms.sourcegitcommit: 8acc2ed4cb807f941a6526ec8aad562536f45aa6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44804685"
---
# <a name="private-channels-in-microsoft-teams"></a>Canais privados no Microsoft Teams

Os canais privados do Microsoft Teams criam espaços reservado para colaboração com suas equipes. O acesso é restrito aos usuários da equipe que forem proprietários ou membros do canal privado. É possível adicionar qualquer pessoa, inclusive convidados, como membro de um canal privado, desde que já sejam membros da equipe.

Você pode usar o canal privado para limitar a colaboração àqueles que precisam de conhecimento ou se quiser facilitar a comunicação entre um grupo de pessoas atribuídas para um projeto específico, sem ter que criar uma equipe adicional para gerenciar.

Por exemplo, um canal privado é útil nestes cenários:

- Um grupo de pessoas em uma equipe deseja um espaço reservado para colaborar sem precisar criar uma equipe separada.
- Um subconjunto de pessoas em uma equipe deseja um canal privado para discutir informações confidenciais, como orçamentos, recursos, posicionamento estratégico e assim por diante.

Um ícone de cadeado indica um canal privado. Somente membros de canais privados podem ver e participar de canais privados aos quais foram adicionados.

![Captura de tela de canais privados em uma equipe](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>O que você precisa saber sobre canais privados

Atualmente, os canais privados oferecem suporte a conectores e guias (exceto Stream, Planner e Forms). Estamos trabalhando no suporte total de aplicativos para canais privados, incluindo extensões de mensagens e bots.

Cada equipe pode ter no máximo 30 canais privados e cada canal privado pode ter no máximo 250 membros. O limite de 30 canais privados é um acréscimo ao limite de 200 canais padrão por equipe. 

Quando você cria uma equipe a partir de uma equipe existente, qualquer canal privado na equipe existente não será copiado.


> [!NOTE]
> Estamos continuamente adicionando recursos aos canais privados, portanto, verifique as informações mais atualizadas sobre aplicativos, reuniões de canal e dimensionamento de canais privados para grandes equipes.

## <a name="when-to-create-a-private-channel"></a>Quando criar um canal privado

Para determinar se um canal privado é apropriado, considere as seguintes perguntas sobre quem precisa trabalhar em conjunto e sobre o que é a colaboração.

|Já existe uma equipe que tem essas pessoas como membros da equipe?  |Esse trabalho precisa ser mantido privado de outras pessoas?  |Há vários tópicos diferentes para discutir?  |Recomendação  |
|---------|---------|---------|---------|
|Sim      |Sim         |Sim         |Crie um canal privado na equipe existente ou considere criar canais privados dedicados para cada tópico.         |
|Sim     |Sim         |Não         |Crie um canal privado na equipe existente.         |
|Sim     |Não         |Não         |Crie um canal na equipe existente.         |
|Não     |Não         |Não         |Considere a criação de uma nova equipe.         |
|Não     |Não         |Sim         |Considere a criação de uma nova equipe e, dependendo da confidencialidade de cada tópico, considere a criação de canais padrão ou privados separados para cada tópico.         |
|Não     |Sim         |Não         |Crie uma nova equipe e considere a criação de um canal privado.         |

Quando um canal privado é criado, ele é vinculado à equipe pai e não pode ser movido para uma equipe diferente. Além disso, os canais privados não podem ser convertidos em canais padrão e vice-versa.

## <a name="private-channel-creation-and-membership"></a>Criação e associação de canal privado

### <a name="who-can-create-private-channels"></a>Quem pode criar canais privados?

Por padrão, qualquer proprietário ou membro de equipe pode criar um canal privado. Os convidados não podem criá-los. A capacidade de criar canais privados pode ser gerenciada no nível da equipe e no nível da organização.

 1. Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

 2. Use [políticas](teams-policies.md) para controlar quais usuários da sua organização podem criar canais privados.
    Depois de definir as políticas, os proprietários da equipe poderão desativar ou ativar a capacidade dos membros de criar canais privados na guia **configurações** de uma equipe.

A pessoa que cria um canal privado é o proprietário de canal privado e somente o proprietário de canal privado pode adicionar ou remover diretamente as pessoas dele. O proprietário de um canal privado pode adicionar qualquer membro da equipe a um canal privado criado, incluindo convidados. Os membros de um canal privado têm um espaço seguro para conversas e, quando novos membros são adicionados, eles podem ver todas as conversas (mesmo conversas antigas) nesse canal privado.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>O que acontece quando um membro da equipe sai ou é removido de uma equipe?

Se um membro da equipe sair ou for removido de uma equipe, esse usuário também deixará ou será removido de todos os canais privados da equipe. Se o usuário for adicionado novamente à equipe, eles devem ser adicionados novamente aos canais privados da equipe.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>O que acontece quando o proprietário de um canal privado é removido de um canal privado?

O proprietário de um canal privado não pode ser removido pelo cliente do Teams se ele for o último proprietário de um ou mais canais privados.

Se um proprietário de canal privado deixar sua organização ou se for removido do grupo do Microsoft 365 associado à equipe, um membro do canal privado será automaticamente promovido para ser o proprietário do canal privado.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>O que os proprietários e membros de equipe podem ver em um canal privado?

Os proprietários de equipe podem ver os nomes de todos os canais privados da equipe e também podem excluir qualquer canal privado da equipe. (Um canal privado excluído pode ser restaurado dentro de 30 dias após a exclusão). Os proprietários de equipe não podem ver os arquivos em um canal privado ou as conversas e a lista de membros de um canal privado, a menos que sejam membros desse canal privado.

A tabela a seguir mostra quem pode ver o que em um canal privado.

|Item  |O proprietário de equipe pode ver |Os membros da equipe podem ver |
|---------|---------|---------|
|Nome e descrição    |Todos os canais privados da equipe         |Somente os canais privados aos quais eles foram adicionados         |
|Conversas e guias     |Somente quando adicionado ao canal privado         |Somente quando adicionado ao canal privado         |
|Arquivos e conteúdo    |Somente quando adicionado ao canal privado        |Somente quando adicionado ao canal privado         |
|Proprietário do canal privado    |Todos os canais privados da equipe        |Somente quando adicionado ao canal privado         |
|Carimbo de data/hora da última atividade  |Todos os canais privados da equipe       |Somente quando adicionado ao canal privado         |

## <a name="manage-private-channels"></a>Gerenciar canais privados

A tabela a seguir descreve quais ações os proprietários, membros e convidados podem fazer em canais privados.

|Ação  |Proprietário de equipe|Membro da equipe|Convidado da equipe|Proprietário do canal privado|Membro do canal privado|Convidado do canal privado|
|---------|---------|---------|---------|---------|---------|---------|
|Criar um canal privado|Sim<sup>1</sup>|Yes<sup>1,2</sup>|Não|N/D|N/A|N/A|
|Excluir canal privado|Sim|Não|Não|Sim|Não|Não|
|Sair do canal privado|Não disponível|N/A|Não disponível|Sim<sup>3</sup>|Sim|Sim|
|Editar canal privado|Não|N/D|Não disponível|Sim|Não|Não|
|Restaurar canal privado excluído|Sim|Não|Não|Sim|Não|Não|
|Adicionar membros|Não|N/D|Não disponível|Sim|Não|Não|
|Editar configurações|Não|N/D|Não disponível|Sim|Não|Não|
|Gerenciar guias e aplicativos|Não|N/D|Não disponível|Sim<sup>4</sup>|Sim<sup>5</sup>|Não|

<sup>1</sup> Supondo que a política que você, o administrador, configurou, permite ao usuário criar canais privados.<br>
<sup>2</sup> Cada equipe tem uma configuração que os proprietários de equipe podem ativar ou desativar para permitir que os membros da equipe criem canais privados. Os proprietários de equipe sempre podem criar canais privados.<br>
<sup>3</sup> Supondo que o proprietário de canal privado não é o último proprietário do canal. <br>
<sup>4</sup> Requer que a equipe tenha um aplicativo instalado para um canal privado usá-lo.<br>
<sup>5</sup> Os proprietários de canal privado podem configurar isso.

### <a name="manage-private-channel-membership-and-settings"></a>Gerenciar configurações e associação a canal privado

Cada canal privado tem suas próprias configurações, incluindo a capacidade de adicionar e remover membros, adicionar guias e @mencionar em todo o canal. Essas configurações são independentes das configurações da equipe pai. Quando um canal privado é criado, ele herda as configurações da equipe pai, cujas configurações podem ser alteradas depois independentemente das configurações da equipe pai.

O proprietário do canal privado pode clicar em **Gerenciar canal** e, em seguida, usar as guias **Membros** e **Configurações** para adicionar ou remover membros e editar configurações.  

![Captura de tela das configurações de canal privado](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Gerenciar o ciclo de vida de canais privados

Confira [Gerenciar o ciclo de vida dos canais privados no Teams](private-channels-life-cycle-management.md) para obter orientação sobre como gerenciar o ciclo de vida de canais privados na sua organização. Isso inclui como controlar se os usuários da sua organização podem criar canais privados, como criar um canal privado em nome do proprietário de equipe, como obter uma lista de todas as mensagens de canal privado para fins de arquivamento e auditoria e outras tarefas de gerenciamento.  

## <a name="private-channel-sharepoint-sites"></a>Sites do SharePoint em canal privado

Cada canal privado tem seu próprio conjunto de sites do SharePoint. O conjunto de sites separado é para garantir que o acesso aos arquivos do canal privado seja restrito apenas aos membros do canal privado, em comparação com o site de equipe em que os proprietários de equipe têm acesso a todos os ativos do conjunto de sites. Esses conjuntos de sites são criados com uma biblioteca de documentos por padrão e podem ser facilmente aprimorados para um conjunto de sites com todos os recursos por meio da [interface de gerenciamento de site](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Cada conjunto de sites é criado na mesma região geográfica do conjunto de sites de equipe pai. Esses sites leves têm uma ID de modelo personalizada, "TEAMCHANNEL# 0", para facilitar o gerenciamento por meio do PowerShell e da API do Graph.  Por padrão, eles não ficam visíveis no centro de administração do SharePoint.

Para acomodar um número maior de conjuntos de sites por locatário, o limite aumentou de 500.000 para 2 milhões. Um conjunto de sites de canal privado sincroniza a classificação de dados e herda permissões de acesso de convidado do conjunto de sites da equipe pai.  A associação do proprietário do conjunto de sites e dos grupos de membros é mantida em sincronia com a associação do canal privado no Teams. As alterações na associação de grupos de Proprietário ou Membro no SharePoint Online serão revertidas para a associação de canal particular dentro de quatro horas automaticamente. Em situações em que determinados usuários precisam acessar os documentos sem a necessidade de acessar mensagens de canal privado, adicione-os ao grupo visitantes no site ou a um novo grupo separado de Proprietários e Membros.

O Teams gerencia o ciclo de vida do conjunto de sites de canal privado do SharePoint. Se o conjunto de sites for excluído fora do Teams, um trabalho em segundo plano restaurará o site dentro de quatro horas, desde que o canal privado ainda esteja ativo. Se o site for excluído e excluído irreversivelmente, um novo conjunto de sites será provisionado para o canal privado.

Se um canal privado ou uma equipe que contenha um canal privado for restaurado, os conjuntos de sites serão restaurados com ele. Se um conjunto de sites de canal privado for restaurado e estiver passado da janela de exclusão temporária de 30 dias do canal privado, o conjunto de sites funcionará como um conjunto de sites autônomo.

## <a name="private-channel-message-compliance-records"></a>Registros de conformidade de mensagens no canal privado

Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo. Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.

Para obter mais informações sobre como executar uma pesquisa de Descoberta Eletrônica por mensagens de canal privado, consulte [Descoberta Eletrônica de Canal Privado](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Considerações sobre o acesso em canais privados

Quando um novo bloco de anotações do OneNote é criado em um canal privado, usuários adicionais ainda podem obter acesso ao bloco de anotações porque o comportamento é o mesmo que compartilhar o acesso a qualquer outro item em um site do SharePoint de canal privado com um usuário.

Se um usuário tiver acesso concedido a um bloco de anotações em um canal privado pelo SharePoint, remover o usuário da equipe ou do canal privado não removerá o acesso do usuário ao bloco de anotações.

Se um bloco de anotações existente for adicionado como uma guia a um canal privado, o acesso ao canal privado não será alterado. Isso significa o seguinte:

- Nem todos no canal privado terão acesso ao bloco de anotações por padrão. Isso ocorre porque eles podem não ter acesso ao local onde o bloco de anotações está hospedado, como o site do SharePoint de outra equipe.
- Os usuários que não são membros do canal privado podem visualizar o bloco de anotações.  

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral de equipes e canais no Teams](teams-channels-overview.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar a API do Microsoft Graph para trabalhar com o Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
