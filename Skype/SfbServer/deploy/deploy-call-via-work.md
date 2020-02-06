---
title: Implantar chamada por meio do trabalho no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: saiba como implantar a chamada por meio do trabalho no Skype for Business Server para alguns ou todos os seus usuários.'
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791079"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implantar chamada por meio do trabalho no Skype for Business Server
 
**Resumo:** Saiba como implantar a chamada por meio do trabalho no Skype for Business Server para alguns ou todos os seus usuários.
  
Use estas etapas para implantar a chamada por meio do trabalho para seus usuários. As considerações de planejamento são discutidas no [plano de chamada por meio do trabalho no Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Em versões anteriores do controle de chamada remota do Lync Server era um recurso que permitia aos usuários controlar os telefones PBX com o Lync Server. No Skype for Business Server, este recurso foi substituído por meio da chamada por meio do trabalho. 
  
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para ligar pelo trabalho

A chamada via trabalho usa a API da Web de comunicação unificada (UCWA), que é instalada automaticamente em todos os servidores de front-end do Skype for Business Server. Para permitir que os usuários liguem por meio do trabalho, você também deve ter os seguintes pré-requisitos em vigor: 
  
- Você deve ter um servidor de mediação implantado, seja como parte de um servidor front-end ou como uma função autônoma. Um gateway IP-PBX também deve ser implantado.
    
- Todos os usuários que serão habilitados para a chamada por meio do trabalho deverão ter uma discagem direta (DID) no sistema de telefonia PBX. 
    
- Você deve habilitar toda a chamada por meio de usuários de trabalho do Enterprise Voice. Ao fazer isso, você deve configurar o Skype for Business para que cada usuário tenha o número DID correspondente para o sistema telefônico PBX correspondente. 
    
- Todos os usuários que usarão a chamada por meio do trabalho deverão ter a **configuração automática** selecionada na opção **conexões avançadas** no cliente Skype for Business. Isso permite que o cliente descubra as URLs do UCWA. **Configuração automática** é a seleção padrão.
    
- Para cada chamada por usuário de trabalho, ative o encaminhamento de chamadas e o toque simultâneo. 
    
- Para cada chamada por usuário do trabalho, verifique se a conferência discada e a conferência discada está habilitada. Isso permite que esses usuários entrem e entrem em conferências do Skype for Business.
    
- Verifique se a delegação, a chamada de equipe e o grupo de resposta estão desabilitados para cada chamada por meio de um usuário de trabalho.
    
## <a name="deploy-call-via-work"></a>Implantar Telefonar via Trabalho

Depois que todos os pré-requisitos forem implantados, execute as seguintes ações:
  
- Crie um número de telefone global para sua implantação do qual o Skype for Business é exibido na identificação de chamadas do PBX de usuários que estão chamando via chamadas de trabalho. 
    
- Criar uma ou mais chamadas via políticas de trabalho
    
- Atribuir uma chamada via política de trabalho a cada usuário que será habilitado para fazer uma chamada via trabalho
    
### <a name="create-the-call-via-work-global-phone-number"></a>Criar o número de telefone global Telefonar via Trabalho

- Digite o seguinte cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por exemplo, o seguinte cmdlet configura o número de telefone global para 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Criar uma política Telefonar via Trabalho

- Digite o seguinte cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por exemplo, o cmdlet a seguir cria uma chamada via política de trabalho chamada ContosoUser1CvWP, requer que o usuário use um número de retorno de chamada de administrador e define esse número de retorno de chamada para 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Atribuir uma chamada via política de trabalho a um usuário

- Digite o seguinte cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por exemplo, o cmdlet a seguir atribui a chamada via política de trabalho "ContosoUser1CvWP" ao usuário chamado **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Confira também

[Planejar a chamada por meio do trabalho no Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

