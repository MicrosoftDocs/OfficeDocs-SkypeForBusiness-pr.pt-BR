---
title: Habilitar usuários para Enterprise Voice em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumo: saiba como permitir que os usuários façam e recebam chamadas usando o Enterprise Voice em Skype for Business Server.'
ms.openlocfilehash: a910ecb8638b926be9d04234c6f429a97cbd28f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387337"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Habilitar usuários para Enterprise Voice em Skype for Business Server
 
**Resumo:** Saiba como permitir que os usuários façam e recebam chamadas usando Enterprise Voice em Skype for Business Server.
  
Depois de implantar Enterprise Voice ou Chamar Via Trabalho, você pode usar os procedimentos a seguir para permitir que um usuário faça chamadas usando Enterprise Voice:
  
> [!NOTE]
> Dos procedimentos a seguir, apenas o primeiro pode ser executado usando Skype for Business Server Painel de Controle. Para os procedimentos restantes, você só pode usar Skype for Business Server Shell de Gerenciamento. 
  
- Habilita a conta de usuário para Enterprise Voice.
    
- (Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.
    
- (Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar uma conta de usuário para Enterprise Voice

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário que você deseja habilitar para Enterprise Voice.
    
6. No painel **Ações**, clique em **Mostrar detalhes**.
    
7. Na página **Editar Skype for Business Server Usuário**, em **Telefonia**, clique **em Enterprise Voice**.
    
8. Clique **em URI de** linha e digite um número de telefone exclusivo e normalizado (por exemplo, `tel:+14255550200`).
    
9. Clique em **Confirmar**.
    
Para concluir a habilitação de um usuário para Enterprise Voice, certifique-se de que o usuário recebe uma política de voz e um plano de discagem, seja global (atribuído por padrão) ou específico do usuário. Por padrão, todos os usuários têm uma política de voz global e um plano de discagem. Se uma política de voz ou plano de discagem existe no nível do site para o site na qual a conta do usuário está hospedada, estas políticas de site serão aplicadas automaticamente ao usuário. Para aplicar uma política de voz por usuário ou plano de discagem para um usuário, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan**. Para obter detalhes, consulte os procedimentos a seguir neste tópico.
## <a name="voice-policy-assignment"></a>Atribuição da política de voz

Políticas de voz globais e de nível de site são atribuídas automaticamente a todas as contas de usuário habilitadas para Enterprise Voice. Também é possível criar políticas de voz que são aplicadas a usuários ou grupos específicos. Estas políticas por usuário devem ser atribuídas explicitamente aos usuários ou grupos. Se você quiser usar a política de voz global ou de site para todos os usuários habilitados para Enterprise Voice, você pode ignorar esta seção e continuar para a seção [](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) Atribuição de Plano de Discagem mais adiante neste tópico.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Para atribuir uma política de voz específica do usuário

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
3. Para atribuir uma política de voz do usuário existente para um usuário, execute o seguinte no prompt de comando:
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    Neste exemplo, o usuário com o nome de exibição Bob Kelly recebe a política de voz com o nome **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Atribuição do plano de discagem
<a name="BKMK_DialPlanAssignment"> </a>

Para concluir a configuração da conta de usuário para usuários de Enterprise Voice ou usuários de conferência discada, o usuário deve ter um plano de discagem atribuído. As contas do usuário usarão automaticamente o plano de discagem global ou, se existir, o plano de discagem a nível do site quando você não atribuir explicitamente um plano de discagem por usuário existente. Se você quiser usar o plano de discagem global ou de site para todos os usuários habilitados para Enterprise Voice, ignore esta seção.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Para atribuir um plano de discagem específico do usuário

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
3. Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    Neste exemplo, o usuário com o nome de exibição Bob Kelly recebe o plano de discagem do usuário com o nome **DialPlanJapan**.
    

