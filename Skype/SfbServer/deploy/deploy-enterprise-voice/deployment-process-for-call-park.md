---
title: Processo de implantação para estacionamento de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processo de implantação e etapas para o parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 55fc887d77d3b68088bb396763a244ef81ce3a6b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233014"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processo de implantação para estacionamento de chamadas no Skype for Business
 
Processo de implantação e etapas para o parque de chamadas no Skype for Business Server Enterprise Voice.
  
O estacionamento de chamadas permite que um usuário de voz empresarial Coloque uma chamada em espera de um telefone e, em seguida, recupere a chamada mais tarde, discando um número interno (conhecido como um parque de chamadas órbita) de qualquer telefone.
  
Os componentes que chamam o parque usa são instalados e habilitados automaticamente no servidor front-end ou no servidor Standard Edition ao implantar o Enterprise Voice. No entanto, você deve usar as etapas a seguir para configurar o estacionamento de chamadas antes que ele esteja disponível para os usuários. 
  
**Implantação do Processo de Estacionamento de Chamada**

|**Fase**|**Etapas**|**Grupos e funções necessários**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Configure os intervalos de órbita de estacionamento de chamada na tabela de órbita  <br/> |Use o painel de controle do Skype for Business Server ou o cmdlet **New-CSCallParkOrbit** para criar os intervalos de órbita na tabela órbita do estacionamento de chamada e associá-los ao serviço de aplicativo que hospeda o aplicativo parque de chamadas. <br/> **Observação:** Para integração perfeita com planos de discagem existentes, os intervalos de órbita geralmente são configurados como um bloco de extensões virtuais. Não há suporte para a atribuição dos números DID (Discagem Direta de Entrada) como números de órbita na tabela de órbita de estacionamento de chamada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar uma faixa de opções de estacionamento de chamada no Skype for Business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Definir configurações de estacionamento de chamadas  <br/> | Use o cmdlet **set-CsCpsConfiguration** para configurar as configurações de estacionamento de chamadas. No mínimo, recomendamos que você configure a opção **OnTimeoutURI** para configurar o destino de fallback a ser usado quando uma chamada estacionada expirar. Você também pode definir as seguintes configurações: <br/>  (Opcional) **EnableMusicOnHold** para habilitar ou desabilitar a música em espera. <br/>  (Opcional)  **MaxCallPickupAttempts** para determinar o número de vezes que uma chamada estacionada toca novamente no telefone de atendimento, antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback. <br/>  (Opcional)  **CallPickupTimeoutThreshold** para determinar o tempo decorrido depois que a chamada foi estacionada, antes que toque novamente no telefone em que foi atendida. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurar as definições do parque de chamadas no Skype for Business](configure-call-park-settings.md) <br/> |
|Opcionalmente, personalize a música em espera  <br/> |Use o cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar e carregar um arquivo de áudio, se você não deseja usar a música em espera padrão. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizar o recurso de chamadas de música com o recurso para reter o Skype for Business](customize-call-park-music-on-hold.md) <br/> |
|Configurar a política de voz para habilitar o estacionamento de chamadas para usuários  <br/> |Use o painel de controle do Skype for Business Server ou o cmdlet **set-CSVoicePolicy** com a opção **EnableCallPark** para habilitar o estacionamento de chamadas para usuários na política de voz. <br/> Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.  <br/> Se você tiver diversas políticas de voz, veja se a propriedade EnableCallPark está configurada para cada política, não somente para a padrão.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar o estacionamento de chamadas para usuários no Skype for Business](enable-call-park-for-users.md) <br/> |
|Verificar regras de normalização para Estacionamento de Chamadas  <br/> |Órbitas de estacionamento de chamadas não devem ser normalizadas. Verifique se suas regras de normalização não incluem nenhum intervalo de órbita. Se necessário, crie regras adicionais de normalização para evitar órbitas normalizadas.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verificar as regras de normalização para o estacionamento de chamadas no Skype for Business](verify-normalization-rules-for-call-park.md) <br/> |
|Verifique a implantação do estacionamento de chamadas  <br/> |Teste estacionar e recuperar chamadas para verificar se a configuração funciona como esperado.  <br/> |-  <br/> |[Adicionais Verificar a implantação do estacionamento de chamadas no Skype for Business](optional-verify-call-park-deployment.md) <br/> |
   

