---
title: Mover os usuários no local para equipes
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumo: Saiba como migrar configurações do usuário e movam usuários às equipes.'
ms.openlocfilehash: 6bee0562b38ce3119306e23b11ea50ebdb8ac3e9
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244029"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover os usuários no local para equipes

Quando um usuário é movido no local para equipes apenas, do usuário Skype para home Business é movido do local para online e o usuário é atribuído TeamsUpgradePolicy com modo = TeamsOnly.  Depois que um usuário é movido do local, para o modo de TeamsOnly:

- Entrada de todas as chamadas e chats de outros usuários (se enviado de Skype para equipes ou comercial), serão land no cliente de equipes do usuário.
- O usuário será capaz de interoperar com outros usuários que usam Skype para negócios (seja online ou no local). 
- O usuário será capaz de se comunicar com usuários em organizações federadas.
- As novas reuniões agendadas pelo usuário são reuniões de equipes.
- Usuário ainda poderão ingressar qualquer Skype para reuniões de negócios.
- Reuniões pré-existente do usuário, agendados para o futuro serão migradas no local para o Skype para negócios Online.
- Os contatos que existiam no local estão disponíveis no equipes logo depois que o usuário fizer logon pela primeira vez.
- Os usuários não podem iniciar chamadas ou chats do Skype for Business, nem podem eles agendar reuniões de novas no Skype para negócios. Se eles tentarem abrir o Skype para o cliente de negócios, elas serão redirecionadas para usar equipes, conforme mostrado abaixo. Se o cliente de equipes não estiver instalado, eles serão direcionados para a versão da web de equipes usando seu navegador.<br><br>
    ![O redirecionamento de um usuário para as equipes de mensagem](../media/go-to-teams-page.png)

