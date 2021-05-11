---
title: Mover usuários do Skype for Business Server 2019 para Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: saiba como migrar as configurações do usuário e mover os usuários para Teams.'
ms.openlocfilehash: 1d2542d3c5b67e935449b4f6fee60506b9232adc
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306015"
---
# <a name="move-users-from-on-premises-to-teams"></a>Migrar usuários de um ambiente local para o Teams

Quando um usuário é movido do local para o Teams Somente, a Skype for Business do usuário é movida do local para o online e o usuário recebe o TeamsUpgradePolicy com mode=TeamsOnly.  Depois que um usuário é movido do local para o modo TeamsOnly:

- Todas as chamadas de entrada e chats de outros usuários (sejam enviadas de Skype for Business ou Teams), serão enviadas no cliente de Teams do usuário.
- O usuário poderá interoperar com outros usuários que usam Skype for Business (online ou local).
- O usuário poderá se comunicar com usuários em organizações federadas.
- Novas reuniões agendadas por esse usuário são Teams reuniões.
- O usuário ainda pode ingressar em qualquer Skype for Business reuniões.
- As reuniões pré-existentes do usuário agendadas para o futuro serão migradas do local para Teams.
- Os contatos que existiam no local estão disponíveis Teams logo após o usuário fazer logor pela primeira vez.
- Os usuários não podem iniciar chamadas ou chats Skype for Business, nem podem agendar novas reuniões no Skype for Business. Se eles tentarem abrir o Skype for Business cliente, eles serão redirecionados para usar Teams como mostrado abaixo. Se o Teams cliente não estiver instalado, eles serão direcionados para a versão web do Teams usando seu navegador.<br><br>
    ![Redirecionamento de mensagens de um usuário para Teams](../media/go-to-teams-page.png)

Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem. Além disso, revise as diretrizes [de migração](/microsoftteams/migration-interop-guidance-for-teams-with-skype)e interoperabilidade para organizações que Teams em conjunto com Skype for Business .


> [!NOTE]
> O Armazenamento de Contatos Unificados deve ser desabilitado na conta SfB no momento para que o contato seja movido para Teams.


Atualmente, *há dois* métodos para mover um usuário do local para Teams:

- Se você estiver usando uma versão anterior Skype for Business Server 2015 CU8, a movimentação exigirá duas etapas (que podem ser escritas em script para serem feitas em conjunto como uma única etapa, se desejado):
  - [Mova o usuário de Skype for Business Server (local) para Skype for Business Online.](move-users-from-on-premises-to-skype-for-business-online.md)
  - Depois que o usuário for Skype for Business Online, atribua o usuário TeamsUpgradePolicy com mode= TeamsOnly. Para conceder o modo TeamsOnly, execute o seguinte cmdlet de uma janela do PowerShell Skype for Business Online:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Se você tiver ferramentas de administração Skype for Business Server cu8 2015 ou posterior, poderá usar o método acima ou fazer essa movimentação em uma etapa, conforme descrito abaixo. Além disso, você pode, opcionalmente, fornecer uma notificação dentro do cliente Skype for Business antes de 2016 para Teams Somente assim como, opcionalmente, fazer com que o cliente Teams seja baixado silenciosamente pelo cliente Skype for Business.

> [!NOTE]
> Em preparação para a próxima aposentadoria do Skype for Business Online, a Microsoft estará simplificando como as organizações se movem para Teams em um futuro próximo. Ao mover um usuário do local para o Teams, em breve não será mais necessário especificar a opção para mover os usuários diretamente do local para o `-MoveToTeams` `Move-CsUser` TeamsOnly. No momento, se essa opção não for especificada, os usuários transiram da sua residência no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado. Após a reforma, ao mover um usuário do local para a nuvem com , os usuários serão atribuídos automaticamente ao modo TeamsOnly e suas reuniões no local serão convertidas automaticamente em reuniões de Teams, como se o , independentemente de a opção ser `Move-CsUser` `-MoveToTeams switch had been specified` realmente especificada. Esperamos lançar essa funcionalidade antes da aposentadoria real de 31 de julho de 2021.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover um usuário diretamente do Skype for Business local para o Teams Only

