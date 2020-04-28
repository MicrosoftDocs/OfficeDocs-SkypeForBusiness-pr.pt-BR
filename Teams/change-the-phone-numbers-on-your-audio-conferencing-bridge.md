---
title: Alterar os números de telefone na ponte de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Conheça as etapas necessárias para atribuir um novo número de telefone de serviço à sua ponte de conferência para expandir a cobertura para seus usuários.
ms.openlocfilehash: d22e3c475ae80b7c6aecb89e9e6487c8db38ab1e
ms.sourcegitcommit: 3ef5c913318fdeeaa8c55caab07c2f8224eae2b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43898146"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Alterar os números de telefone em sua ponte de Audioconferência

Quando você compra licenças de **audioconferência** , a Microsoft está hospedando sua ponte de conferência de áudio para sua organização. A ponte de audioconferência fornece números de telefone de discagem de locais diferentes para que os organizadores da reunião e os participantes possam usá-los para ingressar em reuniões do Skype for Business ou do Microsoft Teams usando um telefone.
  
Além dos números de telefone já atribuídos à sua ponte de conferência, você pode [obter números de serviço adicionais](/microsoftteams/getting-service-phone-numbers) (números de chamada tarifada e de chamada gratuita usados para videoconferências) de outros locais e atribuí-los à ponte de conferência para que você possa expandir a cobertura para seus usuários.
  
> [!NOTE]
> Para poder atribuir/cancelar a atribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de "*serviço*". Você pode ver o tipo de número ao navegar para números de **Voice** > **telefone** de voz no portal herdado e procurar na coluna **tipo de número** . Os créditos de comunicações do Office 365 devem ser configurados primeiro para que os usuários disquem para a ponte em um número de chamada gratuita.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Etapa 1-atribuir o novo número de telefone à sua ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa.

2. Vá para **Centro** > de administração do Microsoft 365 Teams**centers** > Administration**Teams &** > **números de telefone**de**voz** > do**portal** > herdado do Skype

3. Selecione o número de telefone na lista e, no painel Ação, clique em **atribuir**.

4. Na página **Atribuir**, clique em **Salvar**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Etapa 2-alterar o número de telefone padrão da sua ponte de conferência (opcional)

O número de telefone padrão da sua ponte de conferência define a identificação de chamadas que será usada quando uma chamada de saída for feita por um participante ou pelo organizador dentro de uma reunião.

Somente um número de chamada de serviço pode ser definido como o número padrão para a sua ponte de conferência; **números de chamada gratuita do serviço não podem ser definidos como o número padrão de sua ponte de conferência**. Se você estiver atribuindo um número de chamada de serviço e quiser defini-lo como o novo número padrão para a sua ponte de audioconferência, execute estas etapas:

1. Entre no Office 365 com sua conta corporativa.

2. Vá para **Centro** > **Admin centers** > de administração do Microsoft 365 Team centers**Teams & reuniões do Skype** > **reuniões** > **conferência**.

3. Realce o número de chamada de serviço que você deseja configurar como padrão.

4. Selecione **Definir como padrão**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Etapa 3-alterar os números de telefone padrão que estão incluídos nos convites de reunião de usuários (opcional)

