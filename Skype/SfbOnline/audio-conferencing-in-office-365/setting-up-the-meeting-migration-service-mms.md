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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: e240d9913ac543495286d8151bc0200a0f7c196d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configurando o Meeting Migration Service (MMS)

Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
  
 **Requisitos**
  
O MMS exige que as caixas de correio dos organizadores da reunião estejam no Exchange Online.
  
 **Cenários principais**
  
O MMS atualiza as reuniões do Skype para os usuários nestes dois cenários principais:
  
- Quando o usuário migra do Skype for Business Server local para o Skype for Business Online
    
- When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.
    
 **Cenários comuns em que o MMS não pode ser usado**
  
Veja alguns cenários comuns que podem se aplicar a você. Todos eles dão suporte à migração. Porém, o MMS não será executado nesses cenários e você deverá usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) em seu lugar.
  
- As caixas de correio do usuário estão no Exchange Server local
    
- Using a third-party audio conferencing provider
    
- Migração de usuários do Skype for Business Online para o servidor Skype local
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Atualizando reuniões quando um usuário local migra para o Skype for Business Online

Este é o cenário mais comum em que o MMS pode ajudar a proporcionar uma transição mais fluida para os seus usuários. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>If you're currently using Skype Server 2015 for audio conferencing

Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:
  
- Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.
    
- Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. Se você não atribuir a licença primeiro, o MMS atualizará todas as reuniões novamente no momento da atribuição da licença.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Se estiver usando um provedor de serviços de audioconferência (ACP, Audio Conferencing Provider) de terceiros

With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. Por outro lado, talvez seja necessário impedir que isso aconteça e manter os números de discagem do seu ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. Se precisar de ajuda com o PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.
    
- If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Updating meetings when a user's audio conferencing settings change

MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:
  
- When you assign or remove **Audio Conferencing** license.
    
- When you enable or disable audio conferencing.
    
- Quando você alterar ou redefinir a ID de Conferência de um usuário configurado para usar reuniões públicas
    
- When you move the user to a new audio conferencing bridge.
    
- When a phone number is unassigned from a audio conferencing bridge. Esse é um cenário complexo que requer etapas adicionais. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> [!IMPORTANTE] O MMS atualiza as reuniões somente quando você usa a ponte da Microsoft. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. Nesse caso, você pode usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Not all changes to a user's audio conferencing settings trigger MMS. Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:
  
- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
    
- Quando você altera a URL da reunião da organização usando o comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>O que acontece quando o MMS atualiza as reuniões?

Quando o MMS detecta que as reuniões de um usuário precisam ser atualizadas, ele faz o seguinte:
  
1. Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future
    
  - Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped
    
  - Somente as reuniões organizadas pelo usuário são atualizadas
    
2. Substitua o bloco de informações da reunião online nos detalhes da reunião
    
3. Envie atualizações para todos os destinatários da reunião em nome do organizador
    
 **Quanto tempo levará para o MMS ser executado?**
  
The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. A execução levará pelo menos dez minutos. Embora algumas migrações maiores possam levar até 12 horas, a maioria delas deve ser concluída em uma hora.
  
 **Limitações e possíveis problemas**
  
- Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. Em outras palavras, se um usuário copiar e colar as informações da reunião online do Skype de uma reunião para uma nova, essa nova reunião não será atualizada.
    
- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
    
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.
    
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
    
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>O que os usuários verão quando o MMS atualizar suas reuniões?

Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.
  
## <a name="managing-mms"></a>Gerenciando o MMS

Você precisa usar o Windows PowerShell para gerenciar o MMS e verificar o status das migrações em andamento. As informações contidas nesta seção pressupõem que você saiba como usar o PowerShell para gerenciar sua organização do Skype for Business. Se você é iniciante no PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Como faço para conferir o status das migrações de reuniões?

Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.
  
Para ver um status resumido de todas as migrações do MMS, execute este comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Ele fornecerá todos os estados de migração em uma exibição tabular, assim:
  
State UserCount---------------<br/> Pending 21<br/>InProgress 6<br/> Failed 2 <br/> Succeeded 131
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

O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado conforme necessário. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. Você também pode optar por desabilitar o MMS temporariamente. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.
  
Para ver se o MMS está habilitado em sua organização, execute o comando a seguir e confira o valor do parâmetro  `MeetingMigrationEnabled`. Se esse parâmetro está definido como $true, o MMS está habilitado.
  
```
Get-CsTenantMigrationConfiguration
```

Para desabilitar o MMS, execute este comando:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Para habilitar o MMS, execute este comando:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Enabling and disabling MMS only for audio conferencing changes
<a name="Troubleshooting"> </a>

You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

To disable MMS for audio conferencing, run the following command:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

To enable MMS for audio conferencing, run the following command:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Como executo a Migração de Reunião manualmente para um usuário?
<a name="Troubleshooting"> </a>

Além das migrações automáticas de reunião, você também pode executar a migração de reunião manualmente para um usuário executando o cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. O Meeting Migration Service lerá a solicitação do usuário e migrará sua reunião. Você pode verificar o status da migração da reunião com o cmdlet **Get-CsMeetingMigrationStatus**.
  
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
    
  - [Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
