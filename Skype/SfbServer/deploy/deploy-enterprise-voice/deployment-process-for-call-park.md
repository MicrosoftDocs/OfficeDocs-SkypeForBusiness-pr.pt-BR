---
title: Processo de implantação do Estacionamento de Chamada no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processo de implantação e etapas para estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: d7bc57664b7f6880cde7481c3ba5aff97c2d4392
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-call-park-in-skype-for-business-2015"></a>Processo de implantação do Estacionamento de Chamada no Skype for Business 2015
 
Processo de implantação e etapas para estacionamento de chamada no Skype para Business Server Enterprise Voice.
  
Estacionamento de chamadas permite que um usuário Enterprise Voice colocar uma chamada em espera em um telefone e recuperar a chamada posteriormente discando um número interno (conhecido como uma órbita de estacionamento de chamada) de qualquer telefone.
  
Os componentes de estacionamento de chamadas usa automaticamente estão instalados e ativados no servidor do servidor Front-End ou Standard Edition, de quando você implanta o Enterprise Voice. No entanto, você deve usar as seguintes etapas para configurar o estacionamento de chamada antes que ele esteja disponível aos usuários. 
  
**Processo de implantação do estacionamento de chamada**

|**Fase**|**Etapas**|**Grupos e funções necessários**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Configure os intervalos de órbita de estacionamento de chamada na tabela de órbita  <br/> |Use Skype para painel de controle do Business Server ou o cmdlet **New-CSCallParkOrbit** para criar os intervalos de órbita na tabela de órbita de estacionamento de chamada e associá-los com o serviço de aplicativo que hospeda o aplicativo de estacionamento de chamadas. <br/> **Observação:** Para perfeita integração com planos de discagem existente, intervalos de órbita geralmente são configurados como um bloco de extensões virtuais. Não há suporte para a atribuição dos números DID (Discagem Direta de Entrada) como números de órbita na tabela de órbita de estacionamento de chamada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar um intervalo de órbita de estacionamento de chamada no Skype para negócios 2015](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Definir configurações de estacionamento de chamadas  <br/> | Use o cmdlet **Set-CsCpsConfiguration** para definir configurações de estacionamento de chamadas. No mínimo, recomendamos que você configure a opção **OnTimeoutURI** para configurar o destino de fallback para usar quando uma chamada estacionada expire. Você também pode configurar as seguintes configurações: <br/>  (Opcional) **EnableMusicOnHold** para ativar ou desativar música em espera. <br/>  (Opcional) **MaxCallPickupAttempts** para determinar o número de vezes que uma chamada estacionada toca novamente no telefone de atendimento antes de encaminhar a chamada para o fallback identificador URI (Uniform Resource). <br/>  (Opcional) **CallPickupTimeoutThreshold** para determinar a quantidade de tempo que passa após uma chamada foi estacionada, antes que toque novamente no telefone onde a chamada foi atendida. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Definir configurações de estacionamento de chamada no Skype para negócios 2015](configure-call-park-settings.md) <br/> |
|Opcionalmente, personalize a música em espera  <br/> |Use o cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar e carregar um arquivo de áudio, se não quiser usar o padrão de música em espera. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizar a música de estacionamento de chamada em espera inSkype para negócios 2015](customize-call-park-music-on-hold.md) <br/> |
|Configurar a política de voz para habilitar o estacionamento de chamadas para usuários  <br/> |Use o Skype para painel de controle do Business Server ou o cmdlet **Set-CSVoicePolicy** com a opção **EnableCallPark** para habilitar o estacionamento de chamadas para usuários na política de voz. <br/> Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.  <br/> Se você tiver diversas políticas de voz, veja se a propriedade EnableCallPark está configurada para cada política, não somente para a padrão.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar o estacionamento de chamada para usuários no Skype para negócios 2015](enable-call-park-for-users.md) <br/> |
|Verificar regras de normalização para Estacionamento de Chamadas  <br/> |Órbitas de estacionamento de chamadas não devem ser normalizadas. Verifique se suas regras de normalização não incluem nenhum intervalo de órbita. Se necessário, crie regras adicionais de normalização para evitar órbitas normalizadas.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verifique se as regras de normalização para estacionamento de chamada no Skype para negócios 2015](verify-normalization-rules-for-call-park.md) <br/> |
|Verifique se a sua implantação do estacionamento de chamada  <br/> |Teste estacionar e recuperar chamadas para verificar se a configuração funciona como esperado.  <br/> |-  <br/> |[(Opcional) Verificar a implantação de estacionamento de chamada no Skype para negócios 2015](optional-verify-call-park-deployment.md) <br/> |
   

