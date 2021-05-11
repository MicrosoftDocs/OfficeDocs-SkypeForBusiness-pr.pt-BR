---
title: Definir a identificação de chamadas para um usuário
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Saiba mais sobre o Microsoft 365 e Office 365 ID padrão do chamador (número de telefone atribuído a um usuário), também conhecido como ID de Linha de Chamada. Você pode alterar ou bloquear a ID do chamador do usuário.
ms.openlocfilehash: dbbb48952264d82ca24bdd82dbb45538b0428368
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308330"
---
# <a name="set-the-caller-id-for-a-user"></a>Definir a identificação de chamadas para um usuário

Sistema de Telefonia no Microsoft 365 fornece uma ID de chamador padrão que é o número de telefone atribuído pelo usuário. Você pode alterar ou bloquear a ID de chamadas (também chamada de ID da linha de chamada) de um usuário. Você pode saber mais sobre como usar a ID do chamador em sua organização, indo Como a ID do chamador pode ser [usada em sua organização.](how-can-caller-id-be-used-in-your-organization.md)
  
Por padrão, as configurações de ID do chamador a seguir são **desligadas**. Isso significa que o Teams de telefone do usuário pode ser visto quando esse usuário faz uma chamada para um telefone PSTN. Você pode alterar essas configurações da seguinte forma:
  
- **ID do chamador de saída** Você pode substituir a ID do Chamador do usuário, que por padrão é seu número de telefone, por outro número de telefone. Por exemplo, você pode mudar a ID de chamadas do usuário de seu número de telefone para o número de telefone principal de sua empresa ou alterar a ID de Linha de Chamada do usuário de seu número de telefone para o número de telefone principal do departamento jurídico. Você pode alterar o número da ID de chamada para qualquer número de serviço online (gratuito ou gratuito). Você também pode alterar o número da ID de chamada para um número de telefone local por meio do Roteamento Direto atribuído a uma conta de recurso usada por um Atendedor Automático ou Fila de Chamadas.
    
  > [!NOTE]
  > Se quiser usar o parâmetro *Service,* especifique um número de serviço válido.
  
- **Bloquear a ID do chamador de saída.** Você pode impedir que a ID do Chamador de saída seja enviada em chamadas PSTN de saída de um usuário. Isso impede que o número de telefone seja exibido no telefone da pessoa que está sendo chamada.
    
- **Bloquear a ID do chamador de entrada.** Você pode impedir que um usuário receba a ID do Chamador em qualquer chamada PSTN de entrada.

- **Definir Nome da Parte de Chamada (CNAM).** Para seus Microsoft Teams, você pode enviar um CNAM em chamadas PSTN de saída.
    
> [!IMPORTANT]
> [!IMPORTANTE] As chamadas de emergência sempre enviarão o número de telefone dos usuários (ID de chamadas). 
  

  
Para saber mais sobre essas configurações e como usá-las, consulte Como a ID do chamador pode ser [usada em sua organização.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>Definir as configurações de política de ID de chamadas

> [!NOTE]
> Para definir a ID do chamador como um número de telefone da conta de recurso e definir o nome da parte de chamada, use os cmdlets do PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity no módulo 2.3.1 do Teams PowerShell ou posterior. (Essas opções não estão disponíveis no Microsoft Teams de administração.) 

Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>Exibir, criar e aplicar configurações de política

1. Para exibir todas as configurações de política de ID do chamador em sua organização, execute:

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   Para obter mais informações, [consulte Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).
    
2. Para criar uma nova política de ID do chamador para sua organização, use o cmdlet New-CsCallingIdentity de chamada:
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    Em todos os casos, o campo "Número de Serviço" não deve incluir um "+" inicial.

   Para obter mais informações, [consulte New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).
    
3. Aplique a nova política criada usando o cmdlet Grant-CsCallingIdentity. Por exemplo, o exemplo a seguir aplica a nova política ao usuário Amos Marble.
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   Para obter mais informações, [consulte Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.
    

4. Se você quiser bloquear a ID do chamador de entrada, execute:
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   Para obter mais informações, [consulte Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).
    
5. Para aplicar a configuração de política criada a um usuário em sua organização, execute:
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   Para obter mais informações, [consulte Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).

6. Para criar uma nova política de ID do Chamador que define a ID do Chamador como o número de telefone da conta de recurso especificada e define o nome da parte de chamada como Contoso:

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) para aplicar as configurações aos seus usuários.
    
### <a name="remove-a-policy-setting"></a>Remover uma configuração de política

Para remover uma política da sua organização, execute:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Para remover uma política de um usuário, execute:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 usando um único ponto de administração que pode simplificar seu trabalho diário. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
- [Uma introdução ao Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
- [Melhores maneiras de gerenciar Microsoft 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Termos e condições para chamadas de emergência](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
