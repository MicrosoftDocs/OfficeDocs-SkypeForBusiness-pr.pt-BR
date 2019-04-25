---
title: Definir a identificação de chamadas para um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
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
- Calling Plans
description: The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going How can caller ID be used in your organization.
ms.openlocfilehash: e9d2cced647eef2f4db7729c4446068a19000176
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229733"
---
# <a name="set-the-caller-id-for-a-user"></a>Definir a identificação de chamadas para um usuário
The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Você não pode bloquear as chamadas recebidas atualmente no Skype for Business Online. 
  
Há duas configurações que você pode alterar:
  
> [!NOTE]
> [!OBSERVAçãO] Isso **não é** para organizações locais com o Lync ou o Skype for Business Server.
  
- **Mudar a ID de chamadas de saída** Você pode substituir a ID de chamadas de um usuário (que, por padrão, é seu número de telefone) por outro número de telefone. Por exemplo, você pode mudar a ID de chamadas do usuário de seu número de telefone para o número de telefone principal de sua empresa ou alterar a ID de Linha de Chamada do usuário de seu número de telefone para o número de telefone principal do departamento jurídico. Você pode mudar o número de ID de chamadas para o número de qualquer **serviço** online (chamada tarifada ou gratuita).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se você desejar usar o parâmetro  _Service_, especifique um número de serviço válido.
  
- **Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.
    
- **Bloquear seu ID de chamadas de entrada** Você pode bloquear um usuário receba a ID do chamador em qualquer chamadas PSTN de entrada.
    
> [!IMPORTANT]
> [!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas). 
  
Por padrão, essas configurações de ID de chamadas são **desativadas**. Isso significa que o número de telefone do usuário do Skype for Business Online pode ser visto quando o usuário faz uma chamada para um telefone PSTN.
  
Para saber mais sobre essas configurações e como você pode usá-las, clique [Como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Definir as configurações de política de ID de chamadas

> [!NOTE]
> Para todas as configurações de ID do chamador no Skype para Business Online, você deve usar o Windows PowerShell e você **não pode usar** o **Skype para centro de administração de negócios**. 
  
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
   > 
   ```
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para o Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Veja todas as configurações de ID de chamadas em sua organização

- Para exibir todas as configurações de diretiva de ID do chamador em sua organização, execute:

  ```
  Get-CsCallingLineIdentity |fl
  ```
  Consulte mais detalhes e exemplos para [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Criar uma nova política de ID de chamadas para sua organização


- Para criar uma nova política de ID de chamador que define a ID de chamador como anônimo, execute:
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.

  Consulte mais detalhes e exemplos para [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
- Para aplicar a nova política que você criou a Mármore Amos, execute:
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) para aplicar as configurações para os usuários.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Defina a política para que a ID de chamadas de entrada seja bloqueada

- Para bloquear a ID de chamadas de entrada, execute:
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Consulte mais detalhes e exemplos para [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).
    
- Para aplicar a configuração de política que você criou a um usuário em sua organização, execute:
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
### <a name="remove-a-caller-id-policy"></a>Remover uma política de ID de chamadas

Para remover uma política da sua organização, execute:
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Para remover uma política de um usuário, execute:
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Mais informações sobre a Identificação de linha da chamada e o nome do chamador](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[Termos e condições para chamadas de emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
