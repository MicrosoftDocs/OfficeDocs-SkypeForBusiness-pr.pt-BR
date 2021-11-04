---
title: Implantar chamada via trabalho no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumo: saiba como implantar Call Via Work Skype for Business Server para alguns ou todos os seus usuários.'
ms.openlocfilehash: 98d7cc08b2cb4101f1d9d062e62ef32a3998691b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761605"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implantar chamada via trabalho no Skype for Business Server
 
**Resumo:** Saiba como implantar Call Via Work Skype for Business Server para alguns ou todos os seus usuários.
  
Use estas etapas para implantar Call Via Work para seus usuários. Considerações de planejamento são discutidas em [Plan for Call Via Work em Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Em versões anteriores do controle de chamada remota do Lync Server, era um recurso que permitia aos usuários controlar seus telefones PBX com o Lync Server. Em Skype for Business Server, esse recurso foi substituído por Call Via Work. 
  
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para chamada via trabalho

O Call Via Work usa a UCWA (Unified Communications Web API), que é instalada automaticamente em todos os Skype for Business Server Servidores Front-End. Para habilitar os usuários para o Call Via Work, você também deve ter os seguintes pré-requisitos no local: 
  
- Você deve ter um Servidor de Mediação implantado, como parte de um Servidor Front-End ou como uma função autônoma. Você também deve implantar um gateway IP-PBX.
    
- Todos os usuários que serão habilitados para Chamadas Via Trabalho devem ter uma Discagem Direta Interna (DID) no sistema de telefonia PBX. 
    
- Você deve habilitar todos os usuários de Chamada Via Trabalho para Enterprise Voice. Ao fazer isso, você deve configurar o número DID Skype for Business de cada usuário para o número DID correspondente para o sistema de telefonia PBX correspondente. 
    
- Todos os usuários que usarão  o Call Via Work devem ter a Configuração Automática selecionada na opção **Conexões** Avançadas em seu Skype for Business cliente. Isso permite que o cliente descubra as URLs do UCWA. **Configuração Automática** é a seleção padrão.
    
- Para cada usuário de Chamada Via Trabalho, habilita o encaminhamento de chamada e toque simultâneo. 
    
- Para cada usuário de Chamada Via Trabalho, certifique-se de que a discagem discada e a conferência discada estão habilitadas. Isso permite que esses usuários entre e saia de Skype for Business conferências.
    
- Verifique se a delegação, a chamada de equipe e o grupo de resposta estão desabilitados para cada usuário de Chamada Via Trabalho.
    
## <a name="deploy-call-via-work"></a>Implantar Chamada via Trabalho

Depois que os pré-requisitos estão no local, faça o seguinte:
  
- Crie um número de telefone global para sua implantação que Skype for Business exibe na ID do chamador PBX dos usuários que estão fazendo chamadas via trabalho. 
    
- Criar uma ou mais políticas de chamada via trabalho
    
- Atribuir uma política de chamada via trabalho a cada usuário que será habilitado para o Call Via Work
    
### <a name="create-the-call-via-work-global-phone-number"></a>Criar o número de telefone global Call Via Work

- Digite o cmdlet a seguir
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por exemplo, o cmdlet a seguir define o número de telefone global como 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Criar uma política de chamada via trabalho

- Digite o cmdlet a seguir
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por exemplo, o cmdlet a seguir cria uma política de Chamada Via Trabalho chamada ContosoUser1CvWP, exige que o usuário use um número de retorno de chamada de administrador e define esse número de retorno de chamada como 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Atribuir uma política de chamada via trabalho a um usuário

- Digite o cmdlet a seguir
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por exemplo, o cmdlet a seguir atribui a política de chamada via trabalho "ContosoUser1CvWP" ao usuário chamado **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Confira também

[Planejar a chamada via trabalho no Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

