---
title: "Configurando o Meeting Migration Service (MMS)"
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
description: "Serviço de migração (MMS) da reunião é um Skype para o serviço de negócios que é executado em segundo plano e atualizará automaticamente o Skype para reuniões de negócios e Teams da Microsoft para os usuários. MMS foi projetado para eliminar a necessidade de usuários para executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft."
---

# Configurando o Meeting Migration Service (MMS)

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/031f09c0-9d2a-487a-b6db-b5d4bed6d16a). 
  
Serviço de migração (MMS) da reunião é um Skype para o serviço de negócios que é executado em segundo plano e atualizará automaticamente o Skype para reuniões de negócios e Teams da Microsoft para os usuários. MMS foi projetado para eliminar a necessidade de usuários para executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft.
  
 **Requisitos**
  
O MMS exige que as caixas de correio dos organizadores da reunião estejam no Exchange Online.
  
 **Cenários principais**
  
O MMS atualiza as reuniões do Skype para os usuários nestes dois cenários principais: 
  
- Quando o usuário é migrado de local Skype for Business Server para Skype for Business Online.
    
- Quando um administrador altera as configurações do usuário audioconferência que exijam a atualização das informações de conferência de áudio em reuniões do usuário.
    
 **Cenários comuns em que o MMS não pode ser usado**
  
Veja alguns cenários comuns que podem se aplicar a você. Todos eles dão suporte à migração. Porém, o MMS não será executado nesses cenários e você deverá usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) em seu lugar.
  
- As caixas de correio do usuário estão no Exchange Server local
    
- Usando um provedor de audioconferência terceirizado
    
- Migrando usuários do Skype for Business Online para servidor do Skype no local
    
## Atualizando reuniões quando um usuário local migra para o Skype for Business Online

Este é o cenário mais comum onde MMS podem ajudar a criar uma transição suave para seus usuários. Quando um usuário é migrado de um local Skype for Business Server para Skype for Business Online, MMS detecta o novo usuário e examinará o calendário do usuário do Skype para reuniões de negócios e Teams da Microsoft. As reuniões futuras serão atualizadas com as novas informações para esse usuário.
  
### Se você está usando atualmente Skype Server 2015 para conferência de áudio

Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:
  
- Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.
    
- Atribua a licença de **Conferência de áudio** para o usuário antes de executar o cmdlet `Move-CSUser` para migrar o usuário. Isso ocorre porque MMS também atualiza reuniões quando as configurações de conferência de áudio são alteradas para um usuário. Se você não atribuir a licença primeiro, MMS atualizará todas as reuniões novamente quando você atribuir a licença.
    
### Se estiver usando um provedor de serviços de audioconferência (ACP, Audio Conferencing Provider) de terceiros

Com um ACP de terceiros, ou não é executado MMS depende de configurações de conferência de áudio da sua organização. Você pode optar por substituir os números de discagem de seu ACP automaticamente quando você atribui um usuário uma licença de **Conferência de áudio**. Por outro lado, talvez você precise impedir que isso aconteça e manter os números de discagem de seu ACP. Para ver a configuração da sua organização, execute o seguinte comando do Windows PowerShell e verificar o valor do parâmetro  `AutomaticallyReplaceAcpProvider`. Se precisar de ajuda com o PowerShell, consulte a seção de [Usando o PowerShell para gerenciar a organização do Skype for Business](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) no final deste artigo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Se o valor do parâmetro for $true, MMS será executada quando um usuário recebe uma licença de **Conferência de áudio** e atualizar suas reuniões. Os números de discagem de seu ACP são mantidos até que a licença de **Conferência de áudio** está atribuída.
    
- Se o valor do parâmetro for $false, MMS não atualize as reuniões mesmo se um usuário recebe uma licença de **Conferência de áudio**. Os números de discagem de seu ACP são mantidos até que o usuário é provisionado manualmente para conferência de áudio no Skype para o Centro de administração de negócios ou usando o Windows PowerShell.
    
## Atualizando reuniões quando alterar configurações de conferência de áudio de um usuário

MMS atualizará um Skype existente para reuniões de negócios e Teams Microsoft nos seguintes casos:
  
- Quando você atribuir ou remover a licença de **Conferência de áudio**.
    
- Quando você ativar ou desativar a conferência de áudio.
    
- Quando você altera ou redefinir o ID de conferência para um usuário configurado para usar reuniões públicos.
    
- Quando você move o usuário para uma nova ponte de conferência de áudio.
    
