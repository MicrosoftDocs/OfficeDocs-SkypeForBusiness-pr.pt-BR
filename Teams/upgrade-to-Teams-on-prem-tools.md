---
title: Ferramentas para atualizar para Teams de uma implantação Skype for Business local
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Ferramentas para atualização de Skype for Business para Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d98257e9a29564d22b57c5cc537d703bbb1fe842
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729300"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Ferramentas para atualizar para Teams &mdash; para administradores de IT

Este artigo descreve ferramentas para atualizar para Teams de Skype for Business. 

Antes de iniciar a atualização, a Microsoft recomenda os seguintes artigos que descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Ferramentas para gerenciar a atualização

Qualquer método de atualização que você escolher, para usuários que já Skype for Business Online, você gerencia a transição para o TeamsOnly usando [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário. Para usuários com uma conta local no Skype for Business Server, você também usa `Move-CsUser` para movê-los [para a nuvem](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obter mais informações sobre cada um dos modos, consulte [Modos de coexistência](migration-interop-guidance-for-teams-with-skype.md).

> [!NOTE]
> Se você estiver usando o Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo Teams PowerShell e atualizar os scripts existentes do PowerShell. Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module for](teams-powershell-move-from-sfbo.md) more information.

Se você executar uma transição de recursos selecionados usando Skype for Business modos ou simplesmente atualizar para o modo TeamsOnly a partir da configuração padrão das Ilhas, TeamsUpgradePolicy é a ferramenta principal. Como qualquer outra política Teams, você pode atribuir TeamsUpgradePolicy diretamente a um usuário. Você também pode definir a política como o padrão de todo o locatário. Qualquer atribuição a um usuário tem precedência sobre a configuração padrão do locatário.  Você pode gerenciar a política no console Teams Admin e no PowerShell.

Você pode atribuir qualquer modo do TeamsUpgradePolicy, exceto o modo TeamsOnly, aos usuários que estão Skype for Business local. Por outro lado, os usuários que estão na nuvem só podem ser atribuídos ao modo TeamsOnly. O modo **TeamsOnly** só pode ser atribuído a um usuário que já está na nuvem porque a interop e a federação com usuários do Skype for Business, bem como a funcionalidade Microsoft 365 Sistema de Telefonia, só serão possíveis se o usuário estiver em casa no Skype for Business Online.  Além disso, não será possível atribuir o modo **TeamsOnly** como o padrão de todo o locatário se você tiver uma implantação local do Skype for Business (que é detectada pela presença de um registro DNS de descoberta lyncdiscover que aponta para um local diferente do Office 365. Para obter detalhes, [consulte Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).

Os usuários com Skype for Business contas no local devem ser [movidos](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) online para o modo Somente Teams usando Move-CsUser no Skype for Business local. 

Ao contrário de outras políticas, não é possível criar novas instâncias do TeamsUpgradePolicy em Microsoft 365 ou Office 365. Todas as instâncias existentes são criadas no serviço.  (Observe que o modo é uma propriedade dentro do TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns casos, mas não em todos os casos, o nome da instância da política é o mesmo que o modo. Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" do TeamsUpgradePolicy a esse usuário. Para ver uma lista de todas as instâncias, você pode executar o seguinte comando:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para atualizar um usuário local Skype for Business para o modo TeamsOnly, use Move-CsUser no toolset local:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

Para alterar o modo para todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Se você tiver usuários com Skype for Business contas locais, não poderá atribuir o modo TeamsOnly no nível do locatário. Você deve mover esses usuários individualmente para Teams modo Somente usando Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Usando notificações em Skype for Business clientes

Os administradores têm a opção de fornecer notificações de usuário final no cliente Skype for Business para informar aos usuários que eles serão atualizados em breve para Teams, conforme mostrado no diagrama a seguir. Por exemplo, uma semana antes de o administrador planeja atualizar um grupo de usuários para o modo TeamsOnly, talvez o administrador queira ativar essas notificações para esse grupo de usuários. Essas notificações são habilitadas usando uma instância do TeamsUpgradePolicy com NotifySfbUsers=true.  Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.  Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers. 

![Diagrama mostrando notificações.](media/teams-upgrade-sfb-with-notifications.png)

Se os usuários estão em casa no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers=true. 

Se os usuários estão Skype for Business Server no local, você precisará usar o toolset local e você precisará do Skype for Business Server 2019 ou cu8 para Skype for Business Server 2015. Para usuários que estão Skype for Business Server local, a propriedade mode da instância online do TeamsUpgradePolicy é agraciada, mas a propriedade NotifySfbUsers não é. Se as notificações são desejadas, você deve criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente. 

Na janela local do PowerShell, crie uma nova instância do TeamsUpgradePolicy com NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Em seguida, usando a mesma janela local do PowerShell, atribua essa nova política aos usuários desejados:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migração de reunião

Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões Skype for Business existentes que organizaram serão convertidas em Teams. Opcionalmente, você pode desabilitar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário. Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para funcionar com a conta de usuário online, mas se você não especificar -MoveToTeams, as reuniões serão migradas como reuniões Skype for Business, em vez de convertidas em Teams. 

Ao atribuir o modo TeamsOnly no nível do locatário, a migração de reunião não é disparada para nenhum usuário. Se você deseja atribuir o modo TeamsOnly ao nível do locatário e migrar reuniões, poderá usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando o Get-CsOnlineUser com quaisquer filtros necessários) e, em seguida, fazer um loop por cada um desses usuários para disparar a migração de reunião usando Start-CsExMeetingMigration. Para obter detalhes, [consulte Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).



## <a name="related-links"></a>Links relacionados

[Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
