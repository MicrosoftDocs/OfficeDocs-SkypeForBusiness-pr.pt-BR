---
title: "Alterar os números de telefone na sua ponte de conferência de áudio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Quando você adquire licenças de serviços de audioconferência, a Microsoft está hospedando sua ponte de conferência de áudio para sua organização. A ponte de conferência de áudio oferece check-out de números de telefone de discagem de diferentes locais para que participantes e os organizadores da reunião podem usá-los para ingressar Skype para reuniões de negócios ou Microsoft Teams usando um telefone."
ms.openlocfilehash: 74b719d279a5425479b22e0ba6e57c62217b8658
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Alterar os números de telefone na sua ponte de conferência de áudio

Quando você adquire licenças de **Serviços de audioconferência** , a Microsoft está hospedando sua *ponte de conferência de áudio* para sua organização. A ponte de conferência de áudio oferece check-out de números de telefone de discagem de diferentes locais para que participantes e os organizadores da reunião podem usá-los para ingressar Skype para reuniões de negócios ou Microsoft Teams usando um telefone.
  
Além dos números já atribuídos a sua ponte de conferência, você pode [obter os números de serviço adicionais](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (tarifas e números para ligações gratuitas usados para serviços de audioconferência) de outros locais e, em seguida, atribui-los para a conferência ponte para que você possa Expanda cobertura para seus usuários.
  
> [!NOTE]
> Para poder atribuir/retirar a atribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de '*service*'. Você pode ver o tipo de número é navegando até **voz** > **números de telefone** e procurando na coluna **Tipo de número** . Créditos de comunicações do Office 365 deve ser configurados primeiro, em ordem, para que os usuários discam para a ponte de um número de telefone gratuito. 
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Etapa 1 - atribuir o novo número de telefone para sua ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa.
    
2. Vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **voz** > **números de telefone**.
    
3. Selecione o número de telefone da lista e, no painel de ações, clique em **atribuir**.
    
4. Na página **Atribuir**, clique em **Salvar**.
    
    Apenas um número de Chamada Tarifada do serviço pode ser definido como o número padrão para sua ponte de conferência; **números para ligações gratuitas service não podem ser definidos como o número padrão de sua ponte de conferência**. Se você estiver atribuindo um número de Chamada Tarifada do serviço e você gostaria de defini-la como o novo número padrão para sua ponte de conferência de áudio, selecione **usar este número como padrão**.
    
    > [!NOTE]
    > Depois que tiver sido atribuído um novo número de telefone, mesmo se o número tornaram-se o novo número padrão, o número padrão para usuários existentes não alterará. Para definir as tarifas padrão ou um número de chamada gratuito que é adicionado à reunião do organizador convida, consulte [Defina o telefone convidam números incluídos no](set-the-phone-numbers-included-on-invites.md). 
  
### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Etapa 2 - Alterar os números de telefone padrão que são incluídos nos convites de reunião de usuários (opcional)

Os números de telefone padrão para o usuário são aqueles que estão incluídos na sua reunião convida quando eles agendam uma reunião. Para obter mais informações, consulte [definir o telefone convidam números incluídos no](set-the-phone-numbers-included-on-invites.md).
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **audioconferências** > **usuários** e selecione os usuários na lista.
    
3. Clique em **Editar** no painel de ação.
    
4. Em **número de Chamada Tarifada padrão** ou **número de chamada gratuito padrão**, selecione o número na lista e clique em **Salvar**.
    
Depois que as alterações foram salvas, o novo telefone padrão números serão incluídos na reunião convida de organizadores na próxima vez em que eles agendarem uma nova reunião.
  
### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Etapa 3 - Atualizar convites de reunião existentes de usuários do Meeting Migration Service (opcional)

As próximas duas etapas, você precisará para iniciar o Windows PowerShell.
  
Usando o serviço de migração de reunião, você poderá atualizar opcionalmente convites de reunião que já foram enviados aos usuários em sua organização antes de seus números de telefone padrão foram alterados. Para obter informações adicionais, consulte [configuração backup serviço de migração de reunião (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
- Execute o serviço de migração de reunião (MMS) para os usuários que tiveram seus números de telefone padrão alterados na etapa 2. Para fazer isso, execute o seguinte comando:
    
```
    Start-CsExMeetingMigration user@contoso.com

```

- Você também pode visualizar o status de migração da reunião. Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .
    
```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência


Quando você cancelar a atribuição de um número de telefone uma ponte de conferência, os usuários não poderão ingressar em reuniões usando esse número de telefone mais. Como o número de telefone está mudando, é importante para atualizar todos os usuários que poderia ter um número de telefone como seu número padrão (se houver) e atualizar seus convites de reunião antes que o número de telefone não atribuído da ponte de conferência de áudio existentes. 
  
Se o número de telefone for removido sem atualizar os usuários e suas reuniões, os convites de reunião existentes poderiam conter um número de telefone que não funcionará mais para ingressar nas reuniões.
  
As três primeiras etapas, você precisará para iniciar o Windows PowerShell. Para ver como fazer isso, clique em [para saber como gerenciar com o Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)
  
### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Etapa 1 - Atualizar usuários que terão a atribuição de um de seus números padrão cancelada

Substituir o número de chamada tarifada ou gratuita para todos os usuários que têm o número que deixará de ser o número padrão e iniciar o processo de reagendamento das reuniões. Para isso, execute o seguinte comando:
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Você também pode alterar o tarifas padrão ou gratuito número de usuários no Skype para centro de administração de negócios. No entanto, isso automaticamente não reagendar suas reuniões. 
 
 Para obter informações adicionais, consulte [Defina o telefone convidam números incluídos no](set-the-phone-numbers-included-on-invites.md).

  > [!NOTE]
  > [!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir. 
  
### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell

Todas as reuniões serão ser reagendadas quando não há nenhuma operação no estado *pendente* ou *Em andamento* .
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Etapa 3 - retirar o antigo número de telefone de ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **voz** > **números de telefone**.
    
3. Selecione o número de telefone da lista e, no painel de ações, clique em **não atribuído**.
    
4. Na janela de confirmação, clique em **Sim**.
    
  > [!IMPORTANT]
  > Após um número de telefone não atribuído a partir de uma ponte de conferência de áudio, o número de telefone ficarão mais disponível para os usuários ingressem em reuniões de novos ou existentes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar se o Windows PowerShell está pronto

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
  
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
### <a name="to-start-windows-powershell"></a>Para iniciar o Windows PowerShell

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

Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
### <a name="save-time-or-automate"></a>Economizar tempo ou automatizar

Para economizar tempo ou automatizar esse processo, você pode usar o [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) ou os cmdlets **Set-CsOnlineDialInConferencingUserDefaultNumber** .
  
- Use o cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.
    
  - Para mudar o número de chamada gratuita padrão de um usuário, execute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.
    
    > [!NOTE]
    > Para localizar o BridgeID, use o **Get-CsOnlineDialInConferencingBridge**.
  
  - Para definir 8005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para mudar o número de chamada gratuita padrão de todos os usuários que têm 8005551234 como seu número de chamada gratuita padrão para 8005551239 e reagendar automaticamente suas reuniões, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA como 8005551234 e reagendar automaticamente suas reuniões, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > [!OBSERVAçãO] O local usado acima deve corresponder às informações de contato dos usuários definidas no centro de administração do Office 365. 
  
## <a name="about-windows-powershell"></a>Sobre o Windows PowerShell

O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados
[Alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md)
  