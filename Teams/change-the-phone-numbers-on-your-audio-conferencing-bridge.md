---
title: Alterar os números de telefone de sua ponte de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
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
description: Quando você adquire licenças de serviços de audioconferência, a Microsoft está hospedando sua ponte de conferência de áudio para sua organização. A ponte de conferência de áudio oferece check-out de números de telefone de discagem de diferentes locais para que participantes e os organizadores da reunião podem usá-los para ingressar Skype para reuniões de negócios ou Microsoft Teams usando um telefone.
ms.openlocfilehash: 26a6e8dcb467ceea990b974d1687e0a5998eeb4b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372238"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Alterar os números de telefone de sua ponte de audioconferência

Quando você adquire licenças de **Serviços de audioconferência** , a Microsoft está hospedando sua *ponte de conferência de áudio* para sua organização. A ponte de conferência de áudio oferece check-out de números de telefone de discagem de diferentes locais para que participantes e os organizadores da reunião podem usá-los para ingressar Skype para reuniões de negócios ou Microsoft Teams usando um telefone.
  
Além dos números já atribuídos a sua ponte de conferência, você pode [obter os números de serviço adicionais](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (tarifas e números para ligações gratuitas usados para serviços de audioconferência) de outros locais e, em seguida, atribui-los para a conferência ponte para que você possa Expanda cobertura para seus usuários.
  
> [!NOTE]
> Para poder atribuir/retirar a atribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de '*service*'. Você pode ver o tipo de número é navegando até **voz** > **números de telefone** e procurando na coluna **Tipo de número** . Créditos de comunicações do Office 365 deve ser configurados primeiro, em ordem, para que os usuários discam para a ponte de um número de telefone gratuito.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Etapa 1 - atribuir o novo número de telefone para sua ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa.

2. Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes & Skype** > **portal herdada** > **voz** > **números de telefone**.

3. Selecione o número de telefone da lista e, no painel de ações, clique em **atribuir**.

4. Na página **Atribuir**, clique em **Salvar**.

    Apenas um número de Chamada Tarifada do serviço pode ser definido como o número padrão para sua ponte de conferência; **números para ligações gratuitas service não podem ser definidos como o número padrão de sua ponte de conferência**. Se você estiver atribuindo um número de Chamada Tarifada do serviço e você gostaria de defini-la como o novo número padrão para sua ponte de conferência de áudio, selecione **usar este número como padrão**.

    > [!NOTE]
    > [!OBSERVAçãO] Após a atribuição do novo número de telefone, mesmo que ele se torne o novo número padrão, o número padrão dos usuários existentes não mudará. Para definir as tarifas padrão ou um número de chamada gratuito que é adicionado à convites de reunião do organizador, consulte as instruções para [As equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou as instruções para [Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites). 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Etapa 2 - Alterar os números de telefone padrão que são incluídos nos convites de reunião de usuários (opcional)

Os números de telefone padrão para o usuário são aqueles incluídos em seus convites de reunião quando agendam uma reunião. Para obter mais informações, consulte [definir o telefone números incluídos no convidam em equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir o telefone números incluídos no convidam no Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes & Skype** > **portal herdada** > **audioconferências** > **usuários** e selecione os usuários na lista.

3. Clique em **Editar** no painel de ação.

4. Em **número de Chamada Tarifada padrão** ou **número de chamada gratuito padrão**, selecione o número na lista e clique em **Salvar**.

Depois que as alterações foram salvas, o novo telefone padrão números serão incluídos na reunião convida de organizadores na próxima vez em que eles agendarem uma nova reunião.

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Etapa 3 - Atualizar convites de reunião existentes de usuários do Meeting Migration Service (opcional)

As próximas duas etapas, você precisará para iniciar o Windows PowerShell.
  
Usando o serviço de migração de reunião, você poderá atualizar opcionalmente convites de reunião que já foram enviados aos usuários em sua organização antes de seus números de telefone padrão foram alterados. Para obter informações adicionais, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Execute o serviço de migração de reunião (MMS) para os usuários que tiveram seus números de telefone padrão alterados na etapa 2. Para isso, execute o seguinte comando:

```
    Start-CsExMeetingMigration user@contoso.com
```

- Você também pode visualizar o status de migração da reunião. Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência


Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão mais ingressar nas reuniões usando aquele número de telefone. Como o número de telefone está mudando, é importante para atualizar todos os usuários que poderia ter um número de telefone como seu número padrão (se houver) e atualizar seus convites de reunião antes que o número de telefone não atribuído da ponte de conferência de áudio existentes.

Se o número de telefone for removido sem atualizar os usuários e suas reuniões, os convites de reunião existentes poderiam conter um número de telefone que não funcionará mais para ingressar nas reuniões.

Para as primeiras três etapas, você deverá iniciar o Windows PowerShell. Para ver como fazer isso, clique em [para saber como gerenciar com o Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Etapa 1 - Atualizar usuários que terão a atribuição de um de seus números padrão cancelada

Substituir o número de chamada tarifada ou gratuita para todos os usuários que têm o número que deixará de ser o número padrão e iniciar o processo de reagendamento das reuniões. Para isso, execute o seguinte comando:

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Você também pode alterar o tarifas padrão ou gratuito número de usuários no Skype para centro de administração de negócios. No entanto, isso automaticamente não reagendar suas reuniões. 
 
 Para obter informações adicionais, consulte [definir o telefone números incluídos no convidam em equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir o telefone números incluídos no convidam no Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > [!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell

Todas as reuniões serão ser reagendadas quando não há nenhuma operação no estado *pendente* ou *Em andamento* .

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Etapa 3 - retirar o antigo número de telefone de ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes & Skype** > **portal herdada** > **voz** > **números de telefone**.

3. Selecione o número de telefone da lista e, no painel de ações, clique em **não atribuído**.

4. Na janela de confirmação, clique em **Sim**.

   > [!IMPORTANT]
   > Após um número de telefone não atribuído a partir de uma ponte de conferência de áudio, o número de telefone ficarão mais disponível para os usuários ingressem em reuniões de novos ou existentes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar se o Windows PowerShell está pronto

 Estas etapas Verifique que você está executando o Windows PowerShell versão 3.0 ou superior.

1. Digite o **Menu Iniciar** > **do Windows PowerShell**.

2. Digite _Get-Host_ na janela do **Windows PowerShell** para verificar a versão.

3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.

4. Você também precisará instalar o módulo do Windows PowerShell para Skype para Business Online que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype para negócios Online. Este módulo só tem suporte em computadores de 64 bits e pode ser baixado do Microsoft Download Center em um [Módulo do Windows PowerShell para Skype para negócios Online](https://go.microsoft.com/fwlink/?LinkId=294688).
Se for solicitado, reinicie o seu computador.

Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

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

Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Poupe tempo e automatizar

Para poupar tempo automatizando esse processo, você pode usar o [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou os cmdlets **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.

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

Com o Windows PowerShell, você pode gerenciar usuários e o que eles são ou não têm permissão para fazer. Windows PowerShell pode ajudá-lo a gerenciar o Office 365 e Skype para negócios Online usando um único ponto de administração que pode simplificar o seu trabalho diário, especialmente quando você acaba de criar várias tarefas fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados
[Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md)
