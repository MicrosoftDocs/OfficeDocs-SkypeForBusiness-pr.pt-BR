---
title: Introdução aos modelos do Teams
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
description: Saiba como usar os modelos do teams para criar uma equipe com canais predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 378977e86854f3c4b2192017fa10ce19aeb4990e
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968312"
---
# <a name="get-started-with-teams-templates"></a>Introdução aos modelos do Teams

> [!NOTE]
> Atualmente, os modelos de equipe não dão suporte à criação de canais particulares. A criação do canal privado não está incluída nas definições do modelo. 

Os modelos de equipe são definições predefinidas da estrutura de uma equipe projetada em torno de uma necessidade ou projeto comercial. Você pode usar modelos de equipe para criar rapidamente espaços de colaboração avançados com canais para diferentes tópicos e aplicativos pré-instalar para extrair conteúdo e serviços de missão crítica. Os modelos de equipe fornecem uma estrutura de equipe predefinida que pode ajudá-lo a criar facilmente equipes consistentes em toda a sua organização. 

Neste artigo, explicaremos as propriedades que podem ser definidas nos modelos, quais tipos de modelo básico são e como você pode usar algumas solicitações de exemplo para criar uma equipe a partir de um modelo.
 
Este artigo é para você, se estiver:

- Responsável por planejar, implantar e gerenciar várias equipes em toda a organização<br>
- Um desenvolvedor que queira criar programaticamente uma equipe com canais e aplicativos predefinidos

## <a name="teams-template-capabilities"></a>Recursos de modelos de equipes

A maioria das propriedades em uma equipe é incluída e suportada pelos modelos. Mas há algumas propriedades e recursos que não têm suporte no momento. A tabela a seguir fornece um resumo rápido do que está incluído e o que não está incluído nos modelos do teams.

| **Propriedades da equipe com suporte nos modelos de equipe** | **Propriedades da equipe ainda não são compatíveis com os modelos do teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Alinha |
| Configurações da equipe (por exemplo, membro, convidado, @ menção) | Arquivos e conteúdo |
| Canal de favoritos automático | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto verifique as informações mais atualizadas sobre as propriedades com suporte.

## <a name="what-are-base-template-types"></a>O que são tipos de modelo base?

Tipos de modelo básico são modelos especiais criados pela Microsoft para indústrias específicas. Esses modelos básicos geralmente contêm aplicativos proprietários que não estão disponíveis nas propriedades da loja e da equipe que ainda não são suportadas individualmente nos modelos do teams.

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais por propriedades adicionais que gostaria de especificar. Mas alguns tipos de modelo básico contêm propriedades que não podem ser substituídas.

Por padrão, o modelo base é definido como **padrão** , que não contém nenhum aplicativo proprietário adicional ou propriedades especiais. Abaixo está a lista atual de tipos de modelo base disponíveis.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Sem aplicativos e propriedades adicionais |
| Treinamento<br>Equipe de classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Aplicativo<ul><li>Bloco de anotações de classe do OneNote (fixado na guia **geral** ) </li><li>Aplicativo atribuições (fixadas na guia **geral** )</li></ul> Propriedades da equipe:<ul><li>Visibilidade da equipe definida como **HiddenMembership** (não pode ser substituída)</li></ul> |
| Treinamento<br>Equipe da equipe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Aplicativo<ul><li>Bloco de anotações de equipe do OneNote (fixado na guia **geral** )</li></ul> |
|Treinamento<br>Equipe de PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicativo<ul><li>Bloco de anotações de PLC do OneNote (fixado na guia **geral** )</ul></li>|
| Varejo<br>Armazenadas | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canais<ul><li>Deslocar entrega</li><li>Aprendizagem</li></ul>Propriedades da equipe<ul><li>Visibilidade da equipe definida como Public</li></ul>Permissões de membro<ul><li>Impedir que os membros criem, atualizem ou removam canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros criem, atualizem ou removam conectores</li></ul> |
| Varejo<br>Colaboração do gerente | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canais<ul><li>Deslocar entrega</li><li>Aprendizagem</li></ul>Propriedades da equipe:<ul><li>Visibilidade da equipe definida como particular</li></ul>Permissões de membro:<ul><li>Impedir que os membros criem, atualizem ou removam canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros criem, atualizem ou removam conectores</li></ul>|
| Intensivo<br>Flecha |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canais <ul><li>Comunicados\*</li><li>Huddles\*</li><li>Arredonda</li><li>Especificam\*</li><li>Curso\*</li></ul>\*Canais de favoritos automáticos |
|Intensivo<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canais<ul><li>Comunicados\*</li><li>Conformidade\*</li><li>Custodial</li><li>Recursos humanos</li></li><li>Farmácia</li></ul>\*Canal de preferência automática|
|||

> [!NOTE]
> Adicionaremos mais tipos de modelos básicos em versões futuras do Microsoft Teams, portanto verifique as informações mais atualizadas sobre as propriedades com suporte.

## <a name="related-topics"></a>Tópicos relacionados

- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)
- [New-Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento de administrador para o Microsoft Teams](itadmin-readiness.md)
- [Introdução aos modelos de varejo do Teams](get-started-with-retail-teams-templates.md)
- [Introdução aos modelos do Teams para Organizações de Saúde](expand-teams-across-your-org/healthcare/healthcare-templates.md)
