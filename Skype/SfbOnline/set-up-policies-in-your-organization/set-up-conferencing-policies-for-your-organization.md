---
title: Configurar políticas de conferência para sua organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.'
ms.openlocfilehash: 46e22191875709f13936db395563eb9f7326300f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884530"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Configurar políticas de conferência para sua organização

Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.
  
É importante que você mantenha o controle sobre conferências e suas configurações. Em alguns casos, pode haver preocupações de segurança: por padrão, qualquer pessoa, inclusive usuários não autenticados, pode participar de reuniões e salvar nenhum dos slides ou folhetos distribuídos durante essas reuniões. Além disso, pode haver questões legais ocasionais. Por exemplo, por padrão, os participantes da reunião têm permissão para fazer anotações no conteúdo compartilhado; No entanto, essas anotações não são salvas quando a reunião é arquivada. Se sua organização é necessária para manter um registro de todas as comunicações eletrônicas, você talvez queira desabilitar as anotações. 
  
No Skype para Business Online, as conferências são gerenciadas usando políticas de conferência. Diretivas de conferência determinam os recursos e capacidades que podem ser usadas em uma conferência, incluindo tudo de estarem ou não a conferência pode incluir IP, áudio e vídeo para o número máximo de pessoas que podem participar de uma reunião. Políticas de conferência podem ser configuradas no escopo global ou no escopo por usuário. Isso oferece aos administradores uma enorme flexibilidade quando se trata de decidir quais recursos serão disponibilizados para os quais usuários.
  
Configurações de diretiva que podem ser configuradas no momento em que uma diretiva é criada ou você pode usar o cmdlet **Set-CsConferencingPolicy** para modificar as configurações de uma diretiva existente.
  
## <a name="set-your-conferencing-policies"></a>Definir suas políticas de conferência

> [!NOTE]
> Para todas as configurações de diretiva de conferência no Skype para Business Online, você deve usar o Windows PowerShell e você **não pode usar** o **Skype para centro de administração de negócios**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
    Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Iniciar uma sessão do Windows PowerShell**
    
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para o Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquear transferências de arquivo e compartilhamento de área de trabalho durante as reuniões

- Para criar uma nova política para essas configurações, execute:
  > 
  > ```
  > New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  > ```
  > Consulte obter mais informações sobre o cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Para conceder a nova política que você criou para todos os usuários em sua organização, execute:
  > 
  > ```
  > Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  > ```
  > Consulte obter mais informações sobre o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
  Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar as configurações para seus usuários.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquear a gravação de conferências e impedir que os participantes da reunião anônimo

- Para criar uma nova política para essas configurações, execute: 
  > 
  > ```
  > New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  > ```
  > Consulte obter mais informações sobre o cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Para conceder a nova política que você criou para Mármore Amos, execute:
  > 
  > ```
  >  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  > ```
  > Consulte obter mais informações sobre o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar as configurações para seus usuários.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Impedir que participantes anônimos gravem reuniões e que usuários externos salvem o conteúdo da reunião

- Para criar uma nova política para essas configurações, execute:  
  > 
  > ```
  > New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  > ```
  > Consulte obter mais informações sobre o cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Para conceder a nova política que você criou para todos os usuários em sua organização, execute:
    
> 
>   ```
>   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
>   ```

Consulte obter mais informações sobre o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar as configurações para seus usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Transferências de arquivos ponto a ponto de bloqueio](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

  
 
