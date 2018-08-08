---
title: Implantar a chamada Via trabalho no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumo: Saiba como implantar chamada Via trabalho no Skype para Business Server para alguns ou todos os seus usuários.'
ms.openlocfilehash: 60890f510f5f895f3a99f070cd9cf1a7c997da61
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991042"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implantar a chamada Via trabalho no Skype para Business Server
 
**Resumo:** Aprenda a implantar chamada Via trabalho no Skype para Business Server para alguns ou todos os seus usuários.
  
Use estas etapas para implantar a chamada Via trabalho para seus usuários. Considerações de planejamento são abordadas em [Planejar a chamada Via trabalho no Skype para Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Nas versões anteriores de chamada remota do Lync Server controle era um recurso que permitia aos usuários controlar seus telefones PBX com o Lync Server. Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho. 
  
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para chamada Via trabalho

Chamada Via trabalho usa Unified Communications Web API (UCWA), que é instalado automaticamente em todos os Skype para Business Server servidores Front-End. Para habilitar usuários para chamada Via trabalho, você também deve ter os seguintes pré-requisitos in-loco: 
  
- Você deve ter um servidor de mediação implantados, ou como parte de um servidor Front-End ou como uma função autônomo. Um gateway IP-PBX também deve ser implantado.
    
- Todos os usuários que serão habilitados para chamada Via trabalho devem ter um Direct Inward Dialing (DID) no sistema telefônico PBX. 
    
- Você deve habilitar todos os usuários de chamada Via trabalho para o Enterprise Voice. Quando você fizer isso, você deve configurar o Skype para negócios tenha o número para cada usuário no número DID correspondente para o sistema de telefone PBX correspondente. 
    
- Todos os usuários que usarão chamada Via trabalho devem ter **A configuração automática** selecionada na opção suas **Conexões avançadas** em seu Skype para o cliente de negócios. Isso permite que o cliente descobrir as URLs do UCWA. **Configuração automática** é a seleção padrão.
    
- Para cada usuário de chamada Via trabalho, habilite o encaminhamento de chamadas e toque simultâneo. 
    
- Para cada usuário de chamada Via trabalho, certifique-se de que a conferência discada e discar conferência estão habilitados. Isso permite que esses usuários obter e sair Skype para conferências de negócios.
    
- Certifique-se de que a delegação, chamada de equipe e grupo de resposta estão desabilitados para cada usuário de chamada Via trabalho.
    
## <a name="deploy-call-via-work"></a>Implantar Telefonar via Trabalho

Depois que todos os pré-requisitos forem implantados, execute as seguintes ações:
  
- Crie um número de telefone global para sua implantação que Skype para negócios exibe na ID de chamador PBX de usuários que estão fazendo chamadas de chamada Via trabalho. 
    
- Criar uma ou mais políticas de chamada Via trabalho
    
- Atribuir uma política de chamada Via trabalho para cada usuário que será habilitado para chamada Via trabalho
    
### <a name="create-the-call-via-work-global-phone-number"></a>Criar o número de telefone global Telefonar via Trabalho

- Digite o seguinte cmdlet
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por exemplo, o seguinte cmdlet configura o número de telefone global para 1-555-123-4567.
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Criar uma política Telefonar via Trabalho

- Digite o seguinte cmdlet
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por exemplo, o cmdlet a seguir cria uma política de chamada Via trabalho denominada ContosoUser1CvWP requer que o usuário usar um número de retorno de chamada de admin e define esse número de retorno de chamada para 1-555-789-1234.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Atribuir uma política de chamada Via trabalho a um usuário

- Digite o seguinte cmdlet
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por exemplo, o cmdlet a seguir atribui a política de chamada Via trabalho "ContosoUser1CvWP" para o usuário chamado **ContosoUser1**.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Consulte também

[Planejar para chamada Via trabalho no Skype para Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

