---
title: Usar modelos do teams no console de administração
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar os modelos do teams para criar espaços de colaboração com canais para tópicos diferentes usando modelos pré-instalados.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: cc62eeb2cbbc14ce921c3f85860a72d38b59965d
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583168"
---
# <a name="get-started-with-teams-templates-in-the-teams-admin-console"></a>Introdução aos modelos do teams no console de administração do teams

[!INCLUDE [template](includes/preview-feature.md)]

**Os modelos personalizados ainda não têm suporte para clientes EDU.**

> [!NOTE]
> Atualmente, os modelos de equipe não dão suporte à criação de canais particulares. A criação do canal privado não está incluída nas definições do modelo.

Os modelos de equipe são definições predefinidas da estrutura de uma equipe projetada em torno de uma necessidade ou projeto comercial. Use modelos predefinidos ou crie seu próprio modelo. Os modelos de equipe permitem que você crie rapidamente espaços de colaboração avançados com canais para diferentes tópicos e aplicativos pré-instalar para obter conteúdo e serviços de missão crítica. Os modelos de equipe fornecem uma estrutura de equipe predefinida que pode ajudá-lo a criar facilmente equipes consistentes em toda a sua organização. No momento, você pode usar um modelo no console de administração ou usando o [Microsoft Graph](get-started-with-teams-templates.md).

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
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações da equipe (por exemplo, membro, convidado, @ menção) | Arquivos e conteúdo |
| Canal de favoritos automático | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto verifique as informações mais atualizadas sobre as propriedades com suporte.

## <a name="what-are-base-template-types"></a>O que são tipos de modelo base

Tipos de modelo básico são modelos especiais criados pela Microsoft para indústrias específicas. Esses modelos básicos geralmente contêm aplicativos proprietários que estão disponíveis na loja de aplicativos.

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais por propriedades adicionais que gostaria de especificar. Mas alguns tipos de modelo básico contêm propriedades que não podem ser substituídas.

> [!NOTE]
> Os modelos de base predefinidos fornecidos no Microsoft Teams podem ser duplicados, mas não podem ser editados.


| Tipo de modelo base | Propriedades que vêm com este modelo base |
| ------------------ |----------------------------------------------------- |
| Adotar o Office 365 |  Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Canto dos Campeões</li> <li>Formulários de equipe</li></ul> Aplicativo <ul><li>Wiki</li>  <li>Calendário</li> |
| Gerenciar um projeto | Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Recursos</li> <li>Planejamento</li></ul> Aplicativo<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gerenciar um evento | Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e PR</li></ul> Aplicativo<ul><li>Wiki</li><li>Site</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Funcionários onboard | Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Aplicativo<ul><li>Wiki</li><li>Às</li>|</ul>
|Organizar o Help Desk| Canais<ul><li>Geral</li><li>Comunicados</li><li>Perguntas frequentes</li></ul>Aplicativo<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colabore no atendimento ao paciente | Canais<ul><li>Geral</li><li>Comunicados</li><li>Huddles</li><li>Arredonda</li><li>Especificam</li><li>Treinamento</li></ul> Aplicativo <ul><li>Wiki</li>|
| Colaborar em uma crise global ou em um evento |Canais <ul><li>Geral<li>Comunicados</li><li>Notícias do mundo</li><li>Continuidade de negócios</li><li>Trabalho remoto</li><li>Comms internas</li><li>Comentários externos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Atualização executiva</li></ul>Aplicativo <ul><li>Elogia</li><li>Wiki</li><li>Site</li></ul>|
|Colaborar dentro de um Branch bancário |Canais <ul><li>Geral<li>Comunicados</li><li>Huddles</li><li>Reuniões do cliente</li><li>Treina</li><li>Desenvolvimento de habilidades</li><li>Processamento de empréstimos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Coisas divertidas</li><li>Conformidade</li></ul>|
|Coordenar resposta a incidentes |Canais <ul><li>Geral<li>Comunicados</li><li>Logística</li><li>Planejamento</li><li>Automatiza</li><li>Urgente</li></ul> Aplicativo <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital |Canais <ul><li>Geral<li>Comunicados</li><li>Conformidade</li><li>> custodial/li<li>Recursos humanos</li><li>Farmácia</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
|Organizar uma loja |Canais <ul><li>Geral<li>Deslocar entrega</li><li>Aprendizagem</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
|Qualidade e segurança |Canais <ul><li>Geral<li>Comunicados</li><li>Linha 1</li><li>Linha 2</li><li>Linha 3</li><li>Segurança</li><li>Treinamento</li><li>Manutenção</li><li>Coisas divertidas</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
|Colaboração do gerente de varejo |Canais <ul><li>Geral<li>Operações</li><li>Aprendizagem</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
|||

## <a name="related-topics"></a>Tópicos relacionados

- [Criar um modelo de equipe personalizado](create-a-team-template.md)
- [Criar um modelo de equipe a partir de um modelo de equipe existente](create-template-from-existing-template.md)
- [Criar um modelo a partir de uma equipe existente](create-template-from-existing-team.md)
