---
title: Teams PowerShell - Versões com suporte
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba mais sobre versões com suporte do Teams PowerShell, usado para administração de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e292e3ea5659920bca6fe6f663afc53164da5b49
ms.sourcegitcommit: e3a4df81721abe83886714a7c3c798e4c0888c35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2022
ms.locfileid: "64617702"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell - Versões com suporte

Microsoft Teams versões do PowerShell Module (TPM) na série 4.x.x ou acima serão as únicas versões com suporte para avançar. Todas as versões anteriores estão no caminho da aposentadoria. É recomendável atualizar o Teams PowerShell para a versão mais recente.



## <a name="new-organizations"></a>Novas organizações

As organizações recém-Teams poderão usar o módulo Teams PowerShell na série 4.x.x ou acima a partir de 1º de abril de 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizações atuais (não ativas do TPM)

As organizações que não usaram o módulo powershell do Teams nos últimos três meses (22 de janeiro – 22 de março), só poderão usar o módulo Teams PowerShell na série 4.x.x ou acima a partir de 1º de abril de 2022.



## <a name="current-organizations-tpm-active"></a>Organizações atuais (TPM ativo)

As organizações que têm usado o módulo powershell do Teams nos últimos três meses (Jan'22 – Mar'22), só poderão usar o módulo Teams PowerShell na série 4.x.x ou acima a partir de 15 de junho de 2022. Postagem da central de mensagens para referência - MC350371. 



## <a name="important-notes"></a>Anotações importantes

- Notas de versão para todas as Teams do PowerShell Module podem ser encontradas [Teams notas de versão do PowerShell](teams-powershell-release-notes.md).

- Para atualizar qualquer módulo do PowerShell, você deve usar o mesmo método usado para instalar o módulo. Por exemplo, se você usou o Install-Module originalmente, deve usar [o Update-Module](/powershell/module/powershellget/update-module) para obter a versão mais recente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Se atualizar do Teams PowerShell versão 1.1.6, atualize seus scripts `Connect-MicrosoftTeams` para usar em vez de `New-CsOnlineSession`.

-   Durante a atualização, é sugerido não usar o TPM 4.x.x/3.x.x. juntamente com versões anteriores a 3.0.0. Por exemplo, não é recomendável usar as versões 4.x.x & 2.6.0 em conjunto para diferentes operações de administrador na mesma organização. 

- Alterações relacionadas
  * Atualizações para Get-CsOnlineUser & Get-CsOnlineVoiceUser no TPM 3.x.x e acima – mais detalhes em [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (Postagem do Centro de Mensagens – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Alterações na atribuição de número de telefone - mais detalhes em [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Postagem do centro de mensagens – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)

  * Deprecation of Get-CsOnlineDirectoryTenant – mais detalhes em [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant) (Postagem do centro de mensagens – MC346902).



## <a name="related-topics"></a>Tópicos relacionados

[Teams notas de versão do PowerShell](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Gerenciar Teams com Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams de cmdlet](/powershell/module/teams) 

[Skype for Business de cmdlet](/powershell/module/skype) 
