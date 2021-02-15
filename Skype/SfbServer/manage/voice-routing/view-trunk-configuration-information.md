---
title: Exibir informações de configuração de tronco no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços.
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826161"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Exibir informações de configuração de tronco no Skype for Business Server

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços.

- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).

**Para exibir informações de configuração do tronco SIP usando o Painel de Controle do Skype for Business Server**

1. No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e em **Configuração de Tronco.**
2. Na guia **Configuração do** Tronco, você verá uma lista de todas as suas coleções de definições de configuração de tronco; para cada coleção, você verá valores para as propriedades **Name**, **Scope**, **State** e **Media bypass,** juntamente com o número de usos de **PSTN** **,** regras de número de chamada e regras de número **chamado** associadas à coleção. Para exibir informações adicionais sobre um coleção de configurações de tronco, clique na coleção de interesse, clique em **Editar** e depois clique em **Exibir detalhes**. Observe que você pode exibir informações detalhadas somente de uma coleção de configurações de tronco por vez.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração do tronco SIP usando cmdlets do Windows PowerShell

As definições de configuração do tronco SIP podem ser visualizadas usando o PowerShell do Skype for Business Server e o Get-CsTrunkConfiguration cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog do Lync Server Windows PowerShell "Início Rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell Remoto" em https://go.microsoft.com/fwlink/p/?linkId=255876 . SUBSTITUA OU REMOVA ESTE LINK.


**Para exibir informações de configuração do tronco SIP**

Para exibir informações sobre todas as suas definições de configuração de tronco SIP, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:

```powershell
Get-CsTrunkConfiguration
```

Isto retorna informações semelhantes à seguinte:

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)



