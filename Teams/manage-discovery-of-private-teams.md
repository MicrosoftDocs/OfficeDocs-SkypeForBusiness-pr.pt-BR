---
title: Gerenciar a descoberta de equipes privadas em Teams da Microsoft
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como controlar se as equipes privadas podem ser descobertas pelos usuários do Microsoft Teams usando sugestões nos resultados de pesquisa e de galeria da equipe.
ms.openlocfilehash: 3609a592c3c940e9f7cbec6ca5c58fd072322c46
ms.sourcegitcommit: 0bb55cad74b15fc821ae916799aa8c0cb13dd31d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2019
ms.locfileid: "33497949"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Gerenciar a descoberta de equipes privadas em Teams da Microsoft

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

Proprietários de equipe e os administradores podem controlar se as equipes privadas podem ser descobertas pelos usuários Teams da Microsoft em sua organização. Quando uma equipe privada é detectável, ele aparecerá nos resultados da pesquisa e está incluído no sugestões na Galeria de equipe, junto com as equipes públicas em equipes. Isso torna fácil para os usuários procurar e encontre as equipes privadas que desejam ingressar. Os usuários podem solicitar para ingressar em uma equipe privada que um proprietário de equipe pode, em seguida, aprovar ou negar.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Visão geral das equipes públicas, privadas equipes e descoberta em equipes

A maioria das organizações têm os seguintes tipos de equipes - públicas equipes, equipes privadas detectáveis e equipes privadas não detectáveis.

![Galeria de equipe](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Equipes de públicas

Equipes públicas estão disponíveis para todos os usuários em sua organização ingressar. As equipes de públicas são visíveis para todos na Galeria de equipes e os usuários podem ingressar em uma equipe pública sem precisar obter aprovação do proprietário equipe. Exemplos de equipes públicas incluem uma equipe para discutir notícias em uma equipe de rodízio pessoas trabalhem, uma equipe para obter feedback dogfood para os produtos e tecnologia.

### <a name="discoverable-private-teams"></a>Equipes privadas detectáveis

Detectáveis equipes privadas só podem ser incluídas quando o proprietário de equipe adiciona usuários a eles. Quando você faz uma equipe privada detectáveis, a equipe está incluída na lista de equipes sugeridas e resultados de pesquisa na Galeria de equipes. Use detectáveis equipes privadas para projetos e grupos na sua organização que todos está ciente e onde o acesso a conversas e arquivos na equipe de precisam ser controlados. Exemplos incluem uma equipe para seu departamento de RH, uma equipe para todos os gerentes em sua organização e uma equipe para um gerente e seus relatórios diretos.

### <a name="non-discoverable-private-teams"></a>Não-detectável equipes privadas

Não-detectável equipes privadas só podem ser incluídas quando o proprietário de equipe adiciona usuários a eles. Quando você faz uma equipe privada não detectável, ele tem oculto da lista de equipes sugeridas e removidas dos resultados da pesquisa na Galeria de equipes. Use as equipes de não-identificável para colaborar nos tópicos altamente confidenciais. Exemplos incluem uma equipe para discutir uma aquisição futura e uma equipe para discutir uma alteração na direção estratégica de sua organização.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Defina se novas equipes privadas são detectáveis

Quando um proprietário de equipe cria uma equipe privada, eles podem optar por torná-lo localizável, definindo a configuração de descoberta da equipe. Por padrão, as novas equipes privadas são pesquisáveis e detectáveis. Se o proprietário de equipe não quiser que a equipe particular seja mostrada no sugestões e resultados de pesquisa, eles podem desativar a configuração selecionando **Alterar configuração** ao lado de **Este equipe é pesquisável e detectáveis**.

![configuração de descoberta de novas equipes privadas](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Defina se as equipes privadas existentes estão detectáveis

Proprietários de equipe podem definir a configuração de descoberta para uma equipe privada existente diretamente nas configurações de equipe e os administradores podem fazer isso usando o PowerShell.

### <a name="in-team-settings"></a>Nas configurações de equipe

Em equipes, vá para a equipe privada, clique em **mais ˙˙˙ de opções** > **equipe gerenciar**. Na guia **configurações** , expanda a **descoberta de equipe**e desmarque ou marque a caixa de seleção **Ativar o recurso de descoberta** .

![configuração de descoberta para equipes privadas existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a>Usando o PowerShell (em breve)

Use o cmdlet **Set-equipe** para desativar ou ativar a configuração de descoberta para uma equipe privada existente. Aqui está um exemplo de como tornar uma equipe detectável:

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
Você pode usar esse cmdlet em um script para definir a configuração de descoberta de equipes privadas existentes em massa.

## <a name="set-whether-users-can-discover-private-teams"></a>Definir se os usuários podem descobrir equipes privadas

Como um administrador, você pode controlar quais usuários em sua organização têm permissão para descobrir privadas equipes nos resultados da pesquisa e sugestões em equipes. Criar uma diretiva usando o cmdlet **New-CsTeamsChannelsPolicy** e, em seguida, atribuir a política aos usuários.
 
Defina o parâmetro **AllowPrivateTeamDiscovery** como **true** para permitir que os usuários que receberem a política para ver as equipes de privada detectáveis em resultados da pesquisa e sugestões. O parâmetro **AllowPrivateTeamDiscovery** a definição como **false** remove todas as equipes privadas detectáveis resultados da pesquisa e sugestões para os usuários atribuídos a política.

Por padrão, **AllowPrivateTeamDiscovery** é definido como **true** para todos os usuários em uma organização.

Neste exemplo, criamos uma política de chamada VendorPolicy que impede que os usuários descobrindo qualquer equipes privadas que são feitas detectáveis e, em seguida, atribuímos a política a uma usuária chamada vendoruser1. 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> Privada equipes que não são detectáveis nunca são mostradas em resultados da pesquisa e sugestões, independentemente da configuração de política. Por exemplo, se você desativar a configuração de descoberta para uma equipe privada, os usuários não conseguem descubram da equipe, mesmo que o parâmetro **AllowPrivateTeamDiscovery** seja definido como **true** na configuração de diretiva para os usuários.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)