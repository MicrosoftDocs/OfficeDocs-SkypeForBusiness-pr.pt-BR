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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.custom: ''
description: 'Resumo: saiba como migrar as configurações do usuário e mover os usuários para o Teams.'
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705840"
---
# <a name="move-users-from-on-premises-to-teams"></a>Migrar usuários de um ambiente local para o Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Quando um usuário é movido do local apenas para o Teams, a página inicial do Skype for Business do usuário é movida do local para online e o usuário recebe o TeamsUpgradePolicy com mode=TeamsOnly.  Depois que um usuário é movido do local para o modo TeamsOnly:

- Todas as chamadas de entrada e chats de outros usuários (sejam enviadas do Skype for Business ou do Teams), serão enviadas no cliente de Teams do usuário.
- O usuário poderá interoperar com outros usuários que usam o Skype for Business (seja online ou local).
- O usuário poderá se comunicar com usuários em organizações federadas.
- Novas reuniões agendadas por esse usuário são reuniões do Teams.
- O usuário ainda pode ingressar em qualquer reunião do Skype for Business. No entanto, a partir de outubro de 2022, os usuários do TeamsOnly em organizações híbridas só poderão ingressar Skype for Business reuniões anonimamente. Para obter detalhes, confira [o que esperar após a desativação](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement).
- As reuniões pré-existentes do usuário agendadas para o futuro serão migradas do local para o Teams.
- Os contatos que existiam no local estão disponíveis no Teams logo após o usuário fazer logon pela primeira vez.
- Os usuários não podem iniciar chamadas ou chats Skype for Business, nem agendar novas reuniões no Skype for Business. Se eles tentarem abrir o Skype for Business cliente, eles serão redirecionados para usar o Teams, conforme mostrado abaixo. Se o cliente do Teams não estiver instalado, ele será direcionado para a versão da Web do Teams usando seu navegador.<br><br>
    ![Mensagem redirecionando um usuário para o Teams.](../media/go-to-teams-page.png)

