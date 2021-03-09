---
title: Usar a pesquisa de diretório no escopo do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar a pesquisa de diretório com escopo do Microsoft Teams para fornecer exibições personalizadas do diretório.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ba7de8cea23efc23f1eaa6c568d87b0d3ec750
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558320"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar a pesquisa de diretório no escopo do Microsoft Teams

A pesquisa de diretório com escopo do Microsoft Teams permite que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários em sua organização. 

O Microsoft Teams permite que as organizações forneçam exibições personalizadas do diretório para seus usuários. O Microsoft Teams usa [políticas de Barreira de](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) Informações para dar suporte a esses exibições personalizadas. Depois que as políticas são habilitadas, os resultados retornados pelas pesquisas de outros usuários (por exemplo, para iniciar um chat ou para adicionar membros a uma equipe) serão escopos de acordo com as políticas configuradas. Os usuários não poderão pesquisar ou descobrir nenhuma equipe quando a pesquisa com escopo estiver em vigor, mas os membros existentes nessas equipes podem adicionar usuários, conforme permitido pelas políticas ativas da Barreira de Informações.

> [!NOTE]
> Em ambientes híbridos do Exchange, esse recurso só funciona com caixas de correio do Exchange Online e não com caixas de correio locais.

## <a name="when-should-you-use-scoped-directory-searches"></a>Quando você deve usar pesquisas de diretório com escopo?

Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política do livro de endereços. Por exemplo, talvez você queira usar a pesquisa de diretório com escopo nas seguintes situações:

- Sua organização tem várias empresas dentro no locatário que você deseja manter separadas. 
- Sua escola quer limitar os chats entre professores e alunos. 
 
Para saber como usar políticas de livro de endereços, leia [Políticas de Barreira de](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)Informações no Exchange Online .

> [!IMPORTANT]
> As políticas do livro de endereços fornecem apenas uma separação virtual dos usuários da perspectiva do diretório. Também é importante observar que quaisquer dados de usuário que já foram armazenados em cache, antes da aplicação de políticas de livro de endereços novas ou atualizadas, permanecerão disponíveis para os usuários por até 30 dias.

## <a name="turn-on-scoped-directory-search"></a>Ativar a pesquisa de diretório com escopo

1. Use políticas de Barreira de Informações para configurar sua organização em subgrupos virtuais. Para obter mais informações, consulte [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).

2. No centro de administração do Microsoft Teams, selecione **Configurações do** Teams em toda a  >  **organização.**

3. Em **Pesquisa**, ao lado da pesquisa de diretório escopo no Teams usando uma política de livro de **endereços do Exchange (ABP),** a opção **Ativar**.

    ![Pesquisa de diretório com escopo no Centro de administração do Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Essa alteração pode levar algumas horas para ser replicada.
