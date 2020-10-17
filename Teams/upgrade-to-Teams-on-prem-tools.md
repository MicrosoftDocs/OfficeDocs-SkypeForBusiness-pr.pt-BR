---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualize o Skype for Business para o Teams – ferramentas para atualização
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
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Ferramentas para a atualização do teams &mdash; para administradores de ti

Este artigo descreve as ferramentas para a atualização para o Microsoft Teams. Este artigo é o terceiro de vários que descrevem os conceitos de atualização e a implementação para administradores de ti.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Ferramentas para gerenciar a atualização**   (este artigo)
- [Considerações adicionais sobre organizações com o Skype for Business no local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar sua atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre PSTN (rede telefônica pública comutada)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência-referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Ferramentas para gerenciar a atualização

Seja qual for o método de atualização que você escolher, para os usuários que já têm o Skype for Business Online, você gerencia a transição para TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário. Para usuários com uma conta local no Skype for Business Server, você também pode usar `Move-CsUser` para [movê-los para a nuvem](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obter mais informações sobre cada um dos modos, consulte [modos de coexistência](migration-interop-guidance-for-teams-with-skype.md).  

Não importa se você executa uma transição de recursos selecionados usando os modos Skype for Business ou simplesmente atualiza para o modo TeamsOnly da configuração de ilhas padrão, TeamsUpgradePolicy é a principal ferramenta para usuários que já têm o Skype for Business online. Como qualquer outra política do Teams, você pode atribuir TeamsUpgradePolicy diretamente a um usuário. Você também pode definir a política como o padrão de todo o locatário. Qualquer atribuição para um usuário tem precedência sobre a configuração padrão do locatário.  Você pode gerenciar a política no console de administração do Teams e no PowerShell.

Você também pode atribuir qualquer modo de TeamsUpgradePolicy, exceto para o modo TeamsOnly, aos usuários hospedados no Skype for Business local. **O modo TeamsOnly só pode ser atribuído a um usuário que já esteja hospedado no Skype for Business online**. Isso ocorre porque a interoperabilidade com os usuários do Skype for Business e a Federação, bem como a funcionalidade do sistema telefônico do Microsoft 365 só é possível se o usuário estiver hospedado no Skype for Business online. Além disso, **você não pode atribuir o modo TeamsOnly como o padrão geral do locatário se tiver uma implantação do Skype for Business local** (que é detectada pela presença de um registro DNS lyncdiscover que aponta para o local diferente do Office 365.

Os usuários com contas do Skype for Business hospedadas no local [devem ser movidos online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (para o Skype for Business online ou direto para o Microsoft Teams) usando Move-CsUser no conjunto de ferramentas local do Skype for Business. Esses usuários podem ser movidos para o TeamsOnly nas etapas 1 ou 2:

-   1 etapa: Especifique a opção-MoveToTeams em move-CsUser. Isso requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com o CU8 ou posterior.

-   2 etapas: após executar move-CsUser, conceda o modo TeamsOnly ao usuário usando TeamsUpgradePolicy.

Ao contrário de outras políticas, não é possível criar novas instâncias de TeamsUpgradePolicy no Microsoft 365 ou no Office 365. Todas as instâncias existentes são incorporadas ao serviço.  (Observe que Mode é uma propriedade dentro de TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns--mas não em todos os casos, o nome da instância da política é o mesmo que o modo. Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" de TeamsUpgradePolicy a esse usuário. Para ver uma lista de todos os casos, você pode executar o seguinte comando:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para atualizar um usuário local do Skype for Business para o modo TeamsOnly, use Move-CsUser no conjunto de ferramentas local:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Para alterar o modo de todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Se você tiver usuários com contas do Skype for Business locais, não será possível atribuir o modo TeamsOnly no nível do locatário. Você deve mover esses usuários individualmente para a nuvem usando move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Usar notificações nos clientes Skype for Business

Os administradores têm a opção de fornecer notificações de usuário final no cliente Skype for Business para informar aos usuários que eles logo serão atualizados para o Microsoft Teams, conforme mostrado no diagrama a seguir. Por exemplo, uma semana antes de o administrador planejar a atualização de um grupo de usuários para o modo TeamsOnly, o administrador pode querer ativar essas notificações para esse grupo de usuários. Essas notificações são habilitadas usando uma instância de TeamsUpgradePolicy com NotifySfbUsers = true.  Para todos os modos diferentes de TeamsOnly, há, na verdade, duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers.  Para todos os modos diferentes de TeamsOnly, há, na verdade, duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers. 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

Se seus usuários estiverem hospedados no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers = verdadeiro. 

Se seus usuários estiverem hospedados no Skype for Business Server no local, você precisará usar o conjunto de ferramentas local e será necessário o Skype for Business Server 2019 ou o CU8 para o Skype for Business Server 2015. Para os usuários hospedados no Skype for Business Server no local, a propriedade Mode da instância online do TeamsUpgradePolicy é respeitada, mas a propriedade NotifySfbUsers não é. Se as notificações forem desejadas, você deve criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente. 

Na janela do PowerShell local, crie uma nova instância de TeamsUpgradePolicy com NotifySfbUsers = verdadeiro:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Em seguida, usando a mesma janela do PowerShell local, atribua essa nova política aos usuários desejados:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migração de reunião

Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões do Skype for Business existentes que eles organizadas serão convertidas para o Microsoft Teams. Opcionalmente, você pode desativar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário. Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para que funcionem com a conta de usuário online, mas se você não especificar-MoveToTeams, as reuniões serão migradas como reuniões do Skype for Business, em vez de serem convertidas para o Microsoft Teams. 

Ao atribuir o modo TeamsOnly no nível do locatário, a migração da reunião não é disparada para nenhum usuário. Se quiser atribuir o modo TeamsOnly no nível do locatário e migrar reuniões, você pode usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando Get-CsOnlineUser com os filtros necessários) e executar um loop por cada um desses usuários para disparar a migração de reunião usando o Start-CsExMeetingMigration. Para obter detalhes, consulte [usando o serviço de migração de reunião (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).



## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

