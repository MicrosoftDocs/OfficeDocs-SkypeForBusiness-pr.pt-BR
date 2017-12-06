---
title: "Configurar as políticas de conferência para sua organização"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
description: "Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar."
---

# Configurar as políticas de conferência para sua organização

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](9957722b-b542-49ad-8ec8-5569df7fb08b.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/9957722b-b542-49ad-8ec8-5569df7fb08b). 
  
Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.
  
É importante para você manter controle sobre configurações de conferência e conferências. Em alguns casos, pode haver problemas de segurança: por padrão, qualquer pessoa, inclusive usuários não autenticados, pode participar de reuniões e salvar qualquer um dos slides ou folhetos distribuídos durante essas reuniões. Além disso, pode haver eventuais questões legais. Por exemplo, por padrão, os participantes da reunião são permitidos para fazer anotações na conteúdo compartilhado; No entanto, essas anotações não são salvas quando a reunião é arquivada. Se sua organização é necessária para manter o registro de todas as comunicações eletrônicas, talvez você queira desabilitar anotações.
  
No Skype for Business Online, conferências são gerenciadas usando diretivas de conferência. Políticas de conferência determinam os recursos e funcionalidades que podem ser usadas em uma conferência, incluindo desde ou não a conferência pode incluir IP áudio e vídeo para o número máximo de pessoas que podem participar de uma reunião. Políticas de conferência podem ser configuradas no escopo global ou no escopo por usuário. Isso fornece aos administradores imensa flexibilidade quando se trata de decidir quais recursos estarão disponíveis aos quais usuários.
  
Configurações de política podem ser definidas no momento em que uma diretiva é criada ou você pode usar o cmdlet **Set-CsConferencingPolicy** para modificar as configurações de uma política existente.
  
## Definir suas políticas de conferência

> [!NOTE]
> Para todas as configurações de política de conferência em Skype for Business Online, você deve usar o Windows PowerShell e você **não pode usar** o **Skype para o Centro de administração de negócios**. 
  
### Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
    Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar uma sessão do Windows PowerShell**
    
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
    
### Bloquear transferências de arquivo e compartilhamento de área de trabalho durante as reuniões

- Para criar uma nova política para essas configurações, execute:
    
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```

    Veja mais no cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Para conceder a nova política que você criou para todos os usuários em sua organização, execute:
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```

    Veja mais no cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações a política existente e, em seguida, use o cmdlet[Conceder-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar a configurações para seus usuários.
  
### Bloquear a gravação de conferências e impedir que os participantes da reunião anônima

- Para criar uma nova política para essas configurações, execute:
    
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```

    Veja mais no cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Para conceder a nova política que você criou para Amos Mármore, execute:
    
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```

    Veja mais no cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações a política existente e, em seguida, use o cmdlet[Conceder-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar a configurações para seus usuários.
  
### Impedir que participantes anônimos gravem reuniões e que usuários externos salvem o conteúdo da reunião

- Para criar uma nova política para essas configurações, execute:
    
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```

    Veja mais no cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Para conceder a nova política que você criou para todos os usuários em sua organização, execute:
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

    Veja mais no cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações a política existente e, em seguida, use o cmdlet[Conceder-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar a configurações para seus usuários.
  
## Quer saber mais sobre o Windows PowerShell?

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
  

