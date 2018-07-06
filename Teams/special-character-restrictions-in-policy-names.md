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
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205074"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quais são as restrições de caractere especial nas políticas de equipes?

**Embora os caracteres especiais podem ser usados para criar políticas de equipes com o PowerShell, você será limitada no gerenciamento essas políticas.  Sendo assim, é altamente recomendável nomes de política não incluir caracteres especiais.**

Nomes de política que você criar usando o PowerShell para reuniões e bate-papo no equipes podem ter caracteres especiais, como @, #, $. No entanto, se você estiver buscando editar a política no Microsoft Teams e Skype para centro de administração de negócios, você não conseguirá. Você deve usar o Windows PowerShell e o cmdlet diretiva correta para fazer alterações.

Se você tiver um objeto de diretiva com caracteres especiais e você deseja remover os caracteres especiais para gerenciar melhor a política na Microsoft Teams e Skype para centro de administração de negócios, você precisará usar o abaixo procedimento. 

Observação: O procedimento organizado aqui usa o exemplo de uma política de mensagens.  O mesmo processo seria usado para outro tipo de política (por exemplo em reuniões) por subsituting os cmdlets relevantes. 

1). chamar Get-CSMessagingPolicy-identity < nome_da_diretiva_antiga > e capture a saída da política.
2). chamar Set-CSMessagingPolicy-identity < nome_da_diretiva_nova > para criar uma nova política com a mesma configuração como a diretiva original, mas sem caracteres especiais no nome de usuário.
3.) chamada Delete-CSMessagingPolicy-identity < nome_da_diretiva_antiga > para excluir a diretiva.  Se este comando for bem-sucedido, você terminar e pode começar a atribuir usuários à nova diretiva usando o PowerShell ou o Microsoft Teams e Skype para centro de administração de negócios.
4.) se o comando acima não tiver êxito, é porque a diretiva old foi atribuída a um usuário.  Executar retirar a atribuição de cmdlet para retirar a atribuição de política de usuário, atribua a nova política e execute dwlete novamente.


