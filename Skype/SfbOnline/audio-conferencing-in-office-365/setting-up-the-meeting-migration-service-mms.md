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
description: Serviço de migração (MMS) de reunião é um Skype para serviço de negócios que é executado em segundo plano e atualiza automaticamente o Skype para reuniões de negócios e Teams da Microsoft para usuários. MMS foi projetado para eliminar a necessidade de usuários executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft.
ms.openlocfilehash: 8da3aaabdd772c5de8f110996585f1386f9eeb05
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configurando o Meeting Migration Service (MMS)

Serviço de migração (MMS) de reunião é um Skype para serviço de negócios que é executado em segundo plano e atualiza automaticamente o Skype para reuniões de negócios e Teams da Microsoft para usuários. MMS foi projetado para eliminar a necessidade de usuários executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft.  Essa ferramenta não transfere Skype para reuniões de negócios em reuniões de Teams da Microsoft.  
  
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

Este é o cenário mais comum em que o MMS pode ajudar a proporcionar uma transição mais fluida para os seus usuários. Quando um usuário é migrado do Skype local para o servidor de negócios para Skype para Business Online, MMS detectará o novo usuário e examinará calendário desse usuário para Skype para reuniões de negócios e Teams da Microsoft. Qualquer futuras reuniões serão atualizadas com as novas informações para esse usuário.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Se você estiver no momento usando Skype Server 2015 para serviços de audioconferência

Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:
  
- Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.
    
- Atribuir a licença de **Conferência de áudio** ao usuário antes de executar o `Move-CSUser` cmdlet para migrar o usuário. Isso acontece porque MMS também atualiza reuniões quando as configurações de serviços de audioconferência são alteradas para um usuário. Se você não atribuir a licença primeiro, o MMS atualizará todas as reuniões novamente no momento da atribuição da licença.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Se estiver usando um provedor de serviços de audioconferência (ACP, Audio Conferencing Provider) de terceiros

Com um ACP de terceiros, ou não executa o MMS depende das configurações de conferência de áudio da sua organização. Você pode optar por substituir automaticamente os números de discagem do seu ACP ao atribuir um usuário uma licença de **Conferência de áudio** . Por outro lado, talvez seja necessário impedir que isso aconteça e manter os números de discagem do seu ACP. Para ver a definição da sua organização, execute o seguinte comando do Windows PowerShell e verifique o valor do parâmetro `AutomaticallyReplaceAcpProvider`. Se precisar de ajuda com o PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Se o valor desse parâmetro for $true, MMS será executado quando um usuário é atribuído com uma licença de **Conferência de áudio** e atualizar suas reuniões. Os números de discagem do seu ACP são mantidos até que a **Conferência de áudio** de licença foi distribuída.
    
- Se o valor desse parâmetro for $false, MMS não atualize as reuniões, mesmo se um usuário é atribuído com uma licença de **Conferência de áudio** . Os números de discagem do seu ACP são mantidos até que o usuário é provisionado manualmente para conferência de áudio no Skype para o Centro de administração de negócios ou usando o Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Atualizando reuniões quando alteram as configurações de serviços de audioconferência do usuário

MMS atualizará um Skype existente para reuniões de negócios e Teams Microsoft nos seguintes casos:
  
- Quando você atribuir ou remove a licença de **Conferência de áudio** .
    
- Quando você habilitar ou desabilitar os serviços de audioconferência.
    
- Quando você alterar ou reiniciar o ID de conferência para um usuário configurado para usar as reuniões públicas.
    
- Quando você move o usuário para uma nova ponte de conferência de áudio.
    
- Quando um número de telefone é não atribuído a partir de uma ponte de conferência de áudio. Esse é um cenário complexo que requer etapas adicionais. Para obter mais informações, consulte [alterar as tarifas ou números de Chamada Tarifada livres na sua ponte de conferência de áudio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> [!IMPORTANTE] O MMS atualiza as reuniões somente quando você usa a ponte da Microsoft. Se você estiver usando um provedor de serviços de audioconferência de terceiros, os usuários serão necessário atualizar suas reuniões manualmente. Nesse caso, você pode usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Nem todas as alterações nas configurações de conferência de áudio de um usuário disparam MMS. Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:
  
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
  
A quantidade de tempo que leva para MMS migrar reuniões varia dependendo de quantos usuários são impactados e o número total de Skype para reuniões de negócios ou Microsoft Teams que cada usuário tem no seu calendário. A execução levará pelo menos dez minutos. Embora algumas migrações maiores possam levar até 12 horas, a maioria delas deve ser concluída em uma hora.
  
 **Limitações e possíveis problemas**
  
- Somente o Skype para reuniões de negócios ou Teams da Microsoft que foram agendadas clicando no botão **Adicionar Skype reunião** no Outlook na Web, ou usando o suplemento de reunião Skype para Outlook são migradas. Em outras palavras, se um usuário copiar e colar as informações da reunião online do Skype de uma reunião para uma nova, essa nova reunião não será atualizada.
    
- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
    
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.
    
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
    
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>O que os usuários verão quando o MMS atualizar suas reuniões?

Assim como a ferramenta de migração de reunião, MMS envia atualizações de reunião em nome de usuários. Portanto, a única coisa que os usuários verão é outra round de reunião notificações de aceitação para suas reuniões. Isso pode ser confuso para os usuários, portanto, recomendamos que você notifique os usuários com antecedência não somente quando você migrá-los no local para Skype para Business Online, mas também quando você faz alterações de conferência de áudio que irá disparar MMS.
  
## <a name="managing-mms"></a>Gerenciando o MMS

Você precisa usar o Windows PowerShell para gerenciar o MMS e verificar o status das migrações em andamento. As informações contidas nesta seção pressupõem que você saiba como usar o PowerShell para gerenciar sua organização do Skype for Business. Se você é iniciante no PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Como faço para conferir o status das migrações de reuniões?

Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.
  
Para ver um status resumido de todas as migrações do MMS, execute este comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Ele fornecerá todos os estados de migração em uma exibição tabular, assim:
  
Estado UserCount--<br/> 21 pendente<br/>InProgress 6<br/> 2 com falha <br/> 131 sucedidas
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

O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado conforme necessário. Por exemplo, se você quiser migrar manualmente todas as reuniões ou se você usar um provedor de serviços de audioconferência de terceiros, talvez não seja necessário MMS executando. Você também pode optar por desabilitar o MMS temporariamente. Por exemplo, você talvez esteja fazendo alterações substanciais às definições de serviços de audioconferência para sua organização e você não quer MMS execução autorizada até que todas as alterações são concluídas.
  
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

Você também pode desativar MMS somente para alterações de conferência de áudio. Ele ainda será executado quando um usuário é migrado do Skype para negócios local para Skype para negócios Online. Para verificar o status atual do MMS para atualizações de conferência de áudio, execute o seguinte comando e verifique o valor para o `AutomaticallyMigrateUserMeetings` parâmetro. Se esse parâmetro for definido como true$, MMS é definido para atualizar as reuniões do usuário quando as configurações de serviços de audioconferência são alteradas.
  
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
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
