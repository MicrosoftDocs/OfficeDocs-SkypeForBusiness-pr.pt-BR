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
search.appverid: MET150
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
- Audio Conferencing
description: Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 045896fe8b612e01a22360e0c12f15ebe2719c76
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374636"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configurando o Meeting Migration Service (MMS)

Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.  This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.  
  
 **Requisitos**
  
O MMS exige que as caixas de correio dos organizadores da reunião estejam no Exchange Online.
  
 **Cenários principais**
  
O MMS atualiza as reuniões do Skype para os usuários nestes dois cenários principais:
  
- Quando o usuário é migrado do Skype local para o servidor de negócios para Skype para negócios Online.
    
- Quando um administrador faz uma alteração para configurações de serviços de audioconferência do usuário que exigiriam a atualizar as informações de conferência de áudio em reuniões desse usuário.
    
  **Cenários comuns em que o MMS não pode ser usado**
  
Veja alguns cenários comuns que podem se aplicar a você. Todos eles dão suporte à migração. Porém, o MMS não será executado nesses cenários e você deverá usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) em seu lugar.
  
- As caixas de correio do usuário estão no Exchange Server local
    
- Usando um provedor de serviços de audioconferência de terceiros
    
- Migrar usuários do Skype para Business Online para o servidor local Skype
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Atualizando reuniões quando um usuário local migra para o Skype for Business Online

This is the most common scenario where MMS can help create a smoother transition for your users. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Se você estiver no momento usando Skype Server 2015 para serviços de audioconferência

Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:
  
- Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.
    
- Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Se estiver usando um provedor de serviços de audioconferência (ACP, Audio Conferencing Provider) de terceiros

With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.
    
- If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Atualizando reuniões quando alteram as configurações de serviços de audioconferência do usuário

MMS atualizará um Skype existente para reuniões de negócios e Teams Microsoft nos seguintes casos:
  
- Quando você atribuir ou remove a licença de **Conferência de áudio** .
    
- Quando você habilitar ou desabilitar os serviços de audioconferência.
    
- Quando você alterar ou reiniciar o ID de conferência para um usuário configurado para usar as reuniões públicas.
    
- Quando você move o usuário para uma nova ponte de conferência de áudio.
    
- When a phone number is unassigned from a audio conferencing bridge. This is a complex scenario which requires additional steps. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> MMS only updates meetings when you're using the Microsoft bridge. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:
  
- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
    
- Quando você altera a URL da reunião da organização usando o comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>O que acontece quando o MMS atualiza as reuniões?

Quando o MMS detecta que as reuniões de um usuário precisam ser atualizadas, ele faz o seguinte:
  
1. Identificar todos os Skype para reuniões Teams da Microsoft e de negócios, o usuário tiver programado no futuro
    
   - Qualquer Skype para reuniões de negócios ou Microsoft Teams que ocorreram antes de quando MMS é executado são ignorados
    
   - Somente as reuniões organizadas pelo usuário são atualizadas
    
2. Substitua o bloco de informações da reunião online nos detalhes da reunião
    
3. Envie atualizações para todos os destinatários da reunião em nome do organizador
    
   **Quanto tempo levará para o MMS ser executado?**
  
The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. At a minimum, it will take 10 minutes to run. While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.
  
 **Limitações e possíveis problemas**
  
- Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.
    
- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.
    
     ![O bloco de reuniões que são atualizadas pelo MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
    
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.
    
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
    
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>O que os usuários verão quando o MMS atualizar suas reuniões?

Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.
  
## <a name="managing-mms"></a>Gerenciando o MMS

You need to use Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new to PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Como faço para conferir o status das migrações de reuniões?

Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.
  
Para ver um status resumido de todas as migrações do MMS, execute este comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Ele fornecerá todos os estados de migração em uma exibição tabular, assim:
  
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

MMS is enabled by default for all organizations, but it can be disabled as needed. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. You may also choose to temporarily disable MMS. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.
  
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

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Habilitando e desabilitando MMS somente para alterações de conferência de áudio
<a name="Troubleshooting"> </a>

You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Para desativar MMS para conferência de áudio, execute o seguinte comando:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Para habilitar MMS para conferência de áudio, execute o seguinte comando:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Como executo a Migração de Reunião manualmente para um usuário?
<a name="Troubleshooting"> </a>

In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.
  
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
>   ```
>   Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>   $credential = Get-Credential
>   $session = New-CsOnlineSession -Credential $credential
>   Import-PSSession $session
>   ```
> Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
