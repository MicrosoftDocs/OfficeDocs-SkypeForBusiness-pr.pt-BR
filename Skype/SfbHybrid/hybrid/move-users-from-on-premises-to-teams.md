---
title: Mover usuários do Skype for Business Server 2019 para o Teams
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
description: 'Resumo: saiba como migrar as configurações do usuário e mover os usuários para o Teams.'
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836978"
---
# <a name="move-users-from-on-premises-to-teams"></a>Migrar usuários de um ambiente local para o Teams

Quando um usuário é movido do local apenas para o Teams, a casa do Skype for Business do usuário é movida do local para o online e o usuário recebe o TeamsUpgradePolicy com mode=TeamsOnly.  Depois que um usuário é movido do local para o modo TeamsOnly:

- Todas as chamadas de entrada e chats de outros usuários (sejam enviadas do Skype for Business ou do Teams), serão recebidas no cliente do Teams do usuário.
- O usuário poderá interoperar com outros usuários que usam o Skype for Business (online ou local).
- O usuário poderá se comunicar com usuários em organizações federadas.
- Novas reuniões agendadas por esse usuário são reuniões do Teams.
- O usuário ainda pode ingressar em qualquer reunião do Skype for Business.
- As reuniões pré-existentes do usuário agendadas para o futuro serão migradas do local para o Teams.
- Os contatos que existiam no local estão disponíveis no Teams logo após o usuário fazer logor pela primeira vez.
- Os usuários não podem iniciar chamadas ou chats do Skype for Business, nem agendar novas reuniões no Skype for Business. Se eles tentarem abrir o cliente skype for Business, eles serão redirecionados para usar o Teams, conforme mostrado abaixo. Se o cliente do Teams não estiver instalado, ele será direcionado para a versão da Web do Teams usando seu navegador.<br><br>
    ![Redirecionamento de mensagens de um usuário para o Teams](../media/go-to-teams-page.png)

Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem. Também revise as diretrizes de migração e interoperabilidade para organizações [que usam o Teams juntamente com o Skype for Business.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> O Armazenamento de Contatos Unificados deve ser desabilitado na conta SfB no momento para que o contato seja movido para o Teams.


Há dois métodos para mover um usuário local para o Teams:

- Se você estiver usando uma versão anterior à CU8 do Skype for Business Server 2015, a movimentação exigirá duas etapas (que podem ser feitas em script como uma única etapa, se desejado):
  - [Mover o usuário do Skype for Business Server (local) para o Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Depois que o usuário for instalado no Skype for Business Online, atribua o usuário TeamsUpgradePolicy com mode= TeamsOnly. Para conceder o modo TeamsOnly, execute o seguinte cmdlet de uma janela do PowerShell do Skype for Business Online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Se você tiver ferramentas de administração do Skype for Business Server 2015 CU8 ou posterior, poderá usar o método acima ou pode fazer essa movimentação em uma etapa, conforme descrito abaixo. Além disso, você pode, opcionalmente, fornecer uma notificação dentro do cliente skype for Business antes de mudo para o Teams Somente, bem como, opcionalmente, fazer com que o cliente do Teams seja baixado silenciosamente pelo cliente skype for Business.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover um usuário diretamente do Skype for Business local para o Teams Only

As ferramentas de administração locais no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você mova os usuários do local para o modo Somente do Teams em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou o Painel de Controle do Skype for Business Server, conforme descrito abaixo.

### <a name="move-to-teams-using-move-csuser"></a>Mover para o Teams usando Move-CsUser

Move-CsUser está disponível em uma janela local do Shell de Gerenciamento do Skype for Business PowerShell. As etapas abaixo e as permissões necessárias são as mesmas que mover um usuário para o Skype for Business Online, exceto que você também deve especificar a opção MoveToTeams e você deve garantir que o usuário também tenha sido concedido uma licença para o Teams (além do Skype for Business Online).

Você deve ter privilégios suficientes no ambiente local e no serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela do Shell de Gerenciamento do Skype for Business Server local com credenciais locais e usar o parâmetro para especificar credenciais para uma conta do `-Credential` Microsoft 365 ou office 365 com a função administrativa necessária.

Para mover um usuário para o modo Somente do Teams usando Move-CsUser:

- Especifique o usuário para mover usando o `Identity` parâmetro.
- Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".
- Especifique a `MoveToTeams` opção.
- Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365 ou Office 365), use o parâmetro para fornecer uma conta com permissões suficientes no `-credential` Office 365.
- Se a conta com permissões no Microsoft 365 ou Office 365 não terminar em "onmicrosoft. <span> com", você deve especificar o `-HostedMigrationOverrideUrl` parâmetro, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

A sequência de cmdlets a seguir pode ser usada para mover um usuário para o TeamsOnly e presume que a credencial do Microsoft 365 ou office 365 seja uma conta separada e fornecida como entrada para o prompt Get-Credential.

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

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover para o Teams usando o Painel de Controle do Skype for Business Server

1. Abra o aplicativo Painel de Controle do Skype for Business Server.
2. Na navegação à esquerda, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover para o Teams.
4. Selecione os usuários e, em seguida, na lista suspenso **Ação** acima da lista, escolha **Mover usuários selecionados para o Teams**.
5. No assistente, clique em **Próximo**.
6. Se solicitado, entre no Microsoft 365 ou Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar os usuários locais do Skype for Business sobre a próxima movimentação para o Teams

As ferramentas de administração locais no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você notifique os usuários locais do Skype for Business sobre sua próxima mudança para o Teams. Quando você habilita essas notificações, os usuários verão uma notificação em seu cliente do Skype for Business (Win32, Mac, Web e celular), conforme mostrado abaixo. Se os usuários clicarem **no botão Experimentar,** o cliente do Teams será lançado se estiver instalado; caso contrário, os usuários serão navegados para a versão da Web do Teams em seu navegador. Por padrão, quando as notificações são habilitadas, os clientes do Skype for Business Win32 baixam silenciosamente o cliente do Teams para que o cliente rich está disponível antes de mover o usuário para o modo Somente equipes; no entanto, você também pode desabilitar esse comportamento.  As notificações são configuradas usando a versão local de , e o download silencioso para clientes Win32 é controlado por meio do `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet local.

> [!TIP]
> Alguns servidores podem precisar reiniciar para que isso funcione no Skype for Business 2015 com CU8.

![Notificação da próxima movimentação para o Teams](../media/teams-upgrade-notification.png)

Para notificar os usuários locais de que eles serão atualizados em breve para o Teams, crie uma nova instância do TeamsUpgradePolicy com NotifySfBUsers=true. Em seguida, atribua essa política aos usuários que você deseja notificar, atribuindo a política diretamente ao usuário ou definindo a política no site, pool ou nível global. Os cmdlets a seguir criam e concedem uma política no nível do usuário:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

O download automático do Teams por meio do cliente Do Skype for Business Win32 é controlado por meio do cmdlet TeamsUpgradeConfiguration local com o parâmetro DownloadTeams. Você cria essa configuração em um nível global, de site e de pool. Por exemplo, o comando a seguir cria a configuração do site Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Por padrão, o valor de DownloadTeams é True; no entanto, ele só *será* honrado se NotifySfbUser = True para um determinado usuário.

## <a name="see-also"></a>Confira também

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistência com o Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
