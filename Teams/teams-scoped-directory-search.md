---
title: Usar Microsoft Teams no escopo de pesquisa de diretório
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar a pesquisa de diretório com escopo Teams da Microsoft para fornecer exibições personalizadas do diretório.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b62b3e27cf0aa10ea6719cb1f27980ee83f4421
ms.sourcegitcommit: c4254b6119bbce274f895e20d30cb3c513d5a2de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2018
ms.locfileid: "25455960"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar Microsoft Teams no escopo de pesquisa de diretório

A pesquisa de diretório com escopo Teams Microsoft permite que as organizações a criar limites virtuais que controlam como os usuários podem localizar e se comunicar com outros usuários em suas organizações. 

Teams Microsoft permite que as organizações fornecem exibições personalizadas do diretório para seus usuários. Microsoft Teams usa [políticas de catálogo de endereços do Exchange](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) para oferecer suporte a esses modos de exibição personalizados. Depois que as diretivas estão habilitadas, os resultados retornados pelo procura por outros usuários (por exemplo, para iniciar um chat ou adicionar membros a uma equipe) terá o escopo de acordo com as diretivas configuradas. Os usuários não poderão pesquisar ou descobrir e ingressar novas equipes fora essas políticas. 

## <a name="when-should-you-use-scroped-directory-searches"></a>Quando você deve usar scroped pesquisas de diretório?

Cenários que se beneficiam de pesquisas de diretório com escopo são semelhantes aos cenários de política de catálogo de endereços. Por exemplo, convém usar a pesquisa de diretório com escopo nas seguintes situações:

- Sua organização tem várias empresas dentro de seu locatário que você deseja manter separados. 
- Sua escola deseja limitar chats entre professores e alunos. 
 
Você pode aprender mais sobre como as políticas de catálogo de endereços podem ser usadas [aqui](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).

> [!IMPORTANT]
> Políticas de catálogo de endereços fornecem apenas uma virtual separação de usuários da perspectiva de diretório. Os usuários ainda podem iniciar a comunicação com outras pessoas, fornecendo endereços de email completo. 

## <a name="enable-scoped-directory-search"></a>Habilitar a pesquisa de diretório com escopo

1.  Use políticas de catálogo de endereços para configurar sua organização em subgrupos virtuais. Para obter mais informações, consulte [procedimentos para políticas de catálogo de endereços](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).

2.  Entrar no Centro de administração do Microsoft 365, selecione **centrais de Admin**e selecione **equipes & Skype**.
 
3.  No Microsoft Teams & Skype para centro de administração de negócios, selecione **configurações de toda a organização** > **configurações de equipes**.

4.  Em **pesquisa**, ao lado de **pesquisa de diretório do escopo em equipes usando uma política de catálogo de endereços do Exchange (APB)**, ative a alternância **em**. 

    ![Escopo de pesquisa de diretório em equipes & Skype para centro de administração de negócios](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Configurações híbridas (equipes com Exchange local) não suportam o modo de pesquisa com escopo. 

