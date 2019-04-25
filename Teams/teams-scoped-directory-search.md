---
title: Usar a pesquisa de diretório no escopo do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Saiba como usar a pesquisa de diretório com escopo Teams da Microsoft para fornecer exibições personalizadas do diretório.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3b51b56b8cc8a1f08d756cdab245915a2ac6824
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226644"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar a pesquisa de diretório no escopo do Microsoft Teams

A pesquisa de diretório com escopo Teams Microsoft permite que as organizações a criar limites virtuais que controlam como os usuários podem localizar e se comunicar com outros usuários em suas organizações. 

Teams Microsoft permite que as organizações fornecem exibições personalizadas do diretório para seus usuários. Microsoft Teams usa [políticas de catálogo de endereços do Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) para oferecer suporte a esses modos de exibição personalizados. Depois que as diretivas estão habilitadas, os resultados retornados pelo procura por outros usuários (por exemplo, para iniciar um chat ou adicionar membros a uma equipe) terá o escopo de acordo com as diretivas configuradas. Os usuários não poderão pesquisar ou descobrir equipes quando com escopo de pesquisa está em vigor. 

## <a name="when-should-you-use-scoped-directory-searches"></a>Quando você deve usar as pesquisas de diretório com escopo?

Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política de catálogo de endereços. Por exemplo, convém usar a pesquisa de diretório com escopo nas seguintes situações:

- Sua organização tem várias empresas dentro no locatário que você deseja manter separadas. 
- Sua escola quer limitar os chats entre professores e alunos. 
 
Para saber como usar políticas de catálogo de endereços, leia o [Catálogo de endereços, diretivas no Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

> [!IMPORTANT]
> Políticas de catálogo de endereços fornecem apenas uma virtual separação de usuários da perspectiva de diretório. Os usuários ainda podem iniciar a comunicação com outras pessoas, fornecendo endereços de email completo. Também é importante observar que quaisquer dados de usuário que tinham já foram armazenados em cache, antes da aplicação de políticas de catálogo de endereços novos ou atualizados, ficará disponíveis para os usuários por até 30 dias.

## <a name="enable-scoped-directory-search"></a>Habilitar a pesquisa de diretório com escopo

1.  Use políticas de catálogo de endereços para configurar sua organização em subgrupos virtuais. Para obter mais informações, consulte [procedimentos para políticas de catálogo de endereços](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

2.  Entrar no Centro de administração do Microsoft 365, selecione **centrais de Admin**e selecione **equipes & Skype**.
 
3.  No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização** > **configurações de equipes**.

4.  Em **pesquisa**, ao lado de **pesquisa de diretório do escopo em equipes usando uma política de catálogo de endereços do Exchange (APB)**, ative a alternância **em**. 

    ![Escopo de pesquisa de diretório no Centro de administração do Microsoft Teams](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Configurações híbridas (equipes com Exchange local) não suportam o modo de pesquisa com escopo. 

