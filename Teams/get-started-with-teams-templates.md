---
title: Introdução aos modelos do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Saiba como usar modelos de equipes para criar uma equipe com canais predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b620f163f1dc071bde8a0ed43bf7fe546a9bc04a
ms.sourcegitcommit: 355bcdafa58b6349bb6bc771054f4c9c91387a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013633"
---
# <a name="get-started-with-teams-templates"></a>Introdução aos modelos do Microsoft Teams 

Modelos de equipes são pré-criados definições da estrutura de uma equipe Projetado levando em consideração uma necessidade comercial ou projeto. Você pode usar modelos de equipes para criar rapidamente os espaços de colaboração avançada com canais para tópicos diferentes e pré-instalação de aplicativos seja obtida dos planejamentos nos serviços e conteúdo de missão crítica. Os modelos de equipes fornecem uma estrutura de equipe predefinidas que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização. 

Neste artigo, vamos explicar as propriedades que podem ser definidas nos modelos, qual modelo base tipos forem, e como você pode usar algumas solicitações para criar uma equipe a partir de um modelo de exemplo.
 
Este artigo é para você, se você estiver:

- Responsável pelo planejamento, implantação e gerenciamento de várias equipes em toda a organização<br>
- Um desenvolvedor querer criar programaticamente uma equipe com aplicativos e canais predefinidos 

## <a name="teams-template-capabilities"></a>Recursos do modelo de equipes

A maioria das propriedades em uma equipe são incluídas e suportado por modelos. Mas há algumas propriedades e recursos que não são suportados no momento. A tabela a seguir fornece um resumo rápido o que está incluído e o que não está incluído nos modelos de equipes.

| **Propriedades da equipe compatíveis com os modelos de equipes** | **Propriedades da equipe ainda não é suportadas por modelos de equipes** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação de equipe |
| Nome da equipe | Imagem de equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade de equipe (pública ou privada) | Conectores |
| Configurações de equipe (por exemplo, o membro, o convidado, @ menções) | Arquivos e conteúdo |
| Autofavorito canal | |
| Aplicativo instalado | |
| Guias fixados | | 

> [!NOTE]
> Podemos vai ser adicionando mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente para obter as informações mais atualizadas sobre propriedades com suporte.

## <a name="what-are-base-template-types"></a>Quais são os tipos de modelo base?

Tipos de modelo base são modelos especiais que a Microsoft criou para setores específicos. Esses modelos base geralmente contêm proprietários aplicativos que não estão disponíveis nas propriedades do repositório e a equipe que ainda não são aceitas individualmente nos modelos de equipes.

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar. Mas alguns tipos de modelo base contém propriedades que não podem ser substituídas. 

Por padrão, o modelo base é definido para o **padrão** que não contenha nenhum apps proprietárias adicionais ou propriedades especiais. Abaixo é a lista atual de tipos de modelo base disponíveis.

| Tipo de modelo base | baseTemplateId | Propriedades que acompanham este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Não há aplicativos adicionais e propriedades |
| Educação-<br>Equipe de classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Aplicativos:<ul><li>Bloco de anotações de classe do OneNote (fixados a guia **Geral** ) </li><li>Aplicativo de atribuições (fixado a guia **Geral** )</li></ul> Propriedades de equipe:<ul><li>Visibilidade da equipe é definido como **HiddenMembership** (não pode ser substituída)</li></ul> |
| Educação-<br>Equipe de equipe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Aplicativos:<ul><li>Bloco de anotações de equipe do OneNote (fixados a guia **Geral** )</li></ul> |
|Educação-<br>Equipe PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicativos:<ul><li>Anotações do OneNote PLC (fixados a guia **Geral** )</ul></li>|
| Varejo-<br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canais:<ul><li>Deslocar da entrega</li><li>Aprendizado</li></ul>Propriedades da equipe<ul><li>Visibilidade da equipe pública</li></ul>Permissões de membro<ul><li>Impedir que os membros da criação, atualizem ou remoção de canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros da criação, atualizem ou remoção de conectores</li></ul> |
| Varejo-<br>Gerenciador de colaboração | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canais:<ul><li>Deslocar da entrega</li><li>Aprendizado</li></ul>Propriedades de equipe:<ul><li>Visibilidade da equipe definida como privado</li></ul>Permissões de membro:<ul><li>Impedir que os membros da criação, atualizem ou remoção de canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros da criação, atualizem ou remoção de conectores</li></ul>|
| Saúde-<br>Bairro |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canais: <ul><li>Anúncios\*</li><li>Huddles\*</li><li>Arredonda</li><li>Criação da equipe\*</li><li>Treinamento\*</li></ul>\*Canais de auto-favorited |
|Saúde-<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canais:<ul><li>Anúncios\*</li><li>Conformidade\*</li><li>Custódia</li><li>Recursos humanos</li></li><li>Farmácia</li></ul>\*Auto-favorited channel|
|||

> [!NOTE]
> Serão adicionados mais modelo base digita em futuras versões do Microsoft Teams, para verificar novamente as informações mais atualizadas sobre suporte a propriedades.


## <a name="related-topics"></a>Tópicos relacionados

- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (no modo de visualização)
- [Nova equipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento de administrador para o Microsoft Teams](itadmin-readiness.md)
- [Introdução aos modelos de Equipes de varejo](get-started-with-retail-teams-templates.md)
- [Introdução aos modelos do Teams para Organizações de Assistência Médica](expand-teams-across-your-org/healthcare/healthcare-templates.md)