Antes de mover todos os usuários, examine os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem. Examine também as diretrizes [de migração e interoperabilidade para organizações que usam o Teams junto com Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> O Repositório unificado de Contatos deve ser desabilitado na conta SfB local para que o contato seja movido para o Teams.

> [!IMPORTANT]
>
> - Ao mover um usuário do local para a nuvem com Move-CsUser, os usuários são atribuídos automaticamente ao modo TeamsOnly e suas reuniões do local são convertidas automaticamente em reuniões do Teams, `-MoveToTeams` independentemente de a opção ser realmente especificada. (Isso inclui migrações do Lync Server 2013, que nunca tiveram a opção`-MoveToTeams`.)  Anteriormente, se essa opção não fosse especificada, os usuários iam de ser hospedados no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado. Isso foi alterado na preparação para a desativação do Skype for Business Online.
> - Mover usuários entre sua implantação local e o Teams agora requer  versões mínimas atualizadas dos componentes locais, como o Skype for Business Server ou o Lync Server, que não depende mais da infraestrutura herdada do Skype for Business Online. Para obter detalhes [, consulte Pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites).

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover um usuário diretamente do Skype for Business local apenas para o Teams

As ferramentas de administração locais no Skype for Business Server e no Lync Server 2013 permitem que você mova usuários do local para o modo TeamsOnly em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou no Skype for Business Server Painel de Controle, conforme descrito abaixo. Não é mais `-MoveToTeams` necessário especificar a opção e o comportamento para mover-se diretamente do local para o Teams somente agora é automático, independentemente de qual versão do Skype for Business Server ou do Lync Server é usada. 

Você deve ter privilégios suficientes no ambiente local e no serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em Credenciais [administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou iniciar uma janela local do Shell `-Credential` de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para um Microsoft 365 com a função administrativa necessária.

Além disso, você deve garantir que o usuário recebeu uma licença para o Teams (além do Skype for Business Online). Não desabilite a licença Skype for Business Online.

### <a name="move-to-teams-using-move-csuser"></a>Mover para o Teams usando Move-CsUser

Move-CsUser está disponível em uma janela local do PowerShell do Shell de Gerenciamento do Skype for Business Server ou em uma janela do PowerShell do Shell de Gerenciamento do Lync Server. Para mover um usuário para o modo TeamsOnly usando Move-CsUser:
- Especifique o usuário a ser movido usando o `Identity` parâmetro.
- Especifique `-Target` o parâmetro com o valor "sipfed.online.lync.<span> com" (ou valor semelhante se seu locatário for uma nuvem governamental).
- Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365), use `-credential` o parâmetro para fornecer uma conta com permissões suficientes no Microsoft 365.
- Se a conta com permissões no Microsoft 365 não terminar em "onmicrosoft."<span> com", você deve especificar o parâmetro `-HostedMigrationOverrideUrl` , com o valor correto, conforme descrito em [Credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).
- Verifique se o computador que executa as ferramentas de administração local está usando a cu mais recente para sua versão do Skype for Business Server ou do Lync Server 2013, para garantir que o OAuth seja usado para autenticação. 

A sequência de cmdlets a seguir pode ser usada para mover um usuário para o TeamsOnly e pressupõe que a credencial do Microsoft 365 é uma conta separada e fornecida como entrada para o prompt de Get-Credential. O comportamento é o mesmo, independentemente `-MoveToTeams` de a opção ser especificada ou não.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Como há circunstâncias diferentes que exigem parâmetros diferentes, o comando padrão para a maioria dos casos é:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover para o Teams usando o Painel de Controle do Skype for Business Server

1. Abra o Skype for Business Server Painel de Controle aplicativo.
2. No painel de navegação esquerdo, escolha **Usuários**.
3. Use **Procurar** para localizar os usuários que você deseja mover para o Teams.
4. Selecione os usuários e, em seguida, na lista suspensa **Ação** acima da lista, escolha **Mover os usuários selecionados para o Teams** ou **Mover os usuários selecionados para o Skype for Business Online**.   Uma das opções agora move os usuários diretamente para o TeamsOnly.
5. No assistente, clique em **Avançar**.
6. Se solicitado, entre no Microsoft 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique em **Avançar** e, em seguida, **Avançar** mais uma vez para mover o usuário.
8. As mensagens de status relacionadas a êxito ou falha são fornecidas na parte superior do aplicativo Painel de Controle principal, não no assistente.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notifique Skype for Business usuários locais sobre a próxima mudança para o Teams

As ferramentas de administração locais no Skype for Business Server 2015 com CU8 e, no Skype for Business Server 2019, permitem que você notifique os usuários locais Skype for Business sobre sua próxima mudança para o Teams. Quando você habilitar essas notificações, os usuários verão uma notificação no cliente Skype for Business (Win32, Mac, Web e móvel), conforme mostrado abaixo. Se os usuários **clicarem no botão** Experimentar, o cliente do Teams será iniciado se ele estiver instalado; caso contrário, os usuários serão navegados para a versão da Web do Teams em seu navegador. Por padrão, quando as notificações são habilitadas, os clientes win32 Skype for Business baixam silenciosamente o cliente do Teams para que o cliente avançado esteja disponível antes de mover o usuário para o modo TeamsOnly. No entanto, você também pode desabilitar esse comportamento.  As notificações são configuradas usando a `TeamsUpgradePolicy`versão local do , e o download silencioso para clientes Win32 `TeamsUpgradeConfiguration` é controlado por meio do cmdlet local.


![Notificação de mudança futura para o Teams.](../media/teams-upgrade-notification.png)

Para notificar os usuários locais de que eles serão atualizados em breve para o Teams, crie uma nova instância do TeamsUpgradePolicy com NotifySfBUsers=true. Em seguida, atribua essa política aos usuários que você deseja notificar, seja atribuindo a política diretamente ao usuário ou definindo a política no nível do site, pool ou global. Os cmdlets a seguir criam e concedem uma política de nível de usuário:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

O download automático do Teams por meio do cliente Skype for Business Win32 é controlado por meio do cmdlet TeamsUpgradeConfiguration local com o parâmetro DownloadTeams. Você cria essa configuração em um nível global, de site e de pool. Por exemplo, o comando a seguir cria a configuração para o site Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Por padrão, o valor de DownloadTeams é True; no entanto, ele só *será* respeitado se NotifySfbUser = True para um determinado usuário.

## <a name="see-also"></a>Confira também

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistência com o Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
