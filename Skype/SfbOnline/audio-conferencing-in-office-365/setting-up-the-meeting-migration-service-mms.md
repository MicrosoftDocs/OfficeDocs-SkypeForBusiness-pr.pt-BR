---
title: Configurando o Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: O Meeting Migration Service (MMS) é um serviço do Skype for Business executado em segundo plano que atualiza automaticamente as reuniões do Skype for Business e do Microsoft Teams para os usuários. O MMS foi projetado para que os usuários não precisem executar a ferramenta de migração de reunião para atualizar as reuniões do Skype for Business e do Microsoft Teams.
ms.openlocfilehash: 013e68ada16f15b3a410823680ec062b9fb7fa3a
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780497"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configurando o Meeting Migration Service (MMS)

O Meeting Migration Service (MMS) é um serviço do Skype for Business executado em segundo plano que atualiza automaticamente as reuniões do Skype for Business e do Microsoft Teams para os usuários. O MMS foi projetado para que os usuários não precisem executar a ferramenta de migração de reunião para atualizar as reuniões do Skype for Business e do Microsoft Teams.  Essa ferramenta não migra as reuniões do Skype for Business para as reuniões do Microsoft Teams.  
  
 **Requisitos**
  
O MMS exige que as caixas de correio dos organizadores da reunião estejam no Exchange Online.
  
 **Cenários principais**
  
O MMS atualiza as reuniões do Skype para os usuários nestes dois cenários principais:
  
- Quando o usuário migra do Skype for Business Server local para o Skype for Business Online.
    
- Quando um administrador faz uma alteração para configurações de audioconferência do usuário que exigiriam a atualização das informações de audioconferência em reuniões desse usuário.
    
 **Cenários comuns em que o MMS não pode ser usado**
  
Veja alguns cenários comuns que podem se aplicar a você. Todos eles dão suporte à migração. Porém, o MMS não será executado nesses cenários e você deverá usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) em seu lugar.
  
- As caixas de correio do usuário estão no Exchange Server local
    
- Usar um provedor de serviços de audioconferência de terceiros
    
- Migrar usuários do Skype for Business Online para o Skype Server local
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Atualizar reuniões quando um usuário local migra para o Skype for Business Online

Este é o cenário mais comum em que o MMS pode ajudar a proporcionar uma transição mais fluida para os seus usuários. Quando o usuário migra do Skype for Business Server local para o Skype for Business Online, o MMS detecta o novo usuário e verifica as reuniões do Skype for Business e do Microsoft Teams no calendário desse usuário. Todas as reuniões futuras serão atualizadas com as novas informações do usuário.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Se você usa o Skype Server 2015 para audioconferência

Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:
  
- Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.
    
- Atribua a licença de **Audioconferência** ao usuário antes de executar o cmdlet `Move-CSUser` para fazer a migração do usuário. Assim, o MMS também atualizará as reuniões quando as configurações de audioconferência do usuário forem alteradas. Se você não atribuir a licença primeiro, o MMS atualizará todas as reuniões novamente no momento da atribuição da licença.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Se estiver usando um provedor de serviços de audioconferência (ACP) de terceiros

Com um ACP de terceiros, a execução do MMS depende das configurações de audioconferência da sua organização. Você pode optar por substituir os números de discagem do ACP automaticamente quando atribuir a licença de **Audioconferência** ao usuário. Por outro lado, talvez seja necessário impedir que isso aconteça e manter os números de discagem do seu ACP. Para ver as configurações da sua organização, execute o comando do Windows PowerShell a seguir e confira o valor do parâmetro `AutomaticallyReplaceAcpProvider`. Se precisar de ajuda com o PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Se o valor desse parâmetro for $true, o MMS será executado quando for atribuída uma licença de **Audioconferência** ao usuário, atualizando suas reuniões. Os números de discagem de seu ACP são mantidos até que seja atribuída a licença de **Audioconferência**.
    