As ferramentas de administração locais no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019 Teams, permitem que você mova os usuários do local para o modo Somente em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou o Painel de Controle Skype for Business Server, conforme descrito abaixo.

### <a name="move-to-teams-using-move-csuser"></a>Mover para Teams usando Move-CsUser

Move-CsUser está disponível em uma janela local Skype for Business Shell de Gerenciamento do PowerShell. As etapas abaixo e as permissões necessárias são as mesmas que mover um usuário para o Skype for Business Online, exceto que você também deve especificar a opção MoveToTeams e você deve garantir que o usuário também tenha sido concedido uma licença para Teams (além do Skype for Business Online).

Você deve ter privilégios suficientes no ambiente local e no serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta Microsoft 365 ou Office 365 com a função administrativa `-Credential` necessária.

Para mover um usuário para Teams modo Somente usando Move-CsUser:

- Especifique o usuário para mover usando o `Identity` parâmetro.
- Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".
- Especifique a `MoveToTeams` opção.
- Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365 ou Office 365), use o parâmetro para fornecer uma conta com permissões suficientes no `-credential` Office 365.
- Se a conta com permissões em Microsoft 365 ou Office 365 não terminar em "onmicrosoft. <span> com", você deve especificar o `-HostedMigrationOverrideUrl` parâmetro, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

A sequência de cmdlets a seguir pode ser usada para mover um usuário para o TeamsOnly e assume que a credencial Microsoft 365 ou Office 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Como há circunstâncias diferentes que exigem parâmetros diferentes, o comando padrão para a maioria dos casos é:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover para o Teams usando Skype for Business Server Painel de Controle

1. Abra o aplicativo Skype for Business Server Painel de Controle.
2. Na navegação à esquerda, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover para Teams.
4. Selecione os usuários e, em seguida, na lista suspenso **Ação** acima da lista, escolha Mover usuários selecionados **para** Teams .
5. No assistente, clique em **Próximo**.
6. Se solicitado, entre no Microsoft 365 ou Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notifique Skype for Business usuários locais sobre a próxima movimentação para Teams

As ferramentas de administração locais no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você notifique os usuários locais Skype for Business sobre sua próxima movimentação para Teams. Quando você habilita essas notificações, os usuários verão uma notificação em seu cliente Skype for Business (Win32, Mac, Web e mobile), conforme mostrado abaixo. Se os usuários clicarem no **botão Experimentar,** o Teams cliente será lançado se estiver instalado; caso contrário, os usuários serão navegados para a versão web do Teams em seu navegador. Por padrão, quando as notificações são habilitadas, os clientes do Win32 Skype for Business baixam silenciosamente o cliente Teams para que o cliente rico está disponível antes de mover o usuário para o modo Somente Teams; no entanto, você também pode desabilitar esse comportamento.  As notificações são configuradas usando a versão local de , e o download silencioso para clientes Win32 é controlado por meio do `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet local.

> [!TIP]
> Alguns servidores podem precisar reiniciar para que isso funcione Skype for Business 2015 com CU8.

![Notificação da próxima movimentação para Teams](../media/teams-upgrade-notification.png)

Para notificar os usuários locais de que eles serão atualizados em breve para Teams, crie uma nova instância do TeamsUpgradePolicy com NotifySfBUsers=true. Em seguida, atribua essa política aos usuários que você deseja notificar, atribuindo a política diretamente ao usuário ou definindo a política no site, pool ou nível global. Os cmdlets a seguir criam e concedem uma política no nível do usuário:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

O download automático do Teams por meio do cliente Skype for Business Win32 é controlado por meio do cmdlet TeamsUpgradeConfiguration local com o parâmetro DownloadTeams. Você cria essa configuração em um nível global, de site e de pool. Por exemplo, o comando a seguir cria a configuração do site Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Por padrão, o valor de DownloadTeams é True; no entanto, ele só *será* honrado se NotifySfbUser = True para um determinado usuário.

## <a name="see-also"></a>Também consulte

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistência com o Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
