---
title: Processo de implantação do estacionamento de chamada no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
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
ms.openlocfilehash: 76046b8dbd39ecf9b17675ec8b3c1270a6c70122
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988308"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processo de implantação do estacionamento de chamada no Skype para negócios
 
Processo de implantação e etapas para estacionamento de chamada no Skype para Business Server Enterprise Voice.
  
Estacionamento de chamadas permite que um usuário Enterprise Voice colocar uma chamada em espera em um telefone e recuperar a chamada posteriormente discando um número interno (conhecido como uma órbita de estacionamento de chamada) de qualquer telefone.
  
Os componentes de estacionamento de chamadas usa automaticamente estão instalados e ativados no servidor do servidor Front-End ou Standard Edition, de quando você implanta o Enterprise Voice. No entanto, você deve usar as seguintes etapas para configurar o estacionamento de chamada antes que ele esteja disponível aos usuários. 
  
**Implantação do Processo de Estacionamento de Chamada**

|**Fase**|**Etapas**|**Grupos e funções necessários**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Configure os intervalos de órbita de estacionamento de chamada na tabela de órbita  <br/> |Use Skype para painel de controle do Business Server ou o cmdlet **New-CSCallParkOrbit** para criar os intervalos de órbita na tabela de órbita de estacionamento de chamada e associá-los com o serviço de aplicativo que hospeda o aplicativo de estacionamento de chamadas. <br/> **Observação:** Para perfeita integração com planos de discagem existente, intervalos de órbita geralmente são configurados como um bloco de extensões virtuais. Não há suporte para a atribuição dos números DID (Discagem Direta de Entrada) como números de órbita na tabela de órbita de estacionamento de chamada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar um intervalo de órbita de estacionamento de chamada no Skype para negócios](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Definir configurações de estacionamento de chamadas  <br/> | Use o cmdlet **Set-CsCpsConfiguration** para definir configurações de estacionamento de chamadas. No mínimo, recomendamos que você configure a opção **OnTimeoutURI** para configurar o destino de fallback para usar quando uma chamada estacionada expire. Você também pode configurar as seguintes configurações: <br/>  (Opcional) **EnableMusicOnHold** para ativar ou desativar música em espera. <br/>  (Opcional) **MaxCallPickupAttempts** para determinar o número de vezes que uma chamada estacionada toca novamente no telefone de atendimento antes de encaminhar a chamada para o fallback identificador URI (Uniform Resource). <br/>  (Opcional) **CallPickupTimeoutThreshold** para determinar a quantidade de tempo que passa após uma chamada foi estacionada, antes que toque novamente no telefone onde a chamada foi atendida. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Definir configurações de estacionamento de chamada no Skype para negócios](configure-call-park-settings.md) <br/> |
|Opcionalmente, personalize a música em espera  <br/> |Use o cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar e carregar um arquivo de áudio, se não quiser usar o padrão de música em espera. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizar a música de estacionamento de chamada em espera inSkype for Business](customize-call-park-music-on-hold.md) <br/> |
|Configurar a política de voz para habilitar o estacionamento de chamadas para usuários  <br/> |Use o Skype para painel de controle do Business Server ou o cmdlet **Set-CSVoicePolicy** com a opção **EnableCallPark** para habilitar o estacionamento de chamadas para usuários na política de voz. <br/> Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.  <br/> Se você tiver diversas políticas de voz, veja se a propriedade EnableCallPark está configurada para cada política, não somente para a padrão.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar o estacionamento de chamada para usuários no Skype para negócios](enable-call-park-for-users.md) <br/> |
|Verificar regras de normalização para Estacionamento de Chamadas  <br/> |Órbitas de estacionamento de chamadas não devem ser normalizadas. Verifique se suas regras de normalização não incluem nenhum intervalo de órbita. Se necessário, crie regras adicionais de normalização para evitar órbitas normalizadas.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verifique se as regras de normalização para estacionamento de chamada no Skype para negócios](verify-normalization-rules-for-call-park.md) <br/> |
|Verifique se a sua implantação do estacionamento de chamada  <br/> |Teste estacionar e recuperar chamadas para verificar se a configuração funciona como esperado.  <br/> |-  <br/> |[(Opcional) Verificar a implantação de estacionamento de chamada no Skype para negócios](optional-verify-call-park-deployment.md) <br/> |
   

