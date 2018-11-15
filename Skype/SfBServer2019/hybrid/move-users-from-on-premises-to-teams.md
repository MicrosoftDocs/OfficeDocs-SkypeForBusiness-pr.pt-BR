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
ms.openlocfilehash: af0867bfdc2e12a248baf7cc07746845154d27fd
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533138"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover os usuários no local para equipes

Com Skype para Business Server 2019, você pode migrar seus usuários no local para equipes, conforme descrito neste artigo.

Lembre-se que depois de mover os usuários para equipes: 
 
- Suas reuniões são migrados para o Skype para Business Online e seus contatos são migrados para as equipes. 
- Eles podem ingressar em reuniões do Skype por meio do Skype para Business rich client (os usuários não são solicitados para cada vez que entrar) ou o aplicativo de reuniões do Skype (requer um download único e entrar). Quando um usuário clica em um Skype para o link da reunião de negócios dentro de equipes, a reunião será iniciado no aplicativo apropriado.

- Em Mobile, os usuários poderão ingressar Skype existente para reuniões de negócios usando o app nativo somente.

> [!NOTE]
> Depois que um usuário é movido para o modo de TeamsOnly, o usuário está hospedado no Skype para negócios Online.

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a>Pré-requisitos para mover usuários locais para equipes 

Esta seção descreve os pré-requisitos para mover os usuários no local para equipes. Faça o seguinte:
- [Configurar a conectividade híbrida](#set-up-hybrid-connectivity) (se você ainda não tiver feito isso)
- [Notifique os usuários da mudança às equipes](#notify-your-users-of-the-move-to-teams) (opcional)
- [Certifique-se de que os usuários têm uma licença válida](#make-sure-your-users-have-a-valid-license)
- [Esteja ciente dos requisitos de configuração de voz](#voice-configuration-requirements)
- [Atribuir uma política de atualização de equipes](#assign-a-teams-upgrade-policy) (opcional)

## <a name="set-up-hybrid-connectivity"></a>Configurar a conectividade híbrida
Antes de migrar os usuários, se você ainda não tiver feito isso, você deve garantir que você tenha configurado a conectividade híbrida entre o Skype para o ambiente do Business Server local e Skype para negócios Online. Conectividade híbrida exige a sincronização do Active Directory, configurando federação e assim por diante. Para obter mais informações, consulte [Planejar a conectividade híbrida](plan-hybrid-connectivity.md) e [conectividade de híbrida Configure](configure-hybrid-connectivity.md).

## <a name="notify-your-users-of-the-move-to-teams"></a>Notifique os usuários da mudança às equipes 
Essa é uma etapa opcional, mas que você deve considerar. Para notificar os usuários da atualização pendente equipes, você pode usar os cmdlets de TeamsUpgradePolicy e TeamsUpgradeConfiguration do local. Você também pode configurar o download automático silencioso de equipes em segundo plano antes da atualização (somente clientes do Win32). 

Por exemplo, para notificar os usuários que estão sendo atualizados para equipes, use o cmdlet de TeamsUpgradePolicy de local com o parâmetro - NotifySbUser. Você pode definir a diretiva no nível global, site, pool ou usuário. O comando a seguir cria e concede uma política de nível de usuário:
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

Você pode verificar esta diretiva usando o cmdlet Get-csTeamsUpgradePolicy.

Os usuários verão uma notificação da movimentação iminente às equipes. A notificação ocorre no Win32, Mac, móveis e clientes Web (com a versão correta).

Você pode especificar o download automático de equipes (para clientes do Win32) para usuários que estão sendo atualizados usando o cmdlet de TeamsUpgradeConfiguration local com o parâmetro DownloadTeams. Defini-la no nível de locatário, e ele pode ser aplicada em um site global e nível de pool. Por exemplo, o comando a seguir define a política no nível do site:

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

Por padrão, o valor de DownloadTeams é True, mas você também deve definir NotifySfbUser como True para permitir que equipes para um determinado usuário. 

## <a name="make-sure-your-users-have-a-valid-license"></a>Certificar-se de que os usuários têm uma licença válida  
Antes da migração, o usuário local deve ser fornecido uma licença válida, da seguinte maneira:

-   Usuário deve ter uma licença de equipes.
-   Se o usuário estiver configurado para usar o Enterprise Voice do local, eles devem ter uma licença de voz online durante a mudança. 
-   Se o usuário estiver configurado para conferência discada do local, eles devem ter uma licença para o sistema telefônico (nuvem PBX).

## <a name="voice-configuration-requirements"></a>Requisitos de configuração de voz

Se os usuários no local tiverem voz no local, você tem duas opções:

-  **Migre usuários com os recursos de telefonia.** Os usuários podem fazer e receber chamadas usando o cliente de equipes.  Você pode escolher entre Microsoft chamar planejar ou em roteamento direto para conectar os serviços de telefonia para equipes.  

    -  Chamar plano Microsoft fornece uma solução de voz all nuvem. Para obter mais informações sobre como chamar plano Microsoft, consulte (link em breve). 
    -  Roteamento direto permite usar praticamente qualquer tronco PSTN, e você pode configurar a interoperabilidade entre o sistema de telefone da Microsoft e equipamentos de telefonia de propriedade do cliente.  Para obter mais informações, consulte [Planejar roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) e [Configurar o roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).

-  **Migre usuários sem recursos de telefonia.** Se você migrar usuários sem preservar os recursos de telefonia, certifique-se de usuários têm licenças apropriadas na nuvem. 

## <a name="assign-a-teams-upgrade-policy"></a>Atribuir uma política de atualização de equipes  
Você pode usar as ferramentas on-line para gerenciar políticas de usuário, tais como controlar o roteamento de chamadas e mensagens de entrada. Para obter mais informações, consulte (link em breve).

## <a name="move-on-premises-users-to-teams"></a>Mover usuários locais para equipes

Você pode mover os usuários no local para equipes usando cmdlets do PowerShell ou usando o Skype para painel de controle do Business Server 2019.

### <a name="move-users-by-using-powershell"></a>Mover usuários usando o PowerShell
Para mover os usuários para equipes usando o PowerShell, você vai usar o cmdlet Move-CsUser com o parâmetro moveToTeams da seguinte maneira:

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

($cred = get-credenciais. Você deve fornecer credenciais de administrador do Office 365.)

> [!NOTE]
> Esse comando define o TeamsUpgradePolicy para o modo de TeamsOnly. 
 
Após a mudança para equipes for bem-sucedida, Skype do usuário para o cliente de negócios exibirá a seguinte mensagem: 

![Migração bem-sucedida a mensagem de equipes](../media/teams-upgrade-complete-message.png)

Observe que Skype para negócios não ficarão mais disponível para o usuário, exceto ao ingressar em uma reunião. 

Em casos raros, ao mover os usuários para equipes, você talvez queira substituir a conferência discada e funcionalidade de voz na nuvem. Você pode fazer isso usando os seguintes parâmetros com o comando Move-CsUser:
- **BypassAudioConferencingCheck:** Se um usuário tiver discada habilitada para o local, o usuário também deve ter uma licença de AudioConf atribuída no Office 365 antes da migração. Uma vez migrados para a nuvem, o usuário será provisionado para conferência de áudio na nuvem. Se, por algum motivo, que você deseja mover um usuário na nuvem, mas não usar a funcionalidade de conferência de áudio, você pode substitui-la especificando-se esse parâmetro.
- **ByPassEnterpriseVoice:** Se um usuário tiver o Enterprise Voice habilitado para o local, o usuário deve ter uma licença Enterprise Voice atribuída no Office 365 antes da migração. Após a migração para a nuvem, o usuário será provisionado para voz na nuvem. Se, por algum motivo, que você deseja mover um usuário na nuvem, mas não usar a funcionalidade de voz de nuvem, você pode substituir a nuvem voz especificando-se esse parâmetro.
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a>Mover usuários usando o Skype para painel de controle do servidor de negócios 

Para mover usuários para equipes usando o Skype para painel de controle de negócios:

1. Abra o Skype para painel de controle de negócios e entrar em sua conta do Office 365.

2. Selecione os **usuários** no painel de navegação esquerdo e selecione os usuários para migrar. 
     
3. No menu **ação** , selecione **mover usuários selecionados para equipes**. 

    ![Clicar em Avançar para confirmar a migração](../media/migration-confirmation.png)
    
4. Clique em **Avançar** para confirmar sua migração. 

Depois que o usuário é movido para equipes, você verá as confirmações semelhante ao seguinte:

![Mover a confirmação de usuários](../media/move-user-confirmation.png)
<br/><br/>
![Se os usuários foram movidos de mensagem](../media/users-moved-successfully.png)

Se a movimentação não tiver sido bem-sucedida, você verá uma mensagem semelhante ao seguinte:

![Mensagem que não puderam ser movido usuário](../media/users-not-moved.png)