- Quando um número de telefone está sem alocação de uma ponte de conferência de áudio. Este é um cenário complexo que requerem etapas adicionais. Para obter mais informações, consulte [Alterar a chamada Tarifada ou números gratuitos de Chamada Tarifada em sua ponte de conferência de áudio](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS só atualiza reuniões quando você estiver usando a ponte da Microsoft. Se você estiver usando um provedor de audioconferência terceirizado, os usuários precisará atualizar suas reuniões manualmente. Nesse caso, você pode usar a [Ferramenta de migração de reunião](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Nem todas as alterações às configurações de conferência de áudio de um usuário disparam MMS. Especificamente, as seguintes dois alterações não resultará em MMS atualizando reuniões:
  
- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
    
- Quando você altera a URL da reunião da organização usando o comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## O que acontece quando o MMS atualiza as reuniões?

Quando o MMS detecta que as reuniões de um usuário precisam ser atualizadas, ele faz o seguinte:
  
1. Identificar todos os Skype para reuniões de negócios e Teams Microsoft o usuário tiver programado no futuro
    
  - Qualquer Skype para empresas ou Teams Microsoft reuniões ocorridas antes durante a execução de MMS são ignoradas
    
  - Somente as reuniões organizadas pelo usuário são atualizadas
    
2. Substitua o bloco de informações da reunião online nos detalhes da reunião
    
3. Envie atualizações para todos os destinatários da reunião em nome do organizador
    
 **Quanto tempo levará para o MMS ser executado?**
  
A quantidade de tempo que demora MMS migrar reuniões varia dependendo de quantos usuários são afetados e o número total de Skype para empresas ou Teams Microsoft reuniões que cada usuário tem o calendário dela. No mínimo, levará 10 minutos para ser executado. Enquanto alguns grandes migrações podem levar até 12 horas, a maioria das migrações devem ser concluída dentro de 1 hora.
  
 **Limitações e possíveis problemas**
  
- Somente o Skype para empresas ou Teams Microsoft reuniões que foram agendadas clicando no botão **Adicionar Skype reunião** no Outlook na Web ou usando o suplemento de reunião do Skype do Outlook são migradas. Em outras palavras, se um usuário copia e cola as informações de reunião online do Skype de uma reunião para uma nova reunião, essa nova reunião não será atualizado.
    
- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado. 
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
    
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.
    
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas. 
    
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.
    
### O que os usuários verão quando o MMS atualizar suas reuniões?

Como a ferramenta de migração de reunião, MMS envia atualizações de reunião em nome de usuários. Portanto, a única coisa que os usuários verão é outra round de notificações de aceitação para suas reuniões da reunião. Isso pode ser confuso para os usuários, portanto, é recomendável que você notificar os usuários com antecedência não somente quando você migra-los do local para o Skype for Business Online, mas também quando você faz alterações de conferência de áudio que acionará MMS.
  
## Gerenciando o MMS

Você precisa usar o Windows PowerShell para gerenciar o MMS e verificar o status das migrações em andamento. As informações contidas nesta seção pressupõem que você saiba como usar o PowerShell para gerenciar sua organização do Skype for Business. Se você é iniciante no PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) no final deste artigo.
  
### Como faço para conferir o status das migrações de reuniões?

Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.
  
Para ver um status resumido de todas as migrações do MMS, execute este comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Ele fornecerá todos os estados de migração em uma exibição tabular, assim:
  
Estado ContadoUsuário----- ---------Pendente 21EmAndamento 6Falhou 2Bem-sucedido 131
> [!IMPORTANT]
> Se houver migrações com falha, tome as medidas necessárias para resolver os problemas assim que possível. As pessoas não conseguirão discar para as reuniões organizadas por esses usuários até que você os resolva. Veja a seção [O que devo fazer se ocorrer um erro?](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#Troubleshooting) para obter mais informações.
  
Para ver detalhes completos de todas as migrações de um período específico, você pode usar os parâmetros  `StartTime` e `EndTime`. Por exemplo, o comando a seguir retornará detalhes completos de todas as migrações ocorridas de 1º a 8 de outubro de 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Talvez você também queira conferir o status da migração de um usuário específico. Para isso, use o parâmetro  `UserId`. Por exemplo, o comando a seguir retornará o status do usuário ashaw@contoso.com:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### O que devo fazer se ocorrer um erro?
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
    
### Habilitando e desabilitando o MMS
<a name="Troubleshooting"> </a>

MMS é ativada por padrão para todas as organizações, mas ele pode ser desabilitado conforme necessário. Por exemplo, se você deseja migrar manualmente todas as reuniões ou se você usar um provedor de audioconferência terceirizado, talvez não seja necessário MMS executando. Você também pode optar por desativar temporariamente MMS. Por exemplo, você pode fazer alterações substanciais para as configurações de conferência de áudio para a sua organização e não quiser MMS executar até que todas as alterações são concluídas.
  
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

### Ativando e desativando MMS somente para alterações de conferência de áudio
<a name="Troubleshooting"> </a>

Você também pode desativar MMS somente para alterações de audioconferência. Ela ainda serão executadas quando um usuário é migrado do Skype para Business no local para Skype for Business Online. Para verificar o status atual de MMS atualizações de conferência de áudio, execute o seguinte comando e verifique o valor para o parâmetro  `AutomaticallyMigrateUserMeetings` . Se esse parâmetro for definido para$true, MMS está definido para atualizar reuniões do usuário quando as configurações de conferência de áudio são alteradas.
  
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

### Como executo a Migração de Reunião manualmente para um usuário?
<a name="Troubleshooting"> </a>

Além das migrações de reunião automáticos, você também pode executar a migração de reunião manualmente para um usuário, execute o cmdlet **Start-CsExMeetingMigration**. Esse cmdlet adiciona o usuário na fila de migração de reunião. Serviço de migração de reunião lerá a solicitação do usuário e migrar suas reuniões. Você pode verificar o status de migração de reunião por cmdlet **Get-CsMeetingMigrationStatus**.
  
Este é um exemplo que inicia a migração da reunião para o usuário ashaw@contoso.com:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## Usando o PowerShell para gerenciar a organização do Skype for Business
<a name="WPSInfo"> </a>

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
  
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
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
  

