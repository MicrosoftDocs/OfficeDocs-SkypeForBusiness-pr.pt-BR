---
title: Limitar quem os usuários podem ver ao pesquisar o diretório no Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como limitar quem os usuários podem ver ao pesquisar o diretório no Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046423"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>Limitar quem os usuários podem ver ao pesquisar o diretório no Teams

Microsoft Teams permite que as organizações forneçam exibições personalizadas do diretório para seus usuários. Essas exibições podem ser úteis se:

- Sua organização tem várias empresas dentro no locatário que você deseja manter separadas.
- Suas políticas de negócios exigem que você impeça que determinados grupos em sua organização se comuniquem entre si.
- Sua escola quer limitar os chats entre professores e alunos.

Há duas opções para limitar quem os usuários podem ver ao pesquisar o diretório no Teams:

- [Barreiras de informações no Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Políticas de catálogo de endereços Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)

Se estiver usando uma das opções, você deverá ativar a pesquisa por nome no Teams de administração.

É recomendável usar barreiras de informações se sua organização atender às [licenças e permissões necessárias](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions).

Para ativar a pesquisa por nome

1. No centro Microsoft Teams administrador, selecione **Teams** >  **Teams configurações**.

1. Em **Pesquisar por nome**, ao lado da pesquisa de diretório de escopo usando **uma Exchange** de catálogo de endereços, ative a **alternância**.

> [!Note]
> Pode levar algumas horas para que essa alteração entre em vigor.
> 
> Ativar a pesquisa por nome oculta a caixa **Pesquisar equipes** e a listagem de equipes públicas em **Ingressar ou criar uma equipe** no Teams. Ele também desabilitará o ingresso em uma equipe digitando `/join` na caixa de comando na parte superior Teams.
