---
title: Quais são as restrições de caractere especial nas políticas de equipes?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Consulte quais problemas que existem com caracteres especiais nos nomes de políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192160"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quais são as restrições de caractere especial nas políticas de equipes?

**Embora você possa usar caracteres especiais nos nomes de políticas que você criou em equipes, é altamente recomendável que você não.**

Nomes de política que você criar para reuniões, chat e prescense e outras coisas em equipes podem ter caracteres especiais, como @, #, $. No entanto, se você estiver buscando fazer alterações para o nome no Microsoft Teams e Skype para centro de administração de negócios, você não conseguirá. Você deve usar o Windows PowerShell e o cmdlet diretiva correta para fazer alterações.

Por exemplo, se você tiver uma política de reunião com caracteres especiais e você deseja alterar o nome ou remova os caracteres especiais do nome, você precisará usar o cmdlet Set-CsMeetingPolicy. 

Aqui está uma lista dos cmdlets de política que você pode precisar fazer isso:
1. Set-CsMeetingPolicy
2. Set-CsAppPolicy
3. Set-*


