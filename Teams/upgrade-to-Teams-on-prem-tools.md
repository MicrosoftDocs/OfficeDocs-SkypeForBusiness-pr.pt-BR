---
title: Atualizar para o Teams a partir de uma implantação local do Skype for Business – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualizar do Skype for Business para o Teams – ferramentas para atualização
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952214d615b62d0175841e2c7b24b45f1ae2d2b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533568"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Ferramentas para atualizar para o Teams &mdash; para administradores de IT

Este artigo descreve as ferramentas para atualizar para o Teams. Este artigo é o terceiro de vários que descrevem conceitos de atualização e implementação para administradores de IT.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Ferramentas para gerenciar sua atualização**   (este artigo)
- [Considerações adicionais para organizações com o Skype for Business local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar sua atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre A Rede Telefônica Pública Comutado (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência do Teams e do Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Ferramentas para gerenciar a atualização

Seja qual for o método de atualização escolhido, para usuários que já têm o Skype for Business Online, você gerencia a transição para o TeamsOnly usando o [TeamsUpgradePolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)que controla o modo de coexistência do usuário. Para usuários com uma conta local no Skype for Business Server, você também os usa para `Move-CsUser` [movê-los para a nuvem.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Para obter mais informações sobre cada um dos modos, consulte [os modos de coexistência.](migration-interop-guidance-for-teams-with-skype.md)  

Se você executar uma transição de recursos de seleção usando os modos do Skype for Business ou simplesmente atualizar para o modo TeamsOnly a partir da configuração padrão das Ilhas, o TeamsUpgradePolicy é a ferramenta principal para usuários que já têm o Skype for Business Online. Como qualquer outra política no Teams, você pode atribuir o TeamsUpgradePolicy diretamente a um usuário. Você também pode definir a política como padrão em todo o locatário. Qualquer atribuição a um usuário tem precedência sobre a configuração padrão do locatário.  Você pode gerenciar a política no Console de Administração do Teams e no PowerShell.

Você também pode atribuir qualquer modo do TeamsUpgradePolicy, exceto o modo TeamsOnly, aos usuários do Skype for Business local. **O modo TeamsOnly só pode ser atribuído a** um usuário que já está instalado no Skype for Business Online. Isso acontece porque a interopção com usuários e a federação do Skype for Business, bem como com a funcionalidade do Sistema de Telefonia do Microsoft 365 só é possível se o usuário estiver no Skype for Business Online. Além disso, você não poderá atribuir o modo **TeamsOnly** como o padrão de todo o locatário se tiver uma implantação local do Skype for Business (que é detectada pela presença de um registro DNS de descoberta lyncdiscover que aponta para um local diferente do Office 365.

Os usuários com contas do Skype for Business no local devem ser movidos [online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (para o Skype for Business Online ou diretamente para o Teams) usando o Move-CsUser no aplicativo de ferramentas locais do Skype for Business. Esses usuários podem ser movidos para o TeamsOnly em 1 ou 2 etapas:

-   1 etapa: Especifique a opção -MoveToTeams no Move-CsUser. Isso requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com CU8 ou posterior.

-   2 etapas: Depois de executar o Move-CsUser, conceda o modo TeamsOnly ao usuário usando o TeamsUpgradePolicy.

Ao contrário de outras políticas, não é possível criar novas instâncias do TeamsUpgradePolicy no Microsoft 365 ou no Office 365. Todas as instâncias existentes são criadas no serviço.  (Observe que o modo é uma propriedade dentro do TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns casos, mas não em todos, o nome da instância da política é o mesmo que o modo. Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" do TeamsUpgradePolicy a esse usuário. Para ver uma lista de todas as instâncias, execute o seguinte comando:

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

Para alterar o modo de todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Se você tiver usuários com contas do Skype for Business no local, não poderá atribuir o modo TeamsOnly no nível do locatário. Você deve mover esses usuários individualmente para a nuvem usando o Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Usando notificações em clientes do Skype for Business

Os administradores têm a opção de fornecer notificações do usuário final no cliente Skype for Business para informar aos usuários que eles serão atualizados em breve para o Teams, conforme mostrado no diagrama a seguir. Por exemplo, uma semana antes do administrador planeja atualizar um grupo de usuários para o modo TeamsOnly, o administrador pode querer ativar essas notificações para esse grupo de usuários. Essas notificações são habilitadas usando uma instância do TeamsUpgradePolicy com NotifySfbUsers=true.  Para todos os modos diferentes do TeamsOnly, na verdade há duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers.  Para todos os modos diferentes do TeamsOnly, na verdade há duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers. 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

Se os usuários estão no Skype for Business Online, basta atribuir a instância de política que tem o mesmo modo que o usuário, mas com NotifySfbUsers=true. 

Se os usuários estão instalados no Skype for Business Server local, você precisará usar o toolset local e o Skype for Business Server 2019 ou CU8 para Skype for Business Server 2015. Para usuários instalados no Skype for Business Server local, a propriedade de modo da instância online do TeamsUpgradePolicy é uma honra, mas a propriedade NotifySfbUsers não é. Se as notificações desejarem, você deverá criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente. 

Na janela local do PowerShell, crie uma nova instância do TeamsUpgradePolicy com NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Em seguida, usando a mesma janela local do PowerShell, atribua essa nova política aos usuários desejados:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migração de reunião

Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões existentes do Skype for Business que eles organizaram serão convertidas no Teams. Opcionalmente, você pode desabilitar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário. Ao migrar usuários do local, as reuniões devem ser migradas para a nuvem para funcionar com a conta de usuário online, mas se você não especificar -MoveToTeams, as reuniões serão migradas como reuniões do Skype for Business, em vez de convertidas no Teams. 

Ao atribuir o modo TeamsOnly no nível do locatário, a migração de reunião não é disparada para os usuários. Se quiser atribuir o modo TeamsOnly no nível do locatário e migrar reuniões, você pode usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando o Get-CsOnlineUser com quaisquer filtros necessários) e, em seguida, fazer loop em cada um desses usuários para disparar a migração de reunião usando Start-CsExMeetingMigration. Para obter detalhes, [consulte Usando o MMS (Meeting Migration Service).](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

