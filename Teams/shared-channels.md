---
title: Canais compartilhados no Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
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
ms.localizationpriority: high
search.appverid: MET150
description: Saiba como usar e gerenciar canais compartilhados no Microsoft Teams.
ms.openlocfilehash: 72701d71712a553c9a02cf9ab41ce0ced0597c3a
ms.sourcegitcommit: c74c83fdb3fdbf1a5ebc9398bf0379d33f888d1b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65795633"
---
# <a name="shared-channels-in-microsoft-teams"></a>Canais compartilhados no Microsoft Teams

Os canais compartilhados no Microsoft Teams criam espaços de colaboração onde você pode convidar pessoas que não estão na equipe. Apenas os usuários que são proprietários ou membros do canal compartilhado podem acessar o canal. Embora os convidados (pessoas com contas de convidado do Azure Active Directory na sua organização) não possam ser adicionados a um canal compartilhado, você pode convidar pessoas de fora da sua organização para participarem de um canal compartilhado usando a conexão direta do Azure AD B2B.

Talvez você queira usar um canal compartilhado se quiser colaborar com um grupo de pessoas que são membros de equipes diferentes. Por exemplo, pessoas da engenharia, vendas e suporte que trabalham em diferentes aspectos do mesmo projeto ou produto podem usar um canal compartilhado para colaborar.

Apenas os membros de canais privados podem ver e participar de canais privados aos quais foram adicionados. Outros membros da equipe à qual o canal compartilhado está conectado não verão o canal.

Quando um canal privado é criado, ele é vinculado à equipe pai e não pode ser movido para uma equipe diferente. Além disso, os canais compartilhados não podem ser convertidos em canais padrão e vice-versa.