- Se o valor deste parâmetro for $false, o MMS não atualizará as reuniões, mesmo que seja atribuída uma licença de **Audioconferência** ao usuário. Os números de discagem de seu ACP são mantidos até que a audioconferência seja provisionada manualmente para o usuário no centro de administração do Skype for Business ou usando o Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Atualizar reuniões quando as configurações de audioconferência do usuário são alteradas

O MMS atualizará asa reuniões existentes do Skype for Business e do Microsoft Teams nos seguintes casos:
  
- Quando você atribuir ou remover a licença de **Audioconferência**.
    
- Quando você ativar ou desativar os serviços de audioconferência.
    
- Quando você alterar ou redefinir a ID de Conferência de um usuário configurado para usar reuniões públicas.
    
- Quando você mover o usuário para uma nova ponte de audioconferência.
    
- Quando for cancelada a atribuição de um número de telefone de uma ponte de audioconferência. Esse é um cenário complexo que requer etapas adicionais. Para obter mais informações, consulte [Mudar números de chamada tarifada ou de chamada gratuita para sua ponte de audioconferência](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> O MMS atualiza as reuniões somente quando você usa a ponte da Microsoft. Se estiver usando um provedor de serviços de audioconferência de terceiros, os usuários deverão atualizar as reuniões manualmente. Nesse caso, você pode usar a [ferramenta de migração de reunião](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Nem todas as alterações das configurações de audioconferência do usuário acionam o MMS. Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:
  
- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
    
- Quando você altera a URL da reunião da organização usando o comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>O que acontece quando o MMS atualiza as reuniões?

Quando o MMS detecta que as reuniões de um usuário precisam ser atualizadas, ele faz o seguinte:
  
1. Identifica todas as reuniões do Skype for Business e do Microsoft Teams que o usuário tiver programado no futuro
    
  - Qualquer reunião do Skype for Business e do Microsoft Teams que ocorreu antes da execução do MMS é ignorada
    
  - Somente as reuniões organizadas pelo usuário são atualizadas
    
2. Substitua o bloco de informações da reunião online nos detalhes da reunião
    
3. Envie atualizações para todos os destinatários da reunião em nome do organizador
    
 **Quanto tempo levará para o MMS ser executado?**
  
O tempo necessário para o MMS migrar as reuniões varia de acordo com o número de usuários afetados e o número total de reuniões do Skype for Business ou do Microsoft Teams que cada usuário tem no calendário. A execução levará pelo menos dez minutos. Embora algumas migrações maiores possam levar até 12 horas, a maioria delas deve ser concluída em uma hora.
  
 **Limitações e possíveis problemas**
  
- Somente as reuniões do Skype for Business ou do Microsoft Teams que foram agendadas clicando no botão **Adicionar reunião do Skype** no Outlook na Web ou usando o suplemento Reunião do Skype para Outlook são migradas. Em outras palavras, se um usuário copiar e colar as informações da reunião online do Skype de uma reunião para uma nova, essa nova reunião não será atualizada.
    
- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.
    
     ![O bloco de reuniões que são atualizadas pelo MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
    
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.
    
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
    
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>O que os usuários verão quando o MMS atualizar suas reuniões?

Assim como a ferramenta de migração de reunião, o MMS envia atualizações de reunião em nome de usuários. Portanto, a única coisa que os usuários verão é outra rodada de notificações de aceitação para suas reuniões. Isso pode ser confuso para os usuários, portanto, recomendamos que os notifique com antecedência, não somente quando você migrá-los do local para o Skype for Business Online, mas também quando você fizer alterações de audioconferência que irão acionar o MMS.
  
## <a name="managing-mms"></a>Gerenciando o MMS

Você precisa usar o Windows PowerShell para gerenciar o MMS e verificar o status das migrações em andamento. As informações contidas nesta seção pressupõem que você saiba como usar o PowerShell para gerenciar Skype for Business de sua organização. Se você é iniciante no PowerShell, consulte a seção [Usando o PowerShell para gerenciar o Skype for Business se dua organização](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Como faço para conferir o status das migrações de reuniões?

Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.
  
Para ver um status resumido de todas as migrações do MMS, execute este comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Ele fornecerá um modo de exibição tabular de todos os estados de migração desse modo:
  
Estado UserCount---------------<br/> Pending 21<br/>InProgress 6<br/> Failed 2 <br/> Succeeded 131
> [!IMPORTANT]
> [!IMPORTANTE] Se houver migrações com falha, tome as medidas necessárias para resolver os problemas assim que possível. As pessoas não conseguirão discar para as reuniões organizadas por esses usuários até que você os resolva. Veja a seção [O que devo fazer se ocorrer um erro?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) para obter mais informações.
  
Para ver detalhes completos de todas as migrações de um período específico, você pode usar os parâmetros  `StartTime` e `EndTime`. Por exemplo, o comando a seguir retornará detalhes completos de todas as migrações ocorridas de 1º a 8 de outubro de 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Talvez você também queira conferir o status da migração de um usuário específico. Para isso, use o parâmetro  `UserId`. Por exemplo, o comando a seguir retornará o status do usuário ashaw@contoso.com:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>O que devo fazer se ocorrer um erro?
<a name="Troubleshooting"> </a>

Quando você executa o cmdlet  `Get-CsMeetingMigrationStatus` para ver um resumo e o estado Com falhaé observado, você precisa fazer o seguinte:
  
1. Determine quais usuários são afetados. Execute o comando a seguir para obter a lista de usuários afetados e o erro específico que foi informado:
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. Para cada um desses usuários, execute a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) para fazer a migração manual de suas reuniões.
    
3. Se a migração com a ferramenta de migração de reuniões também não funcionar, você terá duas opções:
    
  - Fazer os usuários criarem novas reuniões do Skype.
    
  - [Contatar o suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322).
    
### <a name="enabling-and-disabling-mms"></a>Habilitando e desabilitando o MMS
<a name="Troubleshooting"> </a>

O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado conforme necessário. Por exemplo, se quiser migrar todas as reuniões manualmente ou se usar um provedor de serviços de audioconferência de terceiros, talvez você não precise executar o MMS. Você também pode optar por desativar o MMS temporariamente. Por exemplo, se estiver alterando substancialmente as configurações de audioconferência da organização e não quiser que o MMS seja executado até que todas as alterações sejam concluídas.
  
Para ver se o MMS está habilitado em sua organização, execute o comando a seguir e confira o valor do parâmetro  `MeetingMigrationEnabled`. Se esse parâmetro está definido como $true, o MMS está habilitado.
  
```
Get-CsTenantMigrationConfiguration
```

Para desabilitar o MMS, execute este comando:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Para ativar o MMS, execute este comando:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Ativar e desativar o MMS somente para alterações de audioconferência
<a name="Troubleshooting"> </a>

Você também pode desativar o MMS somente para alterações de audioconferência. Ele continuará sendo executado quando um usuário migrar do Skype for Business local para o Skype for Business Online. Para verificar o status atual do MMS para atualizações de audioconferência, execute o comando a seguir e confira o valor do parâmetro  `AutomaticallyMigrateUserMeetings`. Se esse parâmetro está definido como $true, o MMS está definido para atualizar as reuniões do usuário quando as configurações de audioconferência forem alteradas.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Para desativar o MMS para audioconferência, execute o seguinte comando:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Para ativar o MMS para audioconferência, execute o seguinte comando:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Como executo a Migração de Reunião manualmente para um usuário?
<a name="Troubleshooting"> </a>

Além das migrações automáticas de reunião, você também pode executar a migração de reunião manualmente para um usuário executando o cmdlet **Start-CsExMeetingMigration**. Este cmdlet adiciona o usuário na fila de migração de reunião. O Meeting Migration Service lerá a solicitação do usuário e migrará sua reunião. Você pode verificar o status da migração da reunião com o cmdlet **Get-CsMeetingMigrationStatus**.
  
Este é um exemplo que inicia a migração da reunião para o usuário ashaw@contoso.com:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>Usando o PowerShell para gerenciar a organização do Skype for Business
<a name="WPSInfo"> </a>

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
  
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Iniciar uma sessão do Windows PowerShell**
  
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
