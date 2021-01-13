---
title: Implantar Telefonar via Trabalho no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumo: saiba como implantar o Telefonar via Trabalho no Skype for Business Server para alguns ou todos os seus usuários.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825001"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implantar Telefonar via Trabalho no Skype for Business Server
 
**Resumo:** Saiba como implantar o Telefonar via Trabalho no Skype for Business Server para alguns ou todos os seus usuários.
  
Use estas etapas para implantar o Telefonar via Trabalho para seus usuários. Considerações de planejamento são discutidas no [Plano para Telefonar via Trabalho no Skype for Business Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md) Em versões anteriores do Lync Server, o controle de chamada remota era um recurso que permitia que os usuários controlas seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pelo Telefonar via Trabalho. 
  
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para Telefonar via Trabalho

O Telefonar via Trabalho usa o Unified Communications Web API (UCWA), que é instalado automaticamente em todos os Servidores Front-End do Skype for Business Server. Para habilitar os usuários para Telefonar via Trabalho, você também deve ter os seguintes pré-requisitos no local: 
  
- Você deve ter um Servidor de Mediação implantado, como parte de um Servidor Front-End ou como uma função autônoma. Você também deve implantar um gateway IP-PBX.
    
- Todos os usuários que serão habilitados para Telefonar via Trabalho devem ter um DID (Discagem Direta interna) no sistema de telefonia PBX. 
    
- Você deve habilitar todos os usuários telefonar via trabalho para o Enterprise Voice. Ao fazer isso, você deve configurar o número DID do Skype for Business para cada usuário para o número DID correspondente para o sistema de telefonia PBX correspondente. 
    
- Todos os usuários que usarão  o Telefonar via Trabalho devem ter a Configuração Automática selecionada na opção **Conexões** Avançadas no cliente Skype for Business. Isso permite que o cliente descubra as URLs do UCWA. **A Configuração** Automática é a seleção padrão.
    
- Para cada usuário do Telefonar via Trabalho, habilita o encaminhamento de chamada e o toque simultâneo. 
    
- Para cada usuário da Chamada via Trabalho, verifique se a conferência discada e a discagem estão habilitadas. Isso permite que esses usuários entre e saim de conferências do Skype for Business.
    
- Verifique se a delegação, a chamada de equipe e o grupo de resposta estão desabilitados para cada usuário do Telefonar via Trabalho.
    
## <a name="deploy-call-via-work"></a>Implantar Chamada via Trabalho

Após os pré-requisitos, faça o seguinte:
  
- Crie um número de telefone global para sua implantação que o Skype for Business exibe na ID de chamadas PBX dos usuários que estão fazendo chamadas Telefonar via Trabalho. 
    
- Criar uma ou mais políticas telefonar via trabalho
    
- Atribuir uma política telefonar via trabalho a cada usuário que será habilitado para Telefonar via Trabalho
    
### <a name="create-the-call-via-work-global-phone-number"></a>Criar o número de telefone global Telefonar via Trabalho

- Digite o cmdlet a seguir
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por exemplo, o cmdlet a seguir define o número de telefone global como 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Criar uma política telefonar via trabalho

- Digite o cmdlet a seguir
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por exemplo, o cmdlet a seguir cria uma política Telefonar via Trabalho chamada ContosoUser1CvWP, exige que o usuário use um número de retorno de chamada de administrador e define esse número de retorno de chamada como 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Atribuir uma política telefonar via trabalho a um usuário

- Digite o cmdlet a seguir
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por exemplo, o cmdlet a seguir atribui a política Telefonar via Trabalho "ContosoUser1CvWP" ao usuário chamado **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Confira também

[Planejar o Telefonar via Trabalho no Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

