---
title: Habilitar Estacionamento de Chamada para usuários no Skype for Business
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilitar usuários para Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830951"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Habilitar Estacionamento de Chamada para usuários no Skype for Business
 
Habilitar usuários para Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
  
Por padrão, o Estacionamento de Chamada está desabilitado para todos os usuários. Os usuários não podem estacionar chamadas ou recuperar chamadas estacionadas até que sejam habilitadas para Estacionamento de Chamada na política de voz.
  
Você pode habilitar o Estacionamento de Chamada no escopo global ou no escopo do site ou do usuário. O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global. Se você tiver várias políticas de voz, revise todas as políticas para habilitar o Estacionamento de Chamadas, não apenas a política global.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Para usar o Painel de Controle do Skype for Business Server para habilitar o Estacionamento de Chamadas para Usuários

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.
    
2. Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Roteamento de Voz**.
    
4. Clique na guia **Política de Voz**.
    
5. Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.
    
6. Sob **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.
    
7. Clique em **OK** para salvar a política de voz
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar cmdlets para habilitar o estacionamento de chamada para usuários

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Execute:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Por exemplo, para habilitar o Estacionamento de Chamada para a política de voz global padrão:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Confira também



[Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md)

