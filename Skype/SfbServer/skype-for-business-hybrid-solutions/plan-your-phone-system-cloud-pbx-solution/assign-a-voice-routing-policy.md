---
title: Atribuir uma política de roteamento de voz
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
description: 'Resumo: Leia este tópico para saber como atribuir uma política de voz para usuários que usam o Sistema de Telefonia com conectividade PSTN local.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359317"
---
# <a name="assign-a-voice-routing-policy"></a>Atribuir uma política de roteamento de voz
 
> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021, após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

**Resumo:** Leia este tópico para saber como atribuir uma política de voz para usuários que usam o Sistema de Telefonia com conectividade PSTN local. 
  
Quando um usuário está no Skype for Business Online e usando o Sistema de Telefonia com conectividade PSTN local, duas políticas de voz serão aplicadas a ele. Uma é uma política de roteamento de voz local que você atribuirá no local. Essa política pode ser global ou específica do usuário e define quais registros de uso de PSTN estão associados ao usuário. Este tópico explica como atribuir essa política.
  
A outra política de voz define quais recursos de chamada estão disponíveis para o usuário; essa política de voz é definida pela Microsoft e é idêntica para todo o Sistema de Telefonia com usuários de conectividade PSTN local. Ele é atribuído automaticamente aos usuários do Sistema de Telefonia.
  
||**Usuário local**|**Sistema de Telefonia com usuário de conectividade PSTN local**|
|:-----|:-----|:-----|
|Recursos de chamada definidos em  <br/> |Política de voz  <br/> |Política de voz pré-definida, atribuída automaticamente quando o usuário é licenciado para o Sistema de Telefonia.  <br/> |
|Registros de uso de PSTN associados  <br/> |Política de voz  <br/> |Política de roteamento de voz, atribuída enquanto o usuário ainda está no local.  <br/> |
   
Execute as etapas a seguir usando sua implantação local, enquanto o usuário ainda está na implantação local.
  
## <a name="using-a-global-voice-routing-policy"></a>Usando uma política de roteamento de voz global

Antes de usar uma política de roteamento de voz global para seu Sistema de Telefonia com usuários de conectividade PSTN local, você deve adicionar registros de uso de PSTN à política.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Para atribuir registros de uso de PSTN à política de roteamento de voz global

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Adicione os registros de uso de PSTN à política:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Por exemplo:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Criando uma nova política de roteamento de voz

### <a name="to-create-a-new-voice-routing-policy"></a>Para criar uma nova política de roteamento de voz

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Crie uma nova política de roteamento de voz:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Por exemplo:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

Este exemplo cria uma nova política de roteamento de voz chamada HybridVoice, que tem dois usos de PSTN associados a ela.
  
## <a name="assigning-a-voice-routing-policy"></a>Atribuindo uma política de roteamento de voz

Não importa se você usa a política de roteamento de voz global ou as específicas do usuário, use as etapas a seguir para atribuir a política a um usuário.
  
### <a name="to-assign-the-voice-routing-policy"></a>Para atribuir a política de roteamento de voz

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Atribua uma política de voz existente a um usuário:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído à política de voz criada anteriormente com o nome HybridVoice.
  
Para obter mais detalhes sobre políticas de roteamento de voz, consulte Create [or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

