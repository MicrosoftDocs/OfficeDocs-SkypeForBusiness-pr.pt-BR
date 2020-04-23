---
title: Mover usuários do Skype for Business Server 2019 para o Microsoft Teams
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
description: 'Resumo: saiba como migrar configurações de usuário e mover usuários para o Microsoft Teams.'
ms.openlocfilehash: 07d0657017d24acbbd3961c3528056debb927a5a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779677"
---
# <a name="move-users-from-on-premises-to-teams"></a>Migrar usuários de um ambiente local para o Teams

Quando um usuário é movido de local somente para o Microsoft Teams, a home page do Skype for Business do usuário é movida de local para online e o usuário recebe TeamsUpgradePolicy com modo = TeamsOnly.  Após um usuário ser movido do modo local para o TeamsOnly:

- Todas as chamadas de entrada e chats de outros usuários (sejam enviados do Skype for Business ou do Microsoft Teams) vão para o cliente do Microsoft Teams.
- O usuário poderá interoperar com outros usuários que usam o Skype for Business (seja online ou localmente).
- O usuário poderá se comunicar com os usuários em organizações federadas.
- Novas reuniões agendadas por esse usuário são reuniões do teams.
- O usuário ainda pode participar de qualquer reunião do Skype for Business.
- As reuniões preexistentes do usuário agendadas para o futuro serão migradas do no local para o Microsoft Teams.
- Contatos que existiam no local estão disponíveis no Teams logo após o logon do usuário pela primeira vez.
- Os usuários não podem iniciar chamadas ou chats do Skype for Business, nem podem agendar novas reuniões no Skype for Business. Se ele tentar abrir o cliente Skype for Business, ele será redirecionado para usar o Microsoft Teams, como mostrado abaixo. Se o cliente do Teams não estiver instalado, ele será direcionado para a versão da Web do teams usando o navegador.<br><br>
    ![Mensagem redirecionando um usuário para o Microsoft Teams](../media/go-to-teams-page.png)

