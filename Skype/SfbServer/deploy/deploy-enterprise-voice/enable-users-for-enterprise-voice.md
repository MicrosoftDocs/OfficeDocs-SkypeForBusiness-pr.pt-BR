---
title: Habilitar usuários do Enterprise Voice no Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumo: saiba como habilitar usuários para fazer e receber chamadas usando o Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: 571f708e43b271252840d03ec08e1602f62854d1
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767254"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Habilitar usuários do Enterprise Voice no Skype for Business Server
 
**Resumo:** Saiba como habilitar usuários para fazer e receber chamadas usando o Enterprise Voice no Skype for Business Server.
  
Depois de implantar o Enterprise Voice ou ligar pelo trabalho, você pode usar os procedimentos a seguir para permitir que um usuário faça chamadas usando o Enterprise Voice:
  
> [!NOTE]
> Dos procedimentos a seguir, somente o primeiro pode ser executado usando o painel de controle do Skype for Business Server. Para obter os procedimentos restantes, você pode usar apenas o Shell de gerenciamento do Skype for Business Server. 
  
- Habilite a conta de usuário do Enterprise Voice.
    
- (Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.
    
- (Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar uma conta de usuário para o Enterprise Voice

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.
    
6. No menu **Editar**, clique em **Exibir detalhes**.
    
7. Na página **Editar o usuário do Skype for Business Server** , em **telefonia**, clique em **Enterprise Voice**.
    
8. Clique em **URI de linha** e digite um número de telefone único e normalizado (por exemplo, tel:+14255550200).
    
9. Clique em **Confirmar**.
    
Para concluir a habilitação de um usuário para o Enterprise Voice, certifique-se de que o usuário tenha atribuído uma política de voz e um plano de discagem, seja global (atribuído por padrão) ou específico ao usuário. Por padrão, todos os usuários recebem uma política de voz global e um plano de discagem. Se houver uma política de voz ou um plano de discagem no nível do site no qual a conta de usuário é hospedada, essas políticas do site serão aplicadas automaticamente ao usuário. Para aplicar uma política de voz por usuário ou um plano de discagem a um usuário, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan** . Para obter detalhes, consulte os procedimentos a seguir neste tópico.
## <a name="voice-policy-assignment"></a>Atribuição de política de voz

Políticas de voz globais e no nível do site são automaticamente atribuídas a todas as contas de usuário habilitadas para o Enterprise Voice. Você também pode criar políticas de voz que se aplicam a usuários ou grupos específicos. Essas políticas por usuário devem ser explicitamente atribuídas aos usuários ou grupos. Se quiser usar a política de voz global ou de site para todos os usuários habilitados para o Enterprise Voice, você poderá ignorar esta seção e continuar a [discagem](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) da seção de atribuição de plano posteriormente neste tópico.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Para atribuir uma política de voz específica do usuário

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para atribuir uma política de voz de usuário existente a um usuário, execute o seguinte no prompt de comando:
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    Neste exemplo, o usuário com o nome para exibição Bob está atribuído à política de voz com o nome **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Atribuição de plano de discagem
<a name="BKMK_DialPlanAssignment"> </a>

Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferências discadas, o usuário deve receber um plano de discagem. As contas de usuário usarão automaticamente o plano de discagem global ou, se houver, o plano de discagem no nível do site, quando você não atribui explicitamente um plano de discagem por usuário existente. Se quiser usar o plano global ou de discagem de site para todos os usuários que estão habilitados para o Enterprise Voice, você pode ignorar esta seção.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Para atribuir um plano de discagem específico do usuário

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por exemplo:
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    Neste exemplo, o usuário com o nome para exibição Bob está atribuído ao plano de discagem do usuário com o nome **DialPlanJapan**.
    

