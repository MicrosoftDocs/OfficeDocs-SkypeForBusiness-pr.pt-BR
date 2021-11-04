---
title: Exibir informações de configuração de tronco em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços.
ms.openlocfilehash: b27e3dd72e7a4aebee907541b1ec0250cf7cfd3f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778251"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Exibir informações de configuração de tronco em Skype for Business Server

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços.

- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).

**Para exibir informações de configuração de tronco SIP usando Skype for Business Server Painel de Controle**

1. No painel Skype for Business Server controle, clique em **Roteamento** de Voz e clique em **Configuração do Tronco.**
2. Na guia **Configuração do** Tronco, você verá uma lista de todas as suas coleções de configurações de tronco; para cada coleção, você verá valores para as propriedades  **Name**, **Scope**, **State** e Media **bypass,** juntamente com o número de **usos de PSTN,** regras de número de chamada e regras de número chamado associadas à coleção.  Para exibir informações adicionais sobre um coleção de configurações de tronco, clique na coleção de interesse, clique em **Editar** e depois clique em **Exibir detalhes**. Observe que você pode exibir informações detalhadas somente de uma coleção de configurações de tronco por vez.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de tronco SIP usando Windows PowerShell cmdlets

As definições de configuração do tronco SIP podem ser exibidas usando Skype for Business Server PowerShell e o cmdlet Get-CsTrunkConfiguration de usuário. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog do Lync Server Windows PowerShell "Início Rápido: Gerenciamento do Microsoft Lync Server 2010 Usando o PowerShell Remoto" em https://go.microsoft.com/fwlink/p/?linkId=255876 . SUBSTITUA OU REMOVA ESSE LINK.


**Para exibir informações de configuração de tronco SIP**

Para exibir informações sobre todas as configurações de tronco SIP, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:

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
Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration.](/powershell/module/skype/Get-CsTrunkConfiguration)