---
title: "Alterar a chamada Tarifada ou números gratuitos de Chamada Tarifada em sua ponte de conferência de áudio"
ms.author: tonysmit
author: tonysmit
ms.date: 11/29/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingRemovePhoneNumberFromBridge
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
description: "Quando você comprar licenças de Conferência de áudio, a Microsoft está hospedando sua ponte de conferência de áudio para a sua organização. A ponte de conferência de áudio fornece números de discagem de locais diferentes para que os participantes e organizadores de reunião podem usá-los para ingressar Skype for Business ou Teams Microsoft reuniões usando um telefone."
---

# Alterar a chamada Tarifada ou números gratuitos de Chamada Tarifada em sua ponte de conferência de áudio

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Quando você comprar licenças de **Conferência de áudio**, a Microsoft está hospedando sua  *ponte de conferência de áudio*  para a sua organização. A ponte de conferência de áudio fornece números de discagem de locais diferentes para que os participantes e organizadores de reunião podem usá-los para ingressar Skype for Business ou Teams Microsoft reuniões usando um telefone.
  
Além dos números de telefone já atribuídos à sua ponte de conferência, você pode [Obtendo números telefônicos de serviço do Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) (Chamada Tarifada e números de chamada gratuita usados para conferência de áudio) de outros locais e em seguida, atribua-las para a conferência ponte para que você possa Expanda cobertura para seus usuários.
  
> [!NOTE]
> Para poder atribuir/cancelar a atribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de ' *serviço*  '. Você pode ver o tipo de número é navegando para **voz** > **números de telefone** e procurando na coluna **Tipo de número**. > O Office 365 comunicações créditos devem ser configurados primeiro, em ordem para que os usuários de discagem para a ponte em um número de chamada gratuita. Consulte [Alterar a chamada Tarifada ou números gratuitos de Chamada Tarifada em sua ponte de conferência de áudio](6403f6d1-c05a-44ab-a6e0-558000e246f4.md). 
  
## Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência

### Etapa 1 - atribuir o novo número de telefone para sua ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa.
    
2. Vá para o **Centro de administração do Office 365** > **centros de administração** > **Skype for Business** > **voz** > **números de telefone**.
    
3. Selecione o número de telefone da lista e, no painel ação, clique em **atribuir**.
    
4. Na página **Atribuir**, clique em **Salvar**.
    
    Apenas um número de Chamada Tarifada serviço pode ser definido como o número padrão para sua ponte de conferência; **números de chamada gratuita do serviço não podem ser definidos como o número padrão de sua ponte de conferência**. Se você estiver atribuindo um número de Chamada Tarifada de serviço e você gostaria de defini-lo como o novo número padrão para sua ponte de conferência de áudio, selecione **usar esse número como padrão**.
    
    > [!NOTE]
    > Depois que um novo número de telefone foi atribuído, mesmo se o número se tornou o novo número padrão, não altere o número padrão para usuários existentes. Para definir Tarifada padrão ou um número de chamada gratuita que é adicionado à reunião de um organizador convida, consulte [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md). 
  
### Etapa 2 - Alterar os números de telefone padrão que são incluídos nos convites de reunião de usuários (opcional)

Os números de telefone padrão de usuário são aqueles que estão incluídos na sua reunião convida quando eles agendarem uma reunião. Para obter mais informações, consulte [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **centros de administração** > **Skype for Business** > **audioconferência** > **usuários** e selecione os usuários na lista.
    
3. Clique em **Editar** no painel de ação.
    
4. Em **número de Chamada Tarifada padrão** ou **número de chamada gratuito padrão**, selecione o número na lista e clique em **Salvar**.
    
Depois que as alterações foram salvas, o novo telefone padrão números serão incluídos na reunião convida dos organizadores da próxima vez em que eles agendarem uma nova reunião.
  
### Etapa 3 - Atualizar convites de reunião existentes de usuários do Meeting Migration Service (opcional)

Para as próximas duas etapas, você precisará iniciar o Windows PowerShell. Para ver como fazer isso, clique [Quer saber como gerenciar com o Windows PowerShell?](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell).
  
Usando o serviço de migração de reunião, você pode atualizar opcionalmente convites de reunião que já foram enviados para usuários de sua organização antes de seus números de telefone padrão foram alterados. Para obter informações adicionais, consulte [Configurando o Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
- Execute o serviço de migração de reunião (MMS) para os usuários que tinham seus números de telefone padrão alterados na etapa 2. Para fazer isso, execute o seguinte comando:
    
```
	Start-CsExMeetingMigration user@contoso.com

```

- Você também pode visualizar o status de migração da reunião. Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .
    
```
	Get-CsMeetingMigrationStatus -SummaryOnly
```

## Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência
<a name="bk_StartPowerShell"> </a>

Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão ingressar em reuniões usando esse número de telefone mais. Como o número de telefone está mudando, é importante para atualizar todos os usuários que podem ter um número de telefone como seu número de padrão (se houver) e para atualizar seus convites de reunião antes do número de telefone é sem alocação da ponte de conferência de áudio existente.
  
Se o número de telefone for removido sem atualizar os usuários e suas reuniões, os convites de reunião existentes poderiam conter um número de telefone que não funcionará mais para ingressar nas reuniões.
  
Para as três primeiras etapas, você precisará iniciar o Windows PowerShell. Para ver como fazer isso, clique [Quer saber como gerenciar com o Windows PowerShell?](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell).
  
### Etapa 1 - Atualizar usuários que terão a atribuição de um de seus números padrão cancelada

Substituir o número de chamada tarifada ou gratuita para todos os usuários que têm o número que deixará de ser o número padrão e iniciar o processo de reagendamento das reuniões. Para isso, execute o seguinte comando:
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

> [!NOTE]
> Dependendo do tamanho de sua organização, isso poderia demorar para concluir. 
  
 **Você também pode alterar a chamada Tarifada padrão ou o número de chamada gratuita de usuários do Skype para o Centro de administração de negócios. No entanto, isso não reagendar automaticamente suas reuniões**. Para obter informações adicionais, consulte[Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
### Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell

Todas as reuniões serão reagendadas quando não há nenhuma operações em estado  *pendente*  ou *Em andamento*  .
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
### Etapa 3 - Cancelar atribuição o antigo número de telefone da ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **centros de administração** > **Skype for Business** > **voz** > **números de telefone**.
    
3. Selecione o número de telefone da lista e, no painel ação, clique em **Cancelar atribuição**.
    
4. Na janela de confirmação, clique em **Sim**.
    
> [!IMPORTANT]
> Depois que um número de telefone é sem alocação de uma ponte de conferência de áudio, o número de telefone já não estará disponível para os usuários ingressem em reuniões de novas ou existentes. 
  
## Quer saber como gerenciar com o Windows PowerShell?
<a name="bk_PowerShell"> </a>

### Para verificar se o Windows PowerShell está pronto

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
  
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
### Para iniciar o Windows PowerShell

 **Iniciar uma sessão do Windows PowerShell**
  
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
### Economizar tempo ou automatizar

Para economizar tempo ou automatizar esse processo, você pode usar o [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) ou os cmdlets do **Set-CsOnlineDialInConferencingUserDefaultNumber**.
  
- Use o cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.
    
  - Para mudar o número de chamada gratuita padrão de um usuário, execute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.
    
    > [!NOTE]
    > Nota:Para saber qual é o BridgeID, use **Get-CsOnlineDialInConferencingBridge**.
  
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
    > O local usado acima deve corresponder às informações de contato dos usuários definidas no centro de administração do Office 365. 
  
### Saiba mais

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

