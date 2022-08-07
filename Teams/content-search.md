---
title: Usar a pesquisa de conteúdo no Microsoft Teams
author: v-tophillips
ms.author: v-tophillips
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Saiba mais sobre como usar a pesquisa de conteúdo no portal de conformidade do Microsoft Purview para pesquisar o conteúdo do Microsoft Teams armazenado no Exchange Online, SharePoint Online, OneDrive for Business e OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a069478dc65fcafb5e1354796360c994aa2f0d36
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267436"
---
# <a name="use-content-search-in-microsoft-teams"></a>Usar a pesquisa de conteúdo no Microsoft Teams

> [!NOTE]
> A pesquisa de conteúdo de mensagens e arquivos [em canais privados](private-channels.md) funciona de maneira diferente dos canais padrão. Para saber mais, confira [Pesquisa de conteúdo de canais privados](#content-search-of-private-channels).

A pesquisa de conteúdo fornece uma maneira de consultar informações do Microsoft Teams que abrangem o Exchange, o SharePoint Online e OneDrive for Business.

Para saber mais, confira [Pesquisa de conteúdo no Microsoft 365](/microsoft-365/compliance/content-search).

Por exemplo, usando  a pesquisa de conteúdo em sua caixa de correio de Especificações de Fabricação e no site do SharePoint de Especificações de Fabricação, você pode pesquisar conversas de canal padrão do Teams do Exchange, uploads de arquivos e modificações do SharePoint Online e alterações do OneNote.

Você também pode adicionar critérios de consulta à Pesquisa **de Conteúdo** para restringir os resultados retornados. No exemplo acima, você pode procurar o conteúdo em que as palavras-chave "Novas Especificações **de Fábrica" foram usadas** .

> [!TIP]
> Depois de adicionar condições de pesquisa, você pode exportar um relatório ou o conteúdo real para o computador para análise.

## <a name="content-search-of-private-channels"></a>Pesquisa de conteúdo de canais privados

Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo. Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.

Como cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.

O Teams não dá suporte à pesquisa de conteúdo de um único canal, portanto, toda a equipe deve ser pesquisada. Para executar uma pesquisa de conteúdo de um canal privado, pesquise pela equipe, o conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).

Use as etapas a seguir para identificar arquivos e mensagens em um canal privado a serem incluídos na pesquisa de conteúdo.

### <a name="include-private-channel-files-in-a-content-search"></a>Incluir arquivos de canal privado em uma pesquisa de conteúdo

Antes de executar essas etapas, instale o [Shell de Gerenciamento do SharePoint Online e conecte-se ao SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Execute o seguinte para obter uma lista de todos os conjuntos de sites do SharePoint associados a canais privados na equipe.

    ```PowerShell
    Get-SPOSite
    ```
2. Execute o script do PowerShell a seguir para obter uma lista de todas as URLs do conjunto de sites do SharePoint associadas a canais privados na equipe e à ID do grupo de equipe pai.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Para cada ID de equipe ou grupo, execute o script do PowerShell a seguir para identificar todos os sites de canal privado relevantes.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Incluir mensagens de canal privado em uma pesquisa de conteúdo

Antes de executar essas etapas, verifique se você tem a [versão mais recente do módulo PowerShell do Teams](teams-powershell-overview.md) instalada.

1. Execute o seguinte para obter uma lista de canais privados na equipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Execute o seguinte para obter uma lista de membros do canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Inclua as caixas de correio de todos os membros de cada canal privado na equipe como parte da consulta de pesquisa de conteúdo.

## <a name="related-topics"></a>Tópicos relacionados

- [Casos de Descoberta Eletrônica no portal de conformidade do Microsoft Purview](/Office365/SecurityCompliance/ediscovery-cases)