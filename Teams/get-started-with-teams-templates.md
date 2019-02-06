---
title: Introdução aos modelos do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar modelos de equipes para criar uma equipe com canais predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08abde935b69aa58e5e54bd50b31f1c9d554552e
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742954"
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
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | Não há aplicativos adicionais e propriedades |
| Educação-<br>Equipe de classe | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Aplicativos:<ul><li>Bloco de anotações de classe do OneNote (fixados a guia **Geral** ) </li><li>Aplicativo de atribuições (fixado a guia **Geral** )</li></ul> Propriedades de equipe:<ul><li>Visibilidade da equipe é definido como **HiddenMembership** (não pode ser substituída)</li></ul> |
| Educação-<br>Equipe de equipe | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Aplicativos:<ul><li>Bloco de anotações de equipe do OneNote (fixados a guia **Geral** )</li></ul> |
|Educação-<br>Equipe PLC |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Aplicativos:<ul><li>Anotações do OneNote PLC (fixados a guia **Geral** )</ul></li>|
| Varejo-<br>Repositório | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore` | Canais:<ul><li>Deslocar da entrega</li><li>Aprendizado</li></ul>Propriedades da equipe<ul><li>Visibilidade da equipe pública</li></ul>Permissões de membro<ul><li>Impedir que os membros da criação, atualizem ou remoção de canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros da criação, atualizem ou remoção de conectores</li></ul> |
| Varejo-<br>Gerenciador de colaboração | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration` | Canais:<ul><li>Deslocar da entrega</li><li>Aprendizado</li></ul>Propriedades de equipe:<ul><li>Visibilidade da equipe definida como privado</li></ul>Permissões de membro:<ul><li>Impedir que os membros da criação, atualizem ou remoção de canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros da criação, atualizem ou remoção de conectores</li></ul>|
| Saúde-<br>Bairro |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareWardWide` |Canais: <ul><li>Anúncios\*</li><li>Luzes de chamada</li><li>Coisas divertida\*</li><li>Huddles\*</li><li>Arredonda</li><li>Treinamento\*</li></ul>\*Canais de auto-favorited |
|Saúde-<br>Hospital | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareHospitalWide` |Canais:<ul><li>Anúncios\*</li><li>Conformidade\*</li><li>Custódia</li><li>Finanças</li><li>Coisas divertida\*</li><li>Recursos humanos</li><li>Laboratório</li></li><li>Farmácia</li></ul>\*Auto-favorited channel|
|||

> [!NOTE]
> Serão adicionados mais modelo base digita em futuras versões do Microsoft Teams, para verificar novamente as informações mais atualizadas sobre suporte a propriedades.


## <a name="related-topics"></a>Tópicos relacionados

- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (no modo de visualização)
- [Nova equipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento para o administrador do Microsoft Teams](itadmin-readiness.md)
- [Introdução ao modelos de equipes de varejo](get-started-with-retail-teams-templates.md)
- [Introdução ao modelos de equipes de atendimento médico](healthcare/healthcare-templates.md)
