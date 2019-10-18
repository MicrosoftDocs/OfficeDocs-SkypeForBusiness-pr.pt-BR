---
title: Gerenciar a descoberta de equipes particulares no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como controlar se as equipes particulares podem ser descobertas pelos usuários do Microsoft Teams por meio de sugestões na Galeria de equipe e nos resultados da pesquisa.
ms.openlocfilehash: b60c06299f779ebe798db1ff3df465f1683508ed
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571995"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Gerenciar a descoberta de equipes particulares no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Administradores e proprietários de equipe podem controlar se as equipes particulares podem ser descobertas pelos usuários do Microsoft Teams em sua organização. Quando uma equipe privada é detectável, ela é mostrada nos resultados da pesquisa e está incluída em sugestões na Galeria de equipes juntamente com equipes públicas do Microsoft Teams. Isso torna mais fácil para os usuários procurarem e encontrarem as equipes particulares que desejam participar. Os usuários podem solicitar para ingressar em uma equipe particular, e o proprietário da equipe pode aprovar ou recusar a solicitação.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Visão geral de equipes públicas, equipes particulares e descoberta no Microsoft Teams

A maioria das organizações tem os seguintes tipos de Teams: equipes públicas, equipes privadas detectáveis e equipes privadas não detectáveis.

![Captura de tela da Galeria de equipes](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Equipes públicas

As equipes públicas estão disponíveis para que todos os usuários de sua organização ingressem. As equipes públicas são visíveis para todos na Galeria de equipes, e os usuários podem ingressar em uma equipe pública sem ter que obter a aprovação do proprietário da equipe. Exemplos de equipes públicas incluem uma equipe para discutir notícias sobre tecnologia, uma equipe para obter comentários de seus produtos e uma equipe para que as pessoas carpoolingm de trabalhar.

### <a name="discoverable-private-teams"></a>Equipes privadas detectáveis

As equipes privadas detectáveis só podem ser Unidas quando o proprietário da equipe adiciona usuários a elas. Quando você torna uma equipe particular detectável, a equipe está incluída na lista de equipes sugeridas e nos resultados da pesquisa na galeria do teams. Use equipes particulares detectáveis para projetos e grupos em sua organização que todos estão cientes e onde o acesso a conversas e arquivos na equipe precisa ser controlado. Os exemplos incluem uma equipe para seu departamento de RH, uma equipe para todos os gerentes da sua organização e uma equipe para um gerente e seus relatórios diretos.

### <a name="non-discoverable-private-teams"></a>Equipes privadas não detectáveis

As equipes privadas não detectáveis só podem ser Unidas quando o proprietário da equipe adiciona usuários a elas. Quando você torna uma equipe privada não detectável, ela fica oculta na lista de equipes sugeridas e removida dos resultados da pesquisa na galeria do teams. Use o Microsoft Teams não detectável para colaborar em tópicos confidenciais e altamente confidenciais. Os exemplos incluem uma equipe para discutir uma aquisição futura e uma equipe para discutir uma alteração na orientação estratégica da sua organização.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Definir se novas equipes particulares são detectáveis

Quando um proprietário da equipe cria uma equipe particular, ele pode optar por torná-lo detectável Configurando a configuração de descoberta da equipe. Por padrão, novas equipes particulares são pesquisáveis e detectáveis. Se o proprietário da equipe não quiser que a equipe privada apareça nos resultados da pesquisa e sugestões, o proprietário poderá desativar a configuração selecionando **Alterar configuração** ao lado **desta equipe pode ser pesquisada e detectável**.

![Captura de tela da configuração de descoberta para novas equipes particulares](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Definir se as equipes privadas existentes são detectáveis

Os proprietários da equipe podem definir a configuração de descoberta para uma equipe particular existente diretamente nas configurações da equipe e os administradores podem fazê-lo usando o PowerShell.

### <a name="in-team-settings"></a>Em configurações da equipe

No Teams, vá para a equipe particular, clique em **mais opções** > **Gerenciar equipe**. Na guia **configurações** , expanda **descoberta de equipe**e desmarque ou marque a caixa de seleção **habilitar** a descoberta.

![Captura de tela da configuração de descoberta para equipes privadas existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>Usando o PowerShell

Use o cmdlet **[set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** para desativar ou ativar a configuração de descoberta para uma equipe privada existente. Veja um exemplo de como deixar uma equipe detectável:
```
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
Você pode usar esse cmdlet em um script para definir a configuração de descoberta de equipes particulares existentes em massa.

## <a name="set-whether-users-can-discover-private-teams"></a>Definir se os usuários podem descobrir equipes privadas

Como administrador, você também pode controlar quais usuários em sua organização podem descobrir equipes particulares nos resultados da pesquisa e sugestões no Teams. Crie uma política usando o cmdlet **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** e, em seguida, atribua a política aos usuários.
 
Defina o parâmetro **AllowPrivateTeamDiscovery** como **true** para permitir aos usuários que a política sejam atribuídas a Confira equipes particulares detectáveis nos resultados da pesquisa e sugestões. Definir o parâmetro **AllowPrivateTeamDiscovery** como **false** remove todas as equipes particulares detectáveis dos resultados da pesquisa e sugestões para os usuários atribuídos à política.

Por padrão, **AllowPrivateTeamDiscovery** é definido como **verdadeiro** para todos os usuários de uma organização.

Neste exemplo, criamos uma política denominada VendorPolicy que impede os usuários de descobrir qualquer equipe particular que seja tornada detectável e, em seguida, atribuímos a política a um usuário chamado vendoruser1.
```
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> As equipes privadas não detectáveis nunca são mostradas em resultados e sugestões de pesquisa, independentemente da configuração de política. Por exemplo, se você desativar a configuração de descoberta para uma equipe particular, os usuários não conseguirão descobrir a equipe, mesmo que o parâmetro **AllowPrivateTeamDiscovery** esteja definido como **true** na configuração de política para esses usuários.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
