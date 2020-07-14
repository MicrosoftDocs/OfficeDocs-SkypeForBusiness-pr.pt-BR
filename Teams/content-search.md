---
title: Usar a pesquisa de conteúdo no Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Saiba como usar a pesquisa de conteúdo no Microsoft Teams para consultar informações do Microsoft Teams do Exchange, do SharePoint Online, do OneDrive for Business e do OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d05d815a74fc395c06763920014b7de453847bec
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121521"
---
<a name="use-content-search-in-microsoft-teams"></a>Usar a pesquisa de conteúdo no Microsoft Teams
=====================================

> [!NOTE]
> A pesquisa de conteúdo de mensagens e arquivos em [canais privados](private-channels.md) funciona de forma diferente do que em canais padrão. Para saber mais, consulte [pesquisa de conteúdo em canais privados](#content-search-of-private-channels).

A pesquisa de conteúdo fornece uma maneira de consultar as informações do Microsoft Teams estendido o Exchange, o SharePoint Online e o OneDrive for Business.

Para saber mais, leia [pesquisa de conteúdo no Microsoft 365 ou no Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

Por exemplo, ao usar a **pesquisa de conteúdo** em sua caixa de correio de especificações de fabricação e especificações de fabricação do site do SharePoint, você pode pesquisar as conversas de canal padrão do teams do Exchange, uploads e alterações de arquivos do SharePoint Online e alterações do OneNote.

Você também pode adicionar critérios de consulta à **pesquisa de conteúdo** para restringir os resultados retornados. No exemplo acima, você pode procurar por conteúdo em que as palavras-chave "**novas especificações de fábrica"** foram usadas.

> [!TIP]
> Depois de adicionar critérios de pesquisa, você pode exportar um relatório ou os dados para o seu computador para análise.

## <a name="content-search-of-private-channels"></a>Pesquisa de conteúdo em canais privados

Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo. Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.

Como cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.

O Teams não oferece suporte à pesquisa de conteúdo de um único canal, portanto, a equipe inteira deve ser pesquisada. Para executar uma pesquisa de conteúdo de um canal privado, pesquise na equipe, no conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).

Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir em sua pesquisa de conteúdo.

### <a name="include-private-channel-files-in-a-content-search"></a>Incluir arquivos de canal privado em uma pesquisa de conteúdo

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
3. Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canais particulares relevantes.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Incluir mensagens de canal privado em uma pesquisa de conteúdo

Antes de executar essas etapas, verifique se você tem a [versão mais recente do módulo Teams PowerShell](teams-powershell-overview.md) instalada.

1. Execute o seguinte para obter uma lista de canais privados na equipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Execute o seguinte para obter uma lista de membros do canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Inclua as caixas de correio de todos os membros de cada canal privado da equipe como parte da consulta de pesquisa de conteúdo.

## <a name="related-topics"></a>Tópicos relacionados

- [casos de descoberta eletrônica no centro de conformidade do Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 