[Compare os canais compartilhados com outros tipos de canais](/microsoftteams/teams-channels-overview#channel-feature-comparison).

## <a name="getting-started-with-shared-channels"></a>Introdução aos canais compartilhados

Você pode escolher se as pessoas podem criar canais compartilhados, se elas podem compartilhá-los com pessoas de fora da sua organização e se elas podem participar de canais compartilhados externos [criando uma política de canal](/MicrosoftTeams/teams-policies).

Se você planeja compartilhar canais com pessoas de fora da sua organização, leia o [Planejar a colaboração externa](/microsoft-365/solutions/plan-external-collaboration) com considerações de planejamento importantes.

O compartilhamento de canais com pessoas de fora da sua organização também exige que você defina as configurações de acesso entre locatários no Azure AD. Cada organização com a qual você quer compartilhar canais também deve concluir essa configuração. Consulte [Colaborar com participantes externos em um canal](/microsoft-365/solutions/collaborate-teams-direct-connect) para obter detalhes.

## <a name="shared-channel-creation"></a>Criação do canal compartilhado

Apenas os proprietários de equipe podem criar um canal compartilhado. Os membros e convidados da equipe não podem criá-los. A capacidade de criar canais privados pode ser gerenciada no nível da equipe e da organização. Use as [políticas](teams-policies.md) para controlar quais usuários na sua organização podem criar canais privados.

A pessoa que cria um canal compartilhado se torna o proprietário do canal compartilhado e apenas o proprietário do canal compartilhado pode adicionar ou remover pessoas diretamente dele. (Você pode adicionar mais de um proprietário se quiser.) Um proprietário de canal compartilhado pode adicionar pessoas da organização a um canal compartilhado criado por eles. Os membros de um canal compartilhado têm um espaço de conversa seguro e, quando novos membros são adicionados, eles podem visualizar todas as conversas (até mesmo conversas antigas) nesse canal compartilhado.

Os proprietários da equipe podem ver os nomes de todos os canais compartilhados na sua equipe e também podem excluir canais compartilhados na equipe. Os proprietários da equipe não podem ver os arquivos em um canal compartilhado ou a lista de conversas e membros de um canal compartilhado, a menos que sejam membros desse canal compartilhado.

Os membros da equipe só podem ver canais compartilhados aos quais foram adicionados.

A clonagem de uma equipe não clona os canais compartilhados associados.

## <a name="shared-channel-deletion"></a>Exclusão do canal compartilhado

O canal compartilhado excluído pode ser restaurado dentro de 30 dias após a exclusão. Quando um canal compartilhado excluído é restaurado, todas as associações anteriores (compartilhamento individual e de equipe) serão restauradas.

As equipes excluídas podem ser restauradas dentro de 30 dias após a exclusão. Quando uma equipe é excluída, todos os canais compartilhados também serão excluídos. Quando uma equipe excluída é restaurada, todos os canais compartilhados também serão restaurados com todas as relações de compartilhamento.

Quando uma equipe é arquivada, o compartilhamento individual permanecerá intacto, mas o compartilhamento com equipes diferentes da equipe pai será removido. Quando a equipe arquivada for desarquivada, todos os canais compartilhados serão restaurados apenas com o compartilhamento individual.

## <a name="adding-and-removing-owners-and-members"></a>Adicionando e removendo proprietários e membros

O proprietário de um canal privado não pode ser removido pelo cliente do Teams se ele for o último proprietário de um ou mais canais compartilhados.

Se o último proprietário do canal compartilhado sair da sua organização ou se ele for removido do grupo do Microsoft 365 associado à equipe, um membro do canal compartilhado será promovido automaticamente para ser o proprietário do canal compartilhado. Considere adicionar mais de um proprietário para evitar essa situação.

## <a name="channel-owner-settings"></a>Configurações de proprietário do canal

Cada canal compartilhado possui suas próprias configurações que o proprietário do canal pode gerenciar, incluindo a capacidade de adicionar e remover membros, adicionar guias e @mencionar no canal. Essas configurações são independentes das configurações da equipe pai. Quando um canal compartilhado é criado, ele herda as configurações da equipe pai, após o qual suas configurações podem ser alteradas independentemente das configurações da equipe pai.

O proprietário do canal compartilhado pode clicar em **Gerenciar canal** e usar as guias **Membros** e **Configurações** para adicionar ou remover membros e editar configurações.

## <a name="shared-channel-owner-and-member-actions"></a>Ações de proprietário e membro do canal privado

A tabela a seguir descreve quais ações os proprietários, membros e convidados podem executar nos canais compartilhados.

|Ação  |Proprietário de equipe|Membro da equipe|Convidado da equipe|Proprietário do canal compartilhado|Membro do canal compartilhado|Participante externo do canal compartilhado|
|---------|---------|---------|---------|---------|---------|---------|
|Criar canal compartilhado|Controlado pelo administrador|Controlado pelo administrador e proprietário da equipe|Não|Não disponível|Não|Não|
|Excluir canal compartilhado|Sim|Não|Não|Sim|Não|Não|
|Sair do canal compartilhado|Não disponível|Não disponível|Não disponível|Sim, a menos que eles sejam o último proprietário|Sim|Sim|
|Editar canal compartilhado|Não|Não disponível|Não disponível|Sim|Não|Não|
|Restaurar canal compartilhado excluído|Sim|Não|Não|Sim|Não|Não|
|Adicionar membros|Não|Não disponível|Não disponível|Sim|Não|Não|
|Editar configurações|Não|Não disponível|Não disponível|Sim|Não|Não|
|Gerenciar guias e aplicativos|Não|Não disponível|Não disponível|Sim, os aplicativos devem ser instalados para a equipe|Controle de proprietário do canal|Não|

## <a name="shared-channel-sharepoint-sites"></a>Sites do SharePoint do canal compartilhado

Cada canal compartilhado tem [seu próprio site do SharePoint](/SharePoint/teams-connected-sites). O site separado é para garantir que o acesso aos arquivos do canal compartilhado seja restrito apenas aos membros do canal compartilhado. Esses sites são criados com uma biblioteca de documentos por padrão e podem ser facilmente aprimorados para um site completo por meio da [interface de gerenciamento de site](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Cada site é criado na mesma região geográfica do site de equipe pai. Esses sites leves têm uma ID de modelo personalizada, "TEAMCHANNEL# 0", para facilitar o gerenciamento por meio do PowerShell e da API do Graph. 

> [!NOTE]
> Somente pessoas com permissões de proprietário ou membros do canal terão acesso ao conteúdo no site do canal compartilhado. Os administradores e as pessoas da equipe não terão acesso, a menos que também sejam membros do canal.

Um site do canal compartilhado sincroniza a classificação dos dados do site da equipe pai. A associação ao proprietário do site e aos grupos de membros é mantida em sincronia com a associação do canal compartilhado. As permissões de site de um site de canal compartilhado não podem ser gerenciadas independentemente pelo SharePoint. 

O Teams gerencia o ciclo de vida do site de canal compartilhado. Se o site for excluído fora do Teams, ele será restaurado automaticamente dentro de quatro horas, desde que o canal compartilhado ainda esteja ativo. Se o site for excluído permanentemente, um novo site será provisionado ao canal privado.

Se um canal compartilhado ou uma equipe que contiver um canal compartilhado for restaurado, os sites serão restaurados com ele. Se um site de canal compartilhado for restaurado e estiver além da janela de exclusão temporária de 30 dias no canal compartilhado, o site operará como um site autônomo.

## <a name="shared-channel-messages"></a>Mensagens do canal compartilhado

As mensagens de canal compartilhado são armazenadas em uma caixa de correio de sistema dedicada associada ao canal compartilhado em vez da caixa de correio do grupo.

Para obter mais informações sobre como executar uma pesquisa de Descoberta Eletrônica nas mensagens do canal compartilhado, consulte [Realizar uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams](ediscovery-investigation.md).

## <a name="considerations-around-file-access-in-shared-channels"></a>Considerações sobre o acesso ao arquivo nos canais compartilhados

Arquivos, pastas e blocos de anotações do OneNote em um canal compartilhado podem ser compartilhados com pessoas fora do canal usando o [compartilhamento de arquivos padrão do SharePoint](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c).

Se um usuário tiver acesso a um arquivo, pasta ou bloco de anotações em um canal compartilhado pelo SharePoint, remover o usuário da equipe ou do canal compartilhado não removerá o acesso do usuário ao arquivo, pasta ou bloco de anotações.

Se um bloco de anotações existente for adicionado como uma guia a um canal compartilhado, o acesso ao canal compartilhado não será alterado e o bloco de anotações manterá suas permissões existentes.

## <a name="resources-for-your-users"></a>Recursos para seus usuários

Os artigos a seguir podem ser úteis para os usuários em sua organização quando eles usam canais compartilhados.

[Criar um canal compartilhado no Teams](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Compartilhe um canal com pessoas no Teams](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[Compartilhe um canal com uma equipe](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[Por que usar um canal compartilhado versus outros tipos de canal no Teams?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Convidados e canais compartilhados no Teams](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Proprietários de canais compartilhados e vagas de membros no Teams](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels"></a>Limites para canais compartilhados

A tabela a seguir descreve o número máximo de canais e membros.

|Máximo...|Valor|Observações|
|:---------|:----|:----|
|Membros em uma equipe|25.000|Inclui todos os usuários na equipe e membros diretos nos canais compartilhados.|
|Canais compartilhados por equipe|200|Hospedado e compartilhado com a equipe. (Inclui canais excluídos durante a janela de recuperação de 30 dias.)|
|Equipes com quem um canal pode ser compartilhado|50|Excluindo a equipe pai|
|Membros em um canal compartilhado|5.000 membros diretos, incluindo até 50 equipes. (Cada equipe com a qual o canal é compartilhado conta como um membro tendo em vista esse limite).|As atualizações em tempo real só estão disponíveis para 25.000 usuários por vez e apenas 25.000 usuários serão exibidos na lista de canais.|

As seguintes limitações também se aplicam:

- Os canais compartilhados dão suporte a guias, exceto Stream, Planner e Forms.

- Aplicativos LOB, bots, conectores e extensões de mensagem não são compatíveis.

- Quando você cria uma equipe de uma equipe existente, os canais compartilhados na equipe existente não serão copiados.

- As notificações de canais compartilhados não estão incluídas nos e-mails das atividades perdidas.

## <a name="supported-apps-in-shared-channels"></a>Aplicativos com suporte em canais compartilhados

Para obter informações sobre como preparar seu aplicativo para canais compartilhados, consulte [Como abrir seu aplicativo para colaboração entre organizações com o Microsoft Teams Connect](https://mybuild.microsoft.com/sessions/4d84d73c-08de-4f56-990b-2a73b2037df1).

Os aplicativos a seguir têm suporte para uso em canais compartilhados. 

- Atividade
- Adobe Acrobat Sign
- Asana
- Calendário
- Calendário Pro
- Chamadas
- Bate-papo
- Código por Vivani
- Conceptboard
- Excel
- FileBrowser
- Arquivos
- Flipgrid
- Freehand por InVision
- HeyTaco
- Jira Cloud
- Kahoot!
- Listas
- Lucidchart
- Lumio
- MeisterTask
- MindMeister
- Mindomo
- Miro
- Monday.com
- MURAL
- Nearpod
- OneNote
- PDF
- Pear Deck
- PowerPoint
- Priority Matrix
- Quicklinks
- Quizlet
- Saved
- Scrum-Poker
- Pesquisar
- SharePoint
- Páginas do SharePoint
- Slido
- Smartsheet
- SurveyMonkey
- Tasks in a Box
- Teams
- Teams Manager
- TeamViewer
- Trabalho em equipe
- Testportal
- TrackingTime
- Trello
- Vevox
- Visio
- VSTS
- Wakelet
- Web
- Wooclap
- Palavra
- YouTube
- Zendesk
- Zoho Projects

## <a name="related-topics"></a>Tópicos relacionados

[Visão geral da conexão direta B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Definir as configurações de acesso entre locatários para a conexão direta B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Visão geral de equipes e canais no Teams](teams-channels-overview.md)

[Canais privados no Microsoft Teams](/microsoftteams/private-channels)
