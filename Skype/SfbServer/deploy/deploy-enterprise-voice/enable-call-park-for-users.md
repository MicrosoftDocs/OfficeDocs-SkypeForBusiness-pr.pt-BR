---
title: Habilitar o estacionamento de chamada para usuários no Skype para negócios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilite usuários para o estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 98b02294beb633e5d9a0147fcce7257a4497753d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894540"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Habilitar o estacionamento de chamada para usuários no Skype para negócios
 
Habilite usuários para o estacionamento de chamada no Skype para Business Server Enterprise Voice.
  
Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários. Os usuários não podem estacionar chamadas ou recuperar chamadas estacionadas até estarem habilitados para o estacionamento de chamadas na política de voz.
  
É possível habilitar o estacionamento de chamada no escopo global ou no escopo de site ou usuário. O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global. Se você tiver várias políticas de voz, revise todas as diretivas para habilitar o estacionamento de chamada, não apenas a política global.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Usar Skype para painel de controle do Business Server para habilitar o estacionamento de chamada para usuários

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.
    
2. Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerdo, clique em **Roteamento de voz**.
    
4. Clique na guia **Política de Voz**.
    
5. Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.
    
6. Em **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.
    
7. Clique em **OK** para salvar a política de voz
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar Cmdlets para habilitar o estacionamento de chamada para usuários

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

## <a name="see-also"></a>Consulte Também



[Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios](voice-policy-and-pstn-usage-records.md)

