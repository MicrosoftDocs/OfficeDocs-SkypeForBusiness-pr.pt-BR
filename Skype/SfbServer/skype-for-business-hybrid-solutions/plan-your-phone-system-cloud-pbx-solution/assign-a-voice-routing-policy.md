---
title: Atribuir uma Política de Roteamento de Voz
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumo: Leia este tópico para saber como atribuir uma política de voz para os usuários que usam o sistema telefônico no Office 365 com uma conectividade PSTN local.'
ms.openlocfilehash: 43d8939e6e0cd49f66234e127f05cb421700a15a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569495"
---
# <a name="assign-a-voice-routing-policy"></a>Atribuir uma Política de Roteamento de Voz
 
**Resumo:** Leia este tópico para saber como atribuir uma política de voz para os usuários que usam o sistema telefônico no Office 365 com uma conectividade PSTN local. 
  
Depois que um usuário estiver ligado Skype para Business Online e usando o sistema telefônico no Office 365 com conectividade PSTN de local, duas políticas de voz serão aplicadas a eles. Um é uma política de roteamento de voz de local que você irá atribuir no local. Essa diretiva pode ser global ou específico do usuário e define a quais registros de uso PSTN associados ao usuário. Este tópico explica como atribuir esta política.
  
Política de voz define quais recursos de chamada estão disponíveis para o usuário; Essa política de voz é definida pela Microsoft e é idêntica para todos os sistema telefônico no Office 365 com usuários de conectividade PSTN local. Ele é automaticamente atribuído para o sistema telefônico em usuários do Office 365.
  
||**Usuário local**|**Sistema telefônico no Office 365 com o usuário de conectividade PSTN local**|
|:-----|:-----|:-----|
|Recursos de chamada definidos na  <br/> |Política de voz  <br/> |Pré-definidas política de voz, atribuída automaticamente quando o usuário estiver licenciado para o sistema telefônico no Office 365.  <br/> |
|Registros de uso de PSTN associados a  <br/> |Política de voz  <br/> |Política de roteamento de voz, atribuída enquanto o usuário ainda está hospedado no local.  <br/> |
   
Você execute as seguintes etapas usando sua implantação no local, enquanto o usuário ainda é hospedado na implantação no local.
  
## <a name="using-a-global-voice-routing-policy"></a>Usar uma política de roteamento de voz global

Antes de usar uma política de roteamento de voz global para seu sistema telefônico no Office 365 com usuários de conectividade PSTN local, você deve adicionar registros de uso PSTN à política.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Atribuir registros de uso de PSTN à política de roteamento de voz global

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Adicione os registros de uso PSTN à política:
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
  ```

    Por exemplo:
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
  ```

## <a name="creating-a-new-voice-routing-policy"></a>Crie uma nova política de roteamento de voz

### <a name="to-create-a-new-voice-routing-policy"></a>Criar uma nova política de roteamento de voz

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Crie uma nova política de roteamento de voz:
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    Por exemplo:
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

Esse exemplo cria uma nova política de roteamento de voz, chamada HybridVoice, com dois usos de PSTN associados a ela.
  
## <a name="assigning-a-voice-routing-policy"></a>Atribuir uma política de roteamento de voz

Para política de roteamento de voz global ou específica do usuário, use as etapas a seguir para atribuir a política a um usuário.
  
### <a name="to-assign-the-voice-routing-policy"></a>Atribuir a política de roteamento de voz

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Atribua uma política de voz existente a um usuário:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    Por exemplo:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído à política de voz criada anteriormente com o nome HybridVoice.
  
Para obter mais detalhes sobre as políticas de roteamento de voz, consulte [criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