Antes de mover qualquer usuário, leia os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem. Além disso, certifique-se de revisar a [orientação de migração e de interoperabilidade para organizações que usam o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> O repositório unificado de contatos deve ser desabilitado na conta local do SfB para que o contato seja movido para o Microsoft Teams.


Há dois métodos para mover um usuário de local para o Microsoft Teams:

- Se você estiver usando uma versão anterior ao Skype for Business Server 2015 CU8, a movimentação exigirá duas etapas (que podem ser executadas em script para serem realizadas juntas como uma única etapa, se desejado):
  - [Mover o usuário do Skype for Business Server (local) para o Skype for Business online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Depois que o usuário estiver hospedado no Skype for Business Online, atribua o usuário TeamsUpgradePolicy com o modo = TeamsOnly. Para conceder o modo TeamsOnly, execute o seguinte cmdlet em uma janela do PowerShell do Skype for Business Online:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Se você tem ferramentas de administração do Skype for Business Server 2015 CU8 ou posterior, você pode usar o método acima ou pode fazer essa movimentação em uma etapa, conforme descrito abaixo. Além disso, você pode, opcionalmente, fornecer uma notificação no cliente Skype for Business antes de movê-las para o Microsoft Teams e, opcionalmente, fazer com que o cliente do teams seja baixado silenciosamente pelo cliente Skype for Business.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover um usuário diretamente do Skype for Business no local para o Microsoft Teams

As ferramentas administrativas locais no Skype for Business Server 2015 com o CU8, bem como no Skype for Business Server 2019, permitem que você mova usuários do modo local para o Microsoft Teams em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou o painel de controle do Skype for Business Server, conforme descrito abaixo.

### <a name="move-to-teams-using-move-csuser"></a>Mover para o Microsoft Teams usando move-CsUser

O move-CsUser está disponível em uma janela do PowerShell do Shell de gerenciamento do Skype for Business local. As etapas abaixo e as permissões necessárias são as mesmas que mover um usuário para o Skype for Business Online, exceto que você também deve especificar a opção MoveToTeams e deve garantir que o usuário também tenha recebido uma licença para o Microsoft Teams (além do Skype for Business online).

Você deve ter privilégios suficientes no ambiente local e na organização do Office 365, conforme descrito em [credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de gerenciamento do Skype for Business Server com credenciais locais e usar o `-Credential` parâmetro para especificar credenciais para uma conta do Office 365 com a função administrativa necessária do Office 365.

Para mover um usuário para o modo somente do Microsoft Teams usando o move-CsUser:

- Especifique o usuário a ser movido usando `Identity` o parâmetro.
- Especifique o parâmetro-Target com o valor "sipfed. online. Lync. <span>com ".
- Especifique a `MoveToTeams` opção.
- Se você não tiver uma conta com permissões suficientes no local e no Office 365, use o `-credential` parâmetro para fornecer uma conta com permissões suficientes no Office 365.
- Se a conta com permissões no Office 365 não termina em "onmicrosoft. <span>com ", você deve especificar o `-HostedMigrationOverrideUrl` parâmetro com o valor correto, conforme descrito em [credenciais administrativas obrigatórias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

A sequência de cmdlet a seguir pode ser usada para mover um usuário para o TeamsOnly e pressupõe que a credencial do Office 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover para o Microsoft Teams usando o painel de controle do Skype for Business Server

1. Abra o aplicativo painel de controle do Skype for Business Server.
2. Na navegação à esquerda, escolha **usuários**.
3. Use **Localizar** para localizar o (s) usuário (s) que você gostaria de migrar para o Microsoft Teams.
4. Selecione o (s) usuário (s) e, no menu suspenso **ação** acima da lista, escolha **mover usuários selecionados para o Microsoft Teams**.
5. No assistente, clique em **Avançar**.
6. Se solicitado, entre no Office 365, com uma conta que termina em. onmicrosoft.com e tem permissões suficientes.
7. Clique em **Avançar**e, em seguida, **mais uma vez** para mover o usuário.
8. Observe que as mensagens de status referentes a sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, e não no assistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar os usuários locais do Skype for Business sobre o futuro migrar para o Microsoft Teams

As ferramentas de administração local no Skype for Business Server 2015 com o CU8, bem como no Skype for Business Server 2019, permitem notificar os usuários do Skype for Business no local de suas futuras movimentações para o Microsoft Teams. Ao habilitar essas notificações, os usuários verão uma notificação em seu cliente Skype for Business (Win32, Mac, Web e celular), conforme mostrado abaixo. Se os usuários clicarem no botão **testar** , o cliente do Microsoft Teams será iniciado se estiver instalado; caso contrário, os usuários serão acessados para a versão Web do teams no navegador. Por padrão, quando as notificações são habilitadas, os clientes do Win32 Skype for Business baixam silenciosamente o cliente do teams para que o cliente avançado fique disponível antes de mover o usuário para o modo somente do Microsoft Teams; no entanto, você também pode desabilitar esse comportamento.  As notificações são configuradas usando a versão local `TeamsUpgradePolicy`do e o download silencioso para clientes Win32 é controlado por meio do cmdlet `TeamsUpgradeConfiguration` local.

> [!TIP]
> Talvez seja necessário reinicializar alguns servidores para que isso funcione no Skype for Business 2015 com o CU8.

![Notificação de mudança futura para o Teams](../media/teams-upgrade-notification.png)

Para notificar os usuários locais em breve que eles serão atualizados para o Microsoft Teams, crie uma nova instância do TeamsUpgradePolicy com NotifySfBUsers = true. Em seguida, atribua a política aos usuários que você deseja notificar, atribuindo a política diretamente ao usuário ou configurando a política no site, no pool ou no nível global. Os cmdlets a seguir criam e concedem uma política de nível de usuário:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

O download automático do teams via cliente Win32 do Skype for Business é controlado por meio do cmdlet TeamsUpgradeConfiguration no local com o parâmetro DownloadTeams. Você cria essa configuração em um nível global, de site e de pool. Por exemplo, o comando a seguir cria a configuração para o site Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Por padrão, o valor de DownloadTeams é true; no entanto, *só* será atendida se NotifySfbUser = true para um determinado usuário.

## <a name="see-also"></a>Confira também

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistência com o Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
