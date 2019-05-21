---
title: Habilitar o estacionamento de chamadas para usuários no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilite os usuários para o parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 326b1156ea3b300301b46324d90dbc7dde088b3d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291585"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Habilitar o estacionamento de chamadas para usuários no Skype for Business
 
Habilite os usuários para o parque de chamadas no Skype for Business Server Enterprise Voice.
  
Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários. Os usuários não podem estacionar chamadas nem recuperar chamadas estacionadas até que elas sejam habilitadas para estacionamento de chamadas na política de voz.
  
Você pode habilitar o estacionamento de chamadas no escopo global ou no escopo do site ou no escopo do usuário. O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global. Se você tiver várias políticas de voz, examine todas as políticas para habilitar o estacionamento de chamadas, não apenas a política global.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Para usar o painel de controle do Skype for Business Server para habilitar o estacionamento de chamadas para usuários

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerdo, clique em **Roteamento de voz**.
    
4. Clique na guia **Política de Voz**.
    
5. Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.
    
6. Em **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.
    
7. Clique em **OK** para salvar a política de voz
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar cmdlets para habilitar o estacionamento de chamadas para usuários

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute:
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Por exemplo, para habilitar o estacionamento de chamadas para a política de voz global padrão:
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Confira também



[Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md)