Os números de telefone padrão de um usuário são aqueles que estão incluídos nos convites de reunião quando eles agendam uma reunião. Para obter mais informações, incluindo como os números de telefone padrão são atribuídos para novos usuários, consulte [definir os números de telefone incluídos nos convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir os números de telefone incluídos nos convites no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Entre com sua conta corporativa ou de estudante.

2. Vá para o & **centro de administração do 365** > **de administração** > do centro de administração do,**usuários**de**videoconferência** > **do** > **portal** > herdado do Skype e selecione os usuários na lista.

3. Clique em **Editar** no painel de ação.

4. Em **número de chamada padrão** ou **número de chamada gratuita padrão**, selecione o número na lista e clique em **salvar**.

Depois que as alterações forem salvas, os novos números de telefone padrão serão incluídos nos convites de reunião dos organizadores na próxima vez que agendarem uma nova reunião.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Etapa 4-atualizar os convites de reunião existentes de usuários usando o serviço de migração de reunião (opcional)

Para as próximas duas etapas, será necessário iniciar o Windows PowerShell.
  
Se você atualizou os números de telefone padrão que estão incluídos nos convites de reunião para alguns ou todos os seus usuários, você pode, opcionalmente, atualizar convites de reunião que já foram enviados para os usuários de sua organização antes de os seus números de telefone padrão terem sido alterados usando o serviço de migração de reunião. Para obter informações adicionais, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Execute o serviço de migração de reunião (MMS) para os usuários que tiveram seus números de telefone padrão alterados na etapa 2. Para isso, execute o seguinte comando:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Você também pode visualizar o status de migração da reunião. Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência


Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão mais ingressar nas reuniões usando aquele número de telefone. Como o número de telefone está mudando, é importante atualizar todos os usuários que podem ter um número de telefone como número padrão (se houver) e atualizar seus convites de reunião existentes antes que o número de telefone seja reatribuído da ponte de audioconferência.

Se o número de telefone for removido sem Atualizar os usuários e suas reuniões, os convites de reunião existentes poderão conter um número de telefone que não funcionará para ingressar em suas reuniões.

Para as primeiras três etapas, você deverá iniciar o Windows PowerShell. Para ver como fazer isso, clique em [deseja saber como gerenciar com o Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Etapa 1: atualizar os usuários que têm o número de telefone para serem reatribuídos como um dos números padrão

Substitua o número de chamada tarifada ou gratuita padrão de todos os usuários que tenham o número a ser atribuído como um número padrão e inicie o processo de reagendar suas reuniões. Para isso, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Você também pode alterar o número de chamada tarifada ou gratuita padrão de usuários no centro de administração do Skype for Business. No entanto, isso não reagendará automaticamente suas reuniões. 
 
 Para obter mais informações, consulte [definir os números de telefone incluídos nos convites do Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir os números de telefone incluídos nos convites no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > [!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell

Todas as reuniões serão reagendadas quando não houver operações no estado *pendente* ou *em andamento* .

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Etapa 3-cancelar a atribuição do número de telefone antigo da ponte de audioconferência

1. Entre com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do 365 do centro** > **Admin centers** > de administração do Microsoft &**números de telefone**de**voz** > do**portal** > herdado**do Skype** > .

3. Se o número de telefone for um número de chamada gratuita, selecione o número de telefone na lista e, no painel Ação, clique em **Cancelar atribuição**. Se o número de telefone for um número de chamada tarifada, entre em contato com o [suporte da Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) para que o número de telefone não seja atribuído.

4. Se o número de telefone for um número de chamada gratuita, clique em **Sim** na janela de confirmação.

   > [!IMPORTANT]
   > Após a atribuição de um número de telefone de uma ponte de audioconferência, o número de telefone não estará mais disponível para que os usuários ingressem em reuniões novas ou existentes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar se o Windows PowerShell está pronto

 Estas etapas verificam se você está executando o Windows PowerShell versão 3,0 ou posterior.

1. Digite **menu** > iniciar**Windows PowerShell**.

2. Digite _Get-Host_ na janela do **Windows PowerShell** para verificar a versão.

3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.
Reinicie o computador quando for solicitado.

4. Você também precisa instalar o módulo do Windows PowerShell para o Skype for Business online que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online. Este módulo tem suporte apenas em computadores de 64 bits e pode ser baixado do centro de download da Microsoft no [módulo do Windows PowerShell para Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=294688).
Se for solicitado, reinicie o seu computador.

Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Para iniciar o Windows PowerShell

 **Iniciar uma sessão do Windows PowerShell**

1. No **Menu Iniciar** > **Windows PowerShell**.

2. Na janela do **Windows PowerShell** , conecte-se ao seu Microsoft 365 ou ao Office 365 executando:

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou conectar-se [ao Skype for Business online usando o Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Economize tempo e automatize

Para poupar tempo automatizando esse processo, você pode usar os cmdlets [set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou **set-CsOnlineDialInConferencingUserDefaultNumber** .

- Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.

  - Para mudar o número de chamada gratuita padrão de um usuário, execute:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.

    > [!NOTE]
    > Para localizar o Bridgeid, use **Get-CsOnlineDialInConferencingBridge**.

  - Para definir 8005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para mudar o número de chamada gratuita padrão de todos os usuários que têm 8005551234 como seu número de chamada gratuita padrão para 8005551239 e reagendar automaticamente suas reuniões, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA como 8005551234 e reagendar automaticamente suas reuniões, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > O local usado acima precisa corresponder às informações de contato do (s) usuário (s) definido (s) no centro de administração do Microsoft 365.

## <a name="troubleshooting"></a>Solução de problemas

**O botão Cancelar atribuição não está disponível**

Você deseja cancelar a atribuição de um número, mas o botão não está disponível e, se ao passar o mouse sobre ele, você será redirecionado para contatar o suporte com a seguinte mensagem _"os números padrão ou compartilhados podem possível ser cancelados na ponte. Para cancelar a atribuição de números de chamada dedicada, entre em contato com o suporte._".

Para obter mais informações sobre a (s) ponte (s), execute o seguinte PowerShell:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

O resultado, além de outras informações, como identidade, nome e região, também devem conter o DefaultServiceNumber.

**Exemplo**, para cancelar a atribuição, o DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Sobre o Windows PowerShell

Com o Windows PowerShell você pode gerenciar usuários e o que eles estão ou não podem fazer. O Windows PowerShell pode ajudá-lo a gerenciar o Office 365 e o Skype for Business online usando um único ponto de administração que pode simplificar seu trabalho diário, especialmente quando você tem várias tarefas para fazer isso. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados
[Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md)