Antes de mover todos os usuários, certifique-se de revisar os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuários para a nuvem. Também Certifique-se de revisar a [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Há dois métodos para mover de um usuário no local para equipes:

- Se você estiver usando uma versão anterior ao Skype para Business Server 2015 CU8, a movimentação requer duas etapas (que podem ter scripts a ser feito juntos como uma única etapa, se desejado):
    - [Mover o usuário do Skype para Business Server (no local) para Skype para negócios Online](move-users-from-on-premises-to-skype-for-business-online.md).
    - Depois que o usuário está hospedado no Skype para negócios on-line, atribuir ao usuário TeamsUpgradePolicy com modo = TeamsOnly. Para conceder o modo TeamsOnly, execute o seguinte cmdlet de um Skype para a janela de negócios Online PowerShell:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Se você tiver ferramentas de administração do Skype para Business Server 2015 CU8 ou posterior, você pode usar o método acima, ou você pode fazer essa transferência em uma única etapa, conforme descrito abaixo. Além disso, você pode, opcionalmente, forneça uma notificação dentro do Skype para Business client antes de movê-los para equipes apenas bem como se desejar ter o cliente de equipes silenciosamente baixado pelo Skype para o cliente de negócios.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover um usuário diretamente do Skype for Business no local para equipes somente

As ferramentas de administração do local no Skype para 2015 do servidor de negócios com CU8, bem como em Skype para o servidor de negócios 2019, permitem que você mover os usuários no local para equipes somente modo em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou o Skype para negócios Se servidor & Painel de controle, conforme descrito abaixo.

### <a name="move-to-teams-using-move-csuser"></a>Mover para equipes usando Move-CsUser

Move-CsUser está disponível no Skype local para a janela do PowerShell de Shell de gerenciamento de negócios. As permissões necessárias e etapas a seguir são os mesmos mover um usuário para Skype para negócios Online, exceto que você também deve especificar a opção MoveToTeams e certifique-se de que o usuário também recebeu uma licença para equipes (além do Skype para negócios Online).

Você deve ter privilégios suficientes no ambiente do local e o inquilino do Office 365, conforme descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Você pode usar uma única conta que possua privilégios nos dois ambientes, ou você pode iniciar uma Skype local para a janela do Shell de gerenciamento do servidor de negócios com credenciais locais e usar o `-Credential` parâmetro para especificar as credenciais para um Office 365 conta com a função administrativa do Office 365 necessária.

Para mover um usuário para o modo de equipes apenas usando o Move-CsUser:

- Especificar o usuário mover usando o `Identity` parâmetro.
- Especificar o - parâmetro de destino com o valor "sipfed.online.lync. <span>com ".
- Especificar o `MoveToTeams` alternar.
- Se você não tiver uma conta com permissões suficientes em ambos no local e o Office 365, use o `-credential` parâmetro para fornecer uma conta com permissões suficientes no Office 365.
- Se a conta com permissões no Office 365 não termina em "on.microsoft. <span>com ", você deve especificar o `-HostedMigrationOverrideUrl` parâmetro, com o valor correto, como descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

A seguinte sequência de cmdlet pode ser usada para mover um usuário para TeamsOnly e assume a credencial do Office 365 é uma conta separada e fornecidos como entrada para o prompt de Get-Credential.

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover para equipes usando Skype para painel de controle do servidor de negócios

1.  Abra o Skype para controle de servidor de negócios app do painel.
2.  No painel de navegação esquerdo, escolha **usuários**.
3.  Use o comando **Localizar** para localizar o (s) que você deseja mover para equipes.
4.  Selecione o (s) e, no menu suspenso de **ação** acima da lista, selecione **mover usuários selecionados para equipes**.
5.  No assistente, clique em **Avançar**.
6.  Se solicitado, faça logon no Office 365, com uma conta que termina em. onmicrosoft.com e tem permissões suficientes.
7.  Clique em **Avançar**e, em seguida, **Avançar** mais uma vez para mover o usuário.
8. Observe que as mensagens de status sobre o sucesso ou falha são fornecidas na parte superior do aplicativo principal do painel de controle, não no assistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar seu Skype para usuários locais de negócios da movimentação futura às equipes

As ferramentas de administração do local no Skype para 2015 do servidor de negócios com CU8, bem como em Skype para o servidor de negócios 2019, permitem que você notificar Skype local para usuários comerciais de seu movimentação futura às equipes. Quando você habilita essas notificações, os usuários verão uma notificação em seu Skype para o cliente de negócios (Win32, Mac, web e móveis), conforme mostrado abaixo. Se os usuários clicam no botão **Experimente** , o cliente de equipes será iniciado se ele estiver instalado; Caso contrário, os usuários serão direcionados para a versão da web de equipes em seu navegador. Por padrão, quando as notificações estão habilitadas, Win32 Skype para clientes corporativos silenciosamente baixar o cliente de equipes para que o cliente avançado está disponível antes de mover o usuário para equipes somente modo; No entanto, você também pode desativar esse comportamento.  As notificações são configuradas usando a versão local do `TeamsUpgradePolicy`, e download silenciosa para clientes do Win32 é controlada por meio do local `TeamsUpgradeConfiguration` cmdlet.

![Notificação de movimentação de futura às equipes](../media/teams-upgrade-notification.png)

Para notificar os usuários no local que eles breve serão atualizados para equipes, criar uma nova instância do TeamsUpgradePolicy com NotifySfBUsers = true. Atribua essa diretiva para os usuários que você deseja notificar, atribuindo a política diretamente para o usuário ou definindo a política no nível global, pool ou site. Os cmdlets a seguir criar e conceder uma política de nível de usuário:

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

O download automático de equipes via o Skype para negócios Win32 cliente é controlado por meio do cmdlet de TeamsUpgradeConfiguration local com o parâmetro DownloadTeams. Você criar essa configuração em um global, site e nível de pool. Por exemplo, o comando a seguir cria a configuração do site Redmond1:

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

Por padrão, o valor de DownloadTeams é True; No entanto, é *só* cumpridas se NotifySfbUser = True para um determinado usuário.


## <a name="see-also"></a>Consulte também

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistência com o Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
