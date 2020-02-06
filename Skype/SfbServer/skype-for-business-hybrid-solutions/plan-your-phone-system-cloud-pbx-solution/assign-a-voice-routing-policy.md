---
title: Atribuir uma Política de Roteamento de Voz
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumo: Leia este tópico para saber como atribuir uma política de voz para usuários que usam o sistema telefônico no Office 365 com conectividade PSTN local.'
ms.openlocfilehash: 0e9a39fba8d1db7b70f0422e71223d49917716ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803991"
---
# <a name="assign-a-voice-routing-policy"></a>Atribuir uma Política de Roteamento de Voz
 
**Resumo:** Leia este tópico para saber como atribuir uma política de voz para usuários que usam o sistema telefônico no Office 365 com conectividade PSTN local. 
  
Depois que um usuário estiver no Skype for Business Online e usar o sistema telefônico no Office 365 com conectividade PSTN local, duas políticas de voz serão aplicadas a elas. Uma é uma política de roteamento de voz local que você atribuirá no local. Essa política pode ser global ou específica do usuário e define quais registros de uso PSTN estão associados ao usuário. Este tópico explica como atribuir esta política.
  
A outra política de voz define quais recursos de chamada estão disponíveis para o usuário; Essa política de voz é definida pela Microsoft e é idêntica para todos os sistemas telefônicos do Office 365 com usuários de conectividade PSTN locais. Ele é automaticamente atribuído ao sistema telefônico em usuários do Office 365.
  
||**Usuário local**|**Sistema telefônico no Office 365 com usuário de conectividade PSTN local**|
|:-----|:-----|:-----|
|Recursos de chamada definidos na  <br/> |Política de voz  <br/> |Política de voz previamente definida, atribuída automaticamente quando o usuário é licenciado para o sistema telefônico no Office 365.  <br/> |
|Registros de uso de PSTN associados a  <br/> |Política de voz  <br/> |Política de roteamento de voz, atribuída enquanto o usuário ainda está hospedado no local.  <br/> |
   
Execute as etapas a seguir usando a implantação local, enquanto o usuário ainda é hospedado na implantação local.
  
## <a name="using-a-global-voice-routing-policy"></a>Usar uma política de roteamento de voz global

Antes de usar uma política de roteamento de voz global para seu sistema telefônico no Office 365 com usuários de conectividade PSTN locais, você deve adicionar registros de uso de PSTN à política.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Atribuir registros de uso de PSTN à política de roteamento de voz global

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Adicione os registros de uso de PSTN à política:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Por exemplo:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Crie uma nova política de roteamento de voz

### <a name="to-create-a-new-voice-routing-policy"></a>Criar uma nova política de roteamento de voz

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Crie uma nova política de roteamento de voz:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Por exemplo:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

Esse exemplo cria uma nova política de roteamento de voz, chamada HybridVoice, com dois usos de PSTN associados a ela.
  
## <a name="assigning-a-voice-routing-policy"></a>Atribuir uma política de roteamento de voz

Para política de roteamento de voz global ou específica do usuário, use as etapas a seguir para atribuir a política a um usuário.
  
### <a name="to-assign-the-voice-routing-policy"></a>Atribuir a política de roteamento de voz

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Atribua uma política de voz existente a um usuário:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído à política de voz criada anteriormente com o nome HybridVoice.
  
Para obter mais detalhes sobre as políticas de roteamento de voz, consulte [criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

