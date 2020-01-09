---
title: Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: Saiba o que fazer quando precisar executar uma Descoberta Eletrônica, como quando precisar enviar todas as informações armazenadas eletronicamente para procedimentos judiciais.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43105db9a4e12d658bf5cf2e9c2c8897fdc918e3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989786"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams
============================

Grandes empresas muitas vezes são expostas a grandes procedimentos legais de penalidade que exigem o envio de todas as ESI (informações armazenadas eletronicamente).

Todas as equipes 1:1 ou chats em grupo são registradas nas caixas de correio dos respectivos usuários e todas as mensagens de canal padrão são registradas na caixa de correio do grupo que representa a equipe. Os arquivos carregados em canais padrão são cobertos pela funcionalidade de descoberta eletrônica do SharePoint Online e do OneDrive for Business.

> [!NOTE]
> a descoberta eletrônica de mensagens e arquivos em [canais privados](private-channels.md) funciona de maneira diferente em canais padrão. Para saber mais, consulte [descoberta eletrônica de canais privados](#ediscovery-of-private-channels).

1.  Para conduzir uma investigação de descoberta eletrônica com o conteúdo do Microsoft Teams, examine [a](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) etapa 1 neste link.

2.  Os dados do Microsoft Teams serão exibidos como mensagens instantâneas ou conversas na saída de exportação do Excel para descoberta eletrônica, e você poderá montar o. PST no Outlook para exibir essas mensagens postar na exportação.

    Ao montar o .PST para a equipe, observe que todas as conversas serão mantidas na pasta Bate-papo em Equipe no Histórico de Conversas. O título da mensagem corresponde à Equipe a ao Canal. Para revisar a imagem abaixo, você pode ver esta mensagem em Bob que encontrava o canal padrão do Project 7 da equipe de especificações de fabricação.

    ![Captura de tela de uma pasta de chat de equipe na caixa de correio de um usuário no Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Para ver chats privados na caixa de correio de um usuário, eles também estão localizados dentro da pasta de chat da equipe em histórico de conversas.

## <a name="ediscovery-of-guest-to-guest-chats"></a>Descoberta eletrônica de chats convidados para convidados

Atualmente, para um cenário em que apenas convidados participam do 1:1 ou 1: N chat, não oferecemos suporte para a eDiscovery dessas mensagens de chat. 

Sem uma caixa de correio, chats convidados para convidados (chats 1xN em que não há usuários locatários domésticos) não seriam indexados e, consequentemente, não seriam incluídos na descoberta eletrônica. Para facilitar a descoberta eletrônica para chats convidados a convidados, uma caixa de correio baseada em nuvem (ou uma caixa de correio fantasma) é criada para armazenar os dados do 1xN. Depois que os dados de chat de equipe são armazenados na caixa de correio baseada em nuvem, eles são indexados para pesquisa de conteúdo de descoberta eletrônica e conformidade.

A ilustração a seguir mostra como a descoberta eletrônica funciona para chats convidados a convidados em que não há uma caixa de correio.

![convidado para convidado-chats com e sem caixa de correio](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a>Descoberta eletrônica de canais privados

Os registros de mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo. Os títulos dos registros são formatados para indicar o canal privado do qual foram enviados.

Como cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.

O Microsoft Teams não é compatível com a descoberta eletrônica de um único canal, portanto, a equipe inteira deve ser pesquisada. Para executar uma pesquisa de descoberta eletrônica do conteúdo em um canal privado, pesquise na equipe, no conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).

Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir em sua pesquisa de descoberta eletrônica.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir arquivos de canal privado em uma pesquisa de descoberta eletrônica

Antes de executar essas etapas, instale o [Shell de gerenciamento do SharePoint Online e conecte-se ao SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Execute o seguinte para obter uma lista de todos os conjuntos de sites do SharePoint associados a canais privados na equipe.

    ```PowerShell
    Get-SPOSite
    ```
2. Execute o seguinte script do PowerShell para obter uma lista de todas as URLs de conjuntos de sites do SharePoint associadas a canais privados na equipe e a ID do grupo pai da equipe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canais particulares relevantes, em que $groupID é a ID de grupo da equipe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensagens de canal privado em uma pesquisa de descoberta eletrônica

Antes de executar essas etapas, verifique se você tem a [versão mais recente do módulo Teams PowerShell](teams-powershell-overview.md) instalada.

1. Execute o seguinte para obter uma lista de canais privados na equipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Execute o seguinte para obter uma lista de membros do canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Inclua as caixas de correio de todos os membros de cada canal privado da equipe como parte da sua consulta de pesquisa de descoberta eletrônica.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
