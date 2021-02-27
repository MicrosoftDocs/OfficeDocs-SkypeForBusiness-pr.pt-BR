---
title: Ferramentas para atualizar para o Teams a partir de uma implantação local do Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Ferramentas para atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61dc34d56ebb10dc7319d855bbd0d98184f1e54a
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347842"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Ferramentas para atualizar para o Teams &mdash; para administradores de IT

Este artigo descreve ferramentas para atualizar para o Teams. Este artigo é o terceiro de vários que descrevem conceitos de atualização e implementação para administradores de IT.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Ferramentas para gerenciar sua atualização**   (Este artigo)
- [Considerações adicionais para organizações com o Skype for Business local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar sua atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre a PSTN (Rede Telefônica Pública Comucionária)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência do Teams e do Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Ferramentas para gerenciar a atualização

Qualquer método de atualização que você escolher, para usuários que já têm o Skype for Business Online, você gerencia a transição para o TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário. Para usuários com uma conta local no Skype for Business Server, você também usa para `Move-CsUser` [movê-los para a nuvem.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Para obter mais informações sobre cada um dos modos, consulte [Modos de coexistência](migration-interop-guidance-for-teams-with-skype.md).

> [!NOTE]
> Se você estiver usando o Conector do Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo do PowerShell do Teams e atualizar os scripts existentes do PowerShell. Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.

Se você executar uma transição de recursos selecionados usando os modos do Skype for Business ou simplesmente atualizar para o modo TeamsOnly da configuração padrão das Ilhas, o TeamsUpgradePolicy é a principal ferramenta para usuários que já têm o Skype for Business Online. Como qualquer outra política no Teams, você pode atribuir TeamsUpgradePolicy diretamente a um usuário. Você também pode definir a política como o padrão de todo o locatário. Qualquer atribuição a um usuário tem precedência sobre a configuração padrão do locatário.  Você pode gerenciar a política no Console de Administração do Teams e no PowerShell.

Você também pode atribuir qualquer modo do TeamsUpgradePolicy, exceto o modo TeamsOnly, aos usuários que estão no Skype for Business no local. **O modo TeamsOnly só** pode ser atribuído a um usuário que já está no Skype for Business Online . Isso acontece porque a interopção com usuários e federação do Skype for Business, bem como a funcionalidade do Sistema de Telefonia do Microsoft 365 só é possível se o usuário estiver no Skype for Business Online. Além disso, não será possível atribuir o modo **TeamsOnly** como o padrão de todo o locatário se você tiver uma implantação local do Skype for Business (que é detectada pela presença de um registro DNS de descoberta lyncdiscover que aponta para um local diferente do Office 365.

Os usuários com contas do Skype for Business no local devem ser movidos [online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (para o Skype for Business Online ou diretamente para o Teams) usando o Move-CsUser no toolset local do Skype for Business. Esses usuários podem ser movidos para o TeamsOnly em 1 ou 2 etapas:

-   1 etapa: Especifique a opção -MoveToTeams em Move-CsUser. Isso requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com CU8 ou posterior.

-   2 etapas: depois de executar Move-CsUser, conceda o modo TeamsOnly ao usuário usando TeamsUpgradePolicy.

Ao contrário de outras políticas, não é possível criar novas instâncias do TeamsUpgradePolicy no Microsoft 365 ou No Office 365. Todas as instâncias existentes são criadas no serviço.  (Observe que o modo é uma propriedade dentro do TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns casos, mas não em todos os casos, o nome da instância da política é o mesmo do modo. Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" do TeamsUpgradePolicy a esse usuário. Para ver uma lista de todas as instâncias, você pode executar o seguinte comando:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para atualizar um usuário local do Skype for Business para o modo TeamsOnly, use Move-CsUser no toolset local:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Para alterar o modo para todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Se você tiver usuários com contas do Skype for Business no local, não poderá atribuir o modo TeamsOnly no nível do locatário. Você deve mover esses usuários individualmente para a nuvem usando Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Usando notificações em clientes do Skype for Business

Os administradores têm a opção de fornecer notificações de usuário final no cliente skype for Business para informar aos usuários que eles serão atualizados em breve para o Teams, conforme mostrado no diagrama a seguir. Por exemplo, uma semana antes de o administrador planeja atualizar um grupo de usuários para o modo TeamsOnly, talvez o administrador queira ativar essas notificações para esse grupo de usuários. Essas notificações são habilitadas usando uma instância do TeamsUpgradePolicy com NotifySfbUsers=true.  Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.  Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers. 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

Se seus usuários estão no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers=true. 

Se seus usuários estão no Skype for Business Server local, você precisará usar o toolset local e precisará do Skype for Business Server 2019 ou cu8 para Skype for Business Server 2015. Para usuários instalados no Skype for Business Server no local, a propriedade mode da instância online do TeamsUpgradePolicy é agraciada, mas a propriedade NotifySfbUsers não é. Se as notificações são desejadas, você deve criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente. 

Na janela local do PowerShell, crie uma nova instância do TeamsUpgradePolicy com NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Em seguida, usando a mesma janela local do PowerShell, atribua essa nova política aos usuários desejados:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migração de reunião

Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões existentes do Skype for Business que organizaram serão convertidas no Teams. Opcionalmente, você pode desabilitar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário. Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para funcionar com a conta de usuário online, mas se você não especificar -MoveToTeams, as reuniões serão migradas como reuniões do Skype for Business, em vez de convertidas no Teams. 

Ao atribuir o modo TeamsOnly no nível do locatário, a migração de reunião não é disparada para nenhum usuário. Se quiser atribuir o modo TeamsOnly ao nível do locatário e migrar reuniões, você pode usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando o Get-CsOnlineUser com quaisquer filtros necessários) e, em seguida, fazer um loop por cada um desses usuários para disparar a migração de reunião usando Start-CsExMeetingMigration. Para obter detalhes, [consulte Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).



## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

