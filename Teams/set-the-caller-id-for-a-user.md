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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Saiba mais sobre o recurso de identificação de chamadas padrão do Microsoft 365 e do Office 365 (um número de telefone atribuído a um usuário), também conhecido como identificação da linha de chamada. Você pode alterar ou bloquear o recurso de identificação de chamadas de um usuário.
ms.openlocfilehash: 059e92f04f3d4a5df73ed9201f1f784f2bd01f30
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691117"
---
# <a name="set-the-caller-id-for-a-user"></a>Definir a identificação de chamadas para um usuário
O sistema telefônico do Microsoft 365 e do Office 365 fornece uma ID de chamada padrão que é o número de telefone atribuído ao usuário. Você pode alterar ou bloquear a ID de chamadas (também chamada de ID da linha de chamada) de um usuário. Você pode saber mais sobre como usar o recurso de identificação de chamadas em sua organização, indo [como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Você não pode bloquear as chamadas recebidas atualmente no Skype for Business Online. 
  
Há duas configurações que você pode alterar:
  
> [!NOTE]
> [!OBSERVAçãO] Isso **não é** para organizações locais com o Lync ou o Skype for Business Server.
  
- **Mudar a ID de chamadas de saída** Você pode substituir a ID de chamadas de um usuário (que, por padrão, é seu número de telefone) por outro número de telefone. Por exemplo, você pode mudar a ID de chamadas do usuário de seu número de telefone para o número de telefone principal de sua empresa ou alterar a ID de Linha de Chamada do usuário de seu número de telefone para o número de telefone principal do departamento jurídico. Você pode mudar o número de ID de chamadas para o número de qualquer **serviço** online (chamada tarifada ou gratuita).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se você desejar usar o parâmetro  _Service_, especifique um número de serviço válido.
  
- **Bloquear a identificação de chamadas de saída** Você pode impedir que a identificação de chamadas de saída seja enviada nas chamadas PSTN de um usuário. Isso impede que o número de telefone seja exibido no telefone da pessoa que está sendo chamada.
    
- **Bloquear a identificação de chamadas de entrada** Você pode impedir que um usuário receba a identificação de chamadas em chamadas PSTN de entrada.
    
> [!IMPORTANT]
> [!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas). 
  
Por padrão, essas configurações de ID de chamadas são **desativadas**. Isso significa que o número de telefone do usuário do Skype for Business Online pode ser visto quando o usuário faz uma chamada para um telefone PSTN.
  
Para saber mais sobre essas configurações e como você pode usá-las, clique [Como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Definir as configurações de política de ID de chamadas

> [!NOTE]
> Para todas as configurações de identificação de chamadas no Skype for Business Online, você deve usar o Windows PowerShell e **não pode usar** o **centro de administração do Skype for Business**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
    Se precisar saber mais, consulte [conectar a todos os serviços do Microsoft 365 ou do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar uma sessão do Windows PowerShell**
    
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell** , conecte-se ao seu Microsoft 365 ou ao Office 365 executando:
    
   > [!NOTE]
   > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Microsoft 365 ou do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Veja todas as configurações de ID de chamadas em sua organização

- Para ver todas as configurações de política de identificação de chamadas em sua organização, execute:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Veja mais exemplos e detalhes do [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Criar uma nova política de ID de chamadas para sua organização


- Para criar uma nova política de identificação de chamadas que defina a identificação de chamadas como anônima, execute:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.

  Veja mais exemplos e detalhes do [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).
    
- Para aplicar a nova política criada para o Marble Amos, execute:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
Se você já tiver criado uma política, poderá usar o cmdlet [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) para aplicar as configurações aos usuários.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Defina a política para que a ID de chamadas de entrada seja bloqueada

- Para bloquear a identificação de chamadas de entrada, execute:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Veja mais exemplos e detalhes do [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).
    
- Para aplicar a configuração de política que você criou a um usuário em sua organização, execute:
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
### <a name="remove-a-caller-id-policy"></a>Remover uma política de ID de chamadas

Para remover uma política da sua organização, execute:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Para remover uma política de um usuário, execute:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business online usando um único ponto de administração que pode simplificar o seu trabalho diário, quando você tem várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Termos e condições para chamadas de emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
