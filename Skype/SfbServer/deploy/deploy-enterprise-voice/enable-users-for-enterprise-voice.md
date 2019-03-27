---
title: Habilitar usuários para o Enterprise Voice no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumo: Saiba como permitir que os usuários façam e recebam chamadas usando o Enterprise Voice no Skype para Business Server.'
ms.openlocfilehash: b02155f424e8b3f29881caf8c4a29db6f76cb807
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882966"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Habilitar usuários para o Enterprise Voice no Skype para Business Server
 
**Resumo:** Saiba como permitir que os usuários façam e recebam chamadas usando o Enterprise Voice no Skype para Business Server.
  
Após a implantação do Enterprise Voice ou chamada Via trabalho, você pode usar os procedimentos a seguir para habilitar um usuário fazer chamadas usando o Enterprise Voice:
  
> [!NOTE]
> Dos procedimentos a seguir, somente a primeira pode ser realizada usando Skype para o painel de controle do servidor de negócios. Para os demais procedimentos, você pode usar somente Skype do Shell de gerenciamento do servidor de negócios. 
  
- Habilite a conta de usuário para o Enterprise Voice.
    
- (Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.
    
- (Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar uma conta de usuário para o Enterprise Voice

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.
    
2. Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.
    
6. No menu **Editar**, clique em **Exibir detalhes**.
    
7. Na página **Editar Skype para usuário de servidor de negócios** , em **telefonia**, clique em **Enterprise Voice**.
    
8. Clique em **URI de linha** e digite um número de telefone único e normalizado (por exemplo, tel:+14255550200).
    
9. Clique em **Confirmar**.
    
Para finalizar a habilitação de um usuário para o Enterprise Voice, certifique-se que o usuário é atribuído a uma política de voz e um plano de discagem, global (atribuído por padrão) ou específico do usuário. Por padrão, todos os usuários recebem uma política de voz global e plano de discagem. Se um plano de discagem ou política de voz existir no nível do site para o site no qual a conta de usuário está hospedada, as políticas de site serão automaticamente aplicadas ao usuário. Para aplicar uma política de voz por usuário ou plano a um usuário de discagem, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan** . Para obter detalhes, consulte os seguintes procedimentos neste tópico.
## <a name="voice-policy-assignment"></a>Atribuição de política de voz

Políticas de voz global e no nível do site são automaticamente atribuídas a todas as contas de usuário que estão habilitadas para o Enterprise Voice. Você também pode criar políticas de voz que se aplicam a usuários ou grupos específicos. Essas políticas por usuário devem ser explicitamente atribuídas a usuários ou grupos. Se desejar usar o modelo global ou de site de política de voz para todos os usuários habilitados para o Enterprise Voice, você pode pular esta seção e continuam a [Atribuição de plano de discagem](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) seção mais adiante neste tópico.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Para atribuir uma política de voz específica do usuário

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para atribuir uma política de voz de usuário existente a um usuário, execute o seguinte no prompt de comando:
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído a política de voz com o nome **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Atribuição de plano de discagem
<a name="BKMK_DialPlanAssignment"> </a>

Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferência discada, o usuário deve ser atribuído um plano de discagem. Contas de usuário usarão o plano de discagem global automaticamente ou, se houver, o plano de discagem de nível de site, quando você não atribuir explicitamente um plano de discagem por usuário existente. Se você deseja usar global ou de site de plano de discagem para todos os usuários habilitados para o Enterprise Voice, você poderá ignorar esta seção.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Para atribuir um plano de discagem específico do usuário

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído o plano de discagem do usuário **chamado dialplanjapan**.
    

