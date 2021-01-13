---
title: Processo de implantação do Estacionamento de Chamadas no Skype for Business
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
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processo de implantação e etapas para estacionamento de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 0ddc46c391d362fde922e682db0813ad1c0d72bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812351"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processo de implantação do Estacionamento de Chamadas no Skype for Business
 
Processo de implantação e etapas para estacionamento de chamadas no Skype for Business Server Enterprise Voice.
  
O Estacionamento de Chamada permite que um usuário do Enterprise Voice coloque uma chamada em espera em um telefone e recupere a chamada mais tarde discando um número interno (conhecido como órbita de Estacionamento de Chamadas) de qualquer telefone.
  
Os componentes que o Estacionamento de Chamada usa são instalados e habilitados automaticamente no Servidor front-end ou servidor Standard Edition quando você implanta o Enterprise Voice. No entanto, você deve usar as etapas a seguir para configurar o Estacionamento de Chamada antes que ele seja disponibilizado para os usuários. 
  
**Implantação do Processo de Estacionamento de Chamada**

|**Fase**|**Etapas**|**Grupos e funções exigidos**|**Documentação da implantação**|
|:-----|:-----|:-----|:-----|
|Configure os intervalos de órbita de estacionamento de chamada na tabela de órbita  <br/> |Use o Painel de Controle do Skype for Business Server ou o cmdlet **New-CSCallParkOrbit** para criar os intervalos de órbita na tabela de órbita de estacionamento de chamada e associá-los ao serviço de Aplicativo que hospeda o aplicativo Estacionamento de Chamada. <br/> **Observação:** Para uma integração perfeita com planos de discagem existentes, os intervalos de órbitas são normalmente configurados como um bloco de ramais virtuais. A atribuição dos números DID (Discagem Direta de Entrada) como números de órbita na tabela de órbita de estacionamento de chamada não é suportada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar um intervalo de órbita de Estacionamento de Chamadas no Skype for Business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Definir configurações de Estacionamento de Chamada  <br/> | Use o cmdlet **Set-CsCpsConfiguration** para definir as configurações de Estacionamento de Chamada. No mínimo, recomendamos que você configure a opção **OnTimeoutURI** para configurar o destino de fallback a ser usado quando uma chamada estacionada estime out. Você também pode definir as seguintes configurações: <br/>  (Opcional) **EnableMusicOnHold** para ativar ou desativar música em espera. <br/>  (Opcional) **MaxCallPickupAttempts** para determinar o número de vezes que uma chamada estacionada toca novamente no telefone de atendimento, antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback. <br/>  (Opcional) **CallPickupTimeoutThreshold** para determinar o tempo decorrido depois que a chamada foi estacionada, antes que toque novamente no telefone em que foi atendida. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Definir configurações de Estacionamento de Chamadas no Skype for Business](configure-call-park-settings.md) <br/> |
|Opcionalmente, personalize a música em espera  <br/> |Use o cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar e carregar um arquivo de áudio, se você não deseja usar a música em espera padrão. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizar a música de espera do Estacionamento de Chamada noSkype for Business](customize-call-park-music-on-hold.md) <br/> |
|Configurar política de voz para habilitar o Estacionamento de Chamadas para usuários  <br/> |Use o Painel de Controle do Skype for Business Server ou o cmdlet **Set-CSVoicePolicy** com a opção **EnableCallPark** para habilitar o Estacionamento de Chamada para usuários na política de voz. <br/> Por padrão, o Estacionamento de Chamada está desabilitado para todos os usuários.  <br/> Se você tiver diversas políticas de voz, veja se a propriedade EnableCallPark está configurada para cada política, não somente para a padrão.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar Estacionamento de Chamada para usuários no Skype for Business](enable-call-park-for-users.md) <br/> |
|Verificar regras de normalização para o Estacionamento de Chamada  <br/> |Órbitas de estacionamento de chamadas não devem ser normalizadas. Verifique se suas regras de normalização não incluem nenhum intervalo de órbita. Se necessário, crie regras adicionais de normalização para evitar órbitas normalizadas.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verificar regras de normalização para Estacionamento de Chamadas no Skype for Business](verify-normalization-rules-for-call-park.md) <br/> |
|Verificar a implantação do Estacionamento de Chamada  <br/> |Teste o estacionamento e a recuperação de chamadas para garantir que sua configuração funcione conforme o esperado.  <br/> |-  <br/> |[(Opcional) Verificar a implantação do Estacionamento de Chamada no Skype for Business](optional-verify-call-park-deployment.md) <br/> |
   

