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
ms.openlocfilehash: 49763d7674946eb179188554326863f4860252c3
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130642"
---
# <a name="move-users-from-on-premises-to-teams"></a>Migrar usuários de um ambiente local para o Teams

Quando um usuário é movido do local para o Teams Only, a página pagina do Skype for Business do usuário é movida de local para online e o usuário é atribuído teamsUpgradePolicy com mode=TeamsOnly.  Depois que um usuário é movido do local para o modo TeamsOnly:

- Todas as chamadas e chats de entrada de outros usuários (sejam enviados do Skype for Business ou do Teams) serão recebidos no cliente do Teams do usuário.
- O usuário poderá interoperar com outros usuários que usam o Skype for Business (online ou no local).
- O usuário poderá se comunicar com usuários em organizações federadas.
- Novas reuniões agendadas por esse usuário são reuniões do Teams.
- O usuário ainda pode ingressar em qualquer reunião do Skype for Business.
- As reuniões pré-existentes do usuário agendadas para o futuro serão migradas do local para o Teams.
- Os contatos existentes no local estarão disponíveis no Teams logo após o usuário fazer logor pela primeira vez.
- Os usuários não podem iniciar chamadas ou chats do Skype for Business, nem agendar novas reuniões no Skype for Business. Se eles tentarem abrir o cliente Skype for Business, serão redirecionados para usar o Teams, conforme mostrado abaixo. Se o cliente do Teams não estiver instalado, ele será direcionado para a versão web do Teams usando seu navegador.<br><br>
    ![Mensagem redirecionando um usuário para o Teams](../media/go-to-teams-page.png)

Antes de mover todos os usuários, certifique-se de revisar os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem. Certifique-se também de revisar as [orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> O Armazenamento unificado de Contatos deve ser desabilitado na conta SfB no locais para que o contato seja movido para o Teams.


Há dois métodos para mover um usuário do local para o Teams:

- Se você estiver usando uma versão anterior à cu8 do Skype for Business Server 2015, a movimentação exigirá duas etapas (que podem ser escritas em script para serem feitas juntas como uma única etapa, se desejado):
  - [Mova o usuário do Skype for Business Server (local)](move-users-from-on-premises-to-skype-for-business-online.md)para o Skype for Business Online.
  - Depois que o usuário está no Skype for Business Online, atribua o usuário TeamsUpgradePolicy com mode= TeamsOnly. Para conceder o modo TeamsOnly, execute o seguinte cmdlet em uma janela do PowerShell do Skype for Business Online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Se você tiver ferramentas de administração do Skype for Business Server 2015 CU8 ou posterior, poderá usar o método acima ou pode fazer essa movimentação em uma etapa, conforme descrito abaixo. Além disso, opcionalmente, você pode fornecer uma notificação no cliente Skype for Business antes de muda-las para o Teams Only, bem como, opcionalmente, fazer com que o cliente do Teams seja baixado silenciosamente pelo cliente Skype for Business.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover um usuário diretamente do Skype for Business local para o Teams Only

As ferramentas de administração local no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você mova os usuários do local para o modo Teams Only em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou no Painel de Controle do Skype for Business Server, conforme descrito abaixo.

### <a name="move-to-teams-using-move-csuser"></a>Mover para o Teams usando o Move-CsUser

Move-CsUser está disponível em uma janela do PowerShell do Shell de Gerenciamento do Skype for Business local. As etapas abaixo e as permissões necessárias são as mesmas que mover um usuário para o Skype for Business Online, exceto que você também deve especificar a opção MoveToTeams e deve garantir que o usuário também recebeu uma licença para o Teams (além do Skype for Business Online).

Você deve ter privilégios suficientes no ambiente local e no serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em Credenciais [administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Você pode usar uma única conta com privilégios em ambos os ambientes ou iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta do `-Credential` Microsoft 365 ou office 365 com a função administrativa necessária.

Para mover um usuário para o modo Teams Only usando Move-CsUser:

- Especifique o usuário para mover usando o `Identity` parâmetro.
- Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".
- Especifique a `MoveToTeams` opção.
- Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365 ou Office 365), use o parâmetro para fornecer uma conta com permissões suficientes no `-credential` Office 365.
- Se a conta com permissões no Microsoft 365 ou no Office 365 não terminar no "onmicrosoft. <span> com", você deve especificar o `-HostedMigrationOverrideUrl` parâmetro, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

A sequência de cmdlets a seguir pode ser usada para mover um usuário para o TeamsOnly e presume que a credencial do Microsoft 365 ou Office 365 seja uma conta separada e fornecida como entrada para o prompt Get-Credential.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover para o Teams usando o Painel de Controle do Skype for Business Server

1. Abra o aplicativo Painel de Controle do Skype for Business Server.
2. No painel de navegação esquerdo, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover para o Teams.
4. Selecione os usuários e, em seguida, no **menu** suspenso Ação acima da lista, escolha Mover **usuários selecionados para o Teams.**
5. No assistente, clique em **Próximo.**
6. Se solicitado, entre no Microsoft 365 ou no Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em Avançar** e em **Avançar** mais uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo do Painel de Controle principal, não no assistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar os usuários locais do Skype for Business sobre a mudança futura para o Teams

As ferramentas de administração local no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você notifique os usuários locais do Skype for Business sobre sua próxima mudança para o Teams. Quando você habilitar essas notificações, os usuários verão uma notificação no cliente do Skype for Business (Win32, Mac, Web e dispositivos móveis), conforme mostrado abaixo. Se os usuários clicarem **no** botão Experimentar, o cliente do Teams será lançado se estiver instalado; Caso contrário, os usuários serão navegados para a versão web do Teams em seu navegador. Por padrão, quando as notificações são habilitadas, os clientes win32 Skype for Business baixam silenciosamente o cliente do Teams para que o cliente rico está disponível antes de mover o usuário para o modo Teams Only; no entanto, você também pode desabilitar esse comportamento.  As notificações são configuradas usando a versão local do e o download silencioso para clientes Win32 é controlado por meio do `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet local.

> [!TIP]
> Alguns servidores talvez precisem reiniciar para que isso funcione no Skype for Business 2015 com CU8.

![Notificação de mudança futura para o Teams](../media/teams-upgrade-notification.png)

Para notificar os usuários locais de que eles serão atualizados para o Teams em breve, crie uma nova instância do TeamsUpgradePolicy com NotifySfBUsers=true. Em seguida, atribua essa política aos usuários que você deseja notificar, atribuindo a política diretamente ao usuário ou definindo a política no nível do site, pool ou global. Os seguintes cmdlets criam e concedem uma política de nível de usuário:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

O download automático do Teams por meio do cliente Win32 do Skype for Business é controlado por meio do cmdlet TeamsUpgradeConfiguration local com o parâmetro DownloadTeams. Você cria essa configuração em nível global, de site e de pool. Por exemplo, o seguinte comando cria a configuração para o site Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Por padrão, o valor de DownloadTeams é True; no entanto, ele *só será* acadado se NotifySfbUser = True para um determinado usuário.

## <a name="see-also"></a>Confira também

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistência com o Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
