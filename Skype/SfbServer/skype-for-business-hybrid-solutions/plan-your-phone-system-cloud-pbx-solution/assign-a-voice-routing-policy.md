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
description: 'Resumo: leia este tópico para saber como atribuir uma política de voz para usuários que usam Sistema de Telefonia com conectividade PSTN local.'
ms.openlocfilehash: f01fcc314cd618150df2c67a2de8b4ea3ee8f9bd7fdb5f4a4c8b3ae24537ee3f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282993"
---
# <a name="assign-a-voice-routing-policy"></a>Atribuir uma política de roteamento de voz
 
> [!Important]
> Skype for Business Online será retirado em 31 de julho de 2021 após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local a Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

**Resumo:** Leia este tópico para saber como atribuir uma política de voz para usuários que usam Sistema de Telefonia com conectividade PSTN local. 
  
Quando um usuário está no Skype for Business Online e usando Sistema de Telefonia com conectividade PSTN local, duas políticas de voz serão aplicadas a eles. Um deles é uma política de roteamento de voz local que você atribuirá no local. Essa política pode ser global ou específica do usuário e define quais registros de uso PSTN estão associados ao usuário. Este tópico explica como atribuir essa política.
  
A outra política de voz define quais recursos de chamada estão disponíveis para o usuário; essa política de voz é definida pela Microsoft e é idêntica para todos os Sistema de Telefonia com usuários de conectividade PSTN locais. Ele é atribuído automaticamente aos Sistema de Telefonia usuários.
  
||**Usuário local**|**Sistema de Telefonia com o usuário de conectividade PSTN local**|
|:-----|:-----|:-----|
|Recursos de chamada definidos em  <br/> |Política de voz  <br/> |Política de voz pré-definida, atribuída automaticamente quando o usuário é licenciado para Sistema de Telefonia.  <br/> |
|Registros de uso de PSTN associados  <br/> |Política de voz  <br/> |Política de roteamento de voz, atribuída enquanto o usuário ainda está no local.  <br/> |
   
Execute as etapas a seguir usando sua implantação local, enquanto o usuário ainda está na implantação local.
  
## <a name="using-a-global-voice-routing-policy"></a>Usando uma política de roteamento de voz global

Antes de usar uma política de roteamento de voz global para sua Sistema de Telefonia com usuários de conectividade PSTN locais, você deve adicionar registros de uso PSTN à política.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Para atribuir registros de uso PSTN à política de roteamento de voz global

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
3. Adicione os registros de uso PSTN à política:
    
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
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
3. Crie uma nova política de roteamento de voz:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Por exemplo:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

Este exemplo cria uma nova política de roteamento de voz chamada HybridVoice, que tem dois usos PSTN associados a ela.
  
## <a name="assigning-a-voice-routing-policy"></a>Atribuir uma política de roteamento de voz

Não importa se você usa a política de roteamento de voz global ou as específicas do usuário, use as etapas a seguir para atribuir a política a um usuário.
  
### <a name="to-assign-the-voice-routing-policy"></a>Para atribuir a política de roteamento de voz

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
3. Atribua uma política de voz existente a um usuário:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído à política de voz criada anteriormente com o nome HybridVoice.
  
Para obter mais detalhes sobre políticas de roteamento de voz, consulte Create or modify a voice policy and [configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)e [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
