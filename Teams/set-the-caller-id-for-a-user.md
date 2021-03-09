---
title: Definir a identificação de chamadas para um usuário
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Saiba mais sobre a ID padrão do chamador do Microsoft 365 e do Office 365 (o número de telefone atribuído pelo usuário), também conhecido como ID de Linha de Chamada. Você pode alterar ou bloquear a ID do chamador do usuário.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569413"
---
# <a name="set-the-caller-id-for-a-user"></a>Definir a identificação de chamadas para um usuário
O Sistema de Telefonia no Microsoft 365 e no Office 365 fornece uma ID padrão do chamador que é o número de telefone atribuído pelo usuário. Você pode alterar ou bloquear a ID de chamadas (também chamada de ID da linha de chamada) de um usuário. Você pode saber mais sobre como usar a ID do chamador em sua organização, indo Como a ID do chamador pode ser [usada em sua organização.](how-can-caller-id-be-used-in-your-organization.md)
  
> [!TIP]
> Você não pode bloquear as chamadas recebidas atualmente no Skype for Business Online. 
  
Há duas configurações que você pode alterar:
  
> [!NOTE]
> [!OBSERVAçãO] Isso **não é** para organizações locais com o Lync ou o Skype for Business Server.
  
- **Mudar a ID de chamadas de saída** Você pode substituir a ID de chamadas de um usuário (que, por padrão, é seu número de telefone) por outro número de telefone. Por exemplo, você pode mudar a ID de chamadas do usuário de seu número de telefone para o número de telefone principal de sua empresa ou alterar a ID de Linha de Chamada do usuário de seu número de telefone para o número de telefone principal do departamento jurídico. Você pode mudar o número de ID de chamadas para o número de qualquer **serviço** online (chamada tarifada ou gratuita).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se você desejar usar o parâmetro  _Service_, especifique um número de serviço válido.
  
- **Bloquear a ID do chamador de saída** Você pode impedir que a ID do Chamador de saída seja enviada em chamadas PSTN de saída de um usuário. Isso impede que o número de telefone seja exibido no telefone da pessoa que está sendo chamada.
    
- **Bloquear a ID do chamador de entrada** Você pode impedir que um usuário receba a ID do Chamador em qualquer chamada PSTN de entrada.
    
> [!IMPORTANT]
> [!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas). 
  
Por padrão, essas configurações de ID de chamadas são **desativadas**. Isso significa que o número de telefone do usuário do Skype for Business Online pode ser visto quando o usuário faz uma chamada para um telefone PSTN.
  
Para saber mais sobre essas configurações e como você pode usá-las, clique [Como a identificação de chamadas pode ser usada em sua organização](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Definir as configurações de política de ID de chamadas

> [!NOTE]
> Para todas as configurações de ID do Chamador no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de administração **do Skype for Business.** 
  
### <a name="start-powershell"></a>Iniciar o PowerShell

- Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Veja todas as configurações de ID de chamadas em sua organização

- Para exibir todas as configurações de política de ID do chamador em sua organização, execute:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Consulte mais exemplos e detalhes [para Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Criar uma nova política de ID de chamadas para sua organização


- Para criar uma nova política de ID do chamador que define a ID do chamador como anônima, execute:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.

  Consulte mais exemplos e detalhes [para New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).
    
- Para aplicar a nova política criada ao Amos Marble, execute:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Ver mais sobre o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) para aplicar as configurações aos seus usuários.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Defina a política para que a ID de chamadas de entrada seja bloqueada

- Para bloquear a ID do chamador de entrada, execute:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Consulte mais exemplos e detalhes [para Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).
    
- Para aplicar a configuração de política criada a um usuário em sua organização, execute:
    
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

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Termos e condições para chamadas de emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
