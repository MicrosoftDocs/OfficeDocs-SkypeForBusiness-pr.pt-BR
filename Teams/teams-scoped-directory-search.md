---
title: Usar a pesquisa de diretório no escopo do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
- Teams_ITAdmin_Help
description: Saiba como usar a pesquisa de diretório em escopo do Microsoft Teams para fornecer exibições personalizadas do diretório.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 068a37af62ea31c53caed8c9dc22feec6fd60ec6
ms.sourcegitcommit: bd9b29cdaa183b1f5cc2d643a5a2d231a56a2c3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "35614256"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar a pesquisa de diretório no escopo do Microsoft Teams

A pesquisa de diretório em escopo do Microsoft Teams permite que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários em sua organização. 

O Microsoft Teams permite que as organizações forneçam modos de exibição personalizados do diretório para seus usuários. O Microsoft Teams usa [políticas do catálogo de endereços do Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) para dar suporte a essas exibições personalizadas. Depois que as políticas são habilitadas, os resultados retornados por pesquisas para outros usuários (por exemplo, para iniciar um chat ou para adicionar membros a uma equipe) serão definidos em escopo de acordo com as políticas configuradas. Os usuários não poderão pesquisar nem descobrir Teams quando a pesquisa com escopo estiver em vigor. 

## <a name="when-should-you-use-scoped-directory-searches"></a>Quando você deve usar pesquisas de diretório de escopo?

Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política de catálogo de endereços. Por exemplo, você pode querer usar a pesquisa de diretório em escopo nas seguintes situações:

- Sua organização tem várias empresas dentro no locatário que você deseja manter separadas. 
- Sua escola quer limitar os chats entre professores e alunos. 
 
Para saber como usar as políticas do catálogo de endereços, leia [as políticas do catálogo de endereços no Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

> [!IMPORTANT]
> As políticas de catálogo de endereços fornecem apenas uma separação virtual de usuários da perspectiva do diretório. Os usuários ainda podem iniciar comunicações com outras pessoas fornecendo endereços de e-mail completos. Também é importante observar que todos os dados do usuário que já haviam sido armazenados em cache, antes da aplicação de políticas novas ou atualizadas do catálogo de endereços, permanecerão disponíveis para os usuários por até 30 dias.

## <a name="turn-on-scoped-directory-search"></a>Ativar a pesquisa de diretório escopo

1. Use as políticas de catálogo de endereços para configurar sua organização em subgrupos virtuais. Para obter mais informações, consulte [procedimentos para políticas do catálogo de endereços](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

2. No centro de administração do Microsoft Teams, selecione**configurações de equipes** **de configurações** > de toda a organização.

3. Em **Pesquisar**, ao lado de **pesquisa de diretório de escopo no Teams usando uma política de catálogo de endereços do Exchange (APB)**, ative o botão de alternância. ****

    ![Pesquisa de diretório em escopo no centro de administração do Microsoft Teams](media/teams-scoped-directory-search-image1.png)



