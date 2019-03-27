---
title: Exibir informações de configuração de tronco no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços.
ms.openlocfilehash: 6ba97fa4650b8d62be625256ff4d3b9a3bb7cc68
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892162"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Exibir informações de configuração de tronco no Skype para Business Server

Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços.

- Se o desvio de mídia deve ser ativado nos troncos.
- As condições nas quais os pacotes RTCP (protocolo) de controle de transporte em tempo real são enviados.
- Ou não a criptografia do protocolo em tempo real seguro (SRTP) é necessário em cada tronco.

Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).

**Para exibir informações de configuração de tronco SIP usando Skype para o painel de controle do servidor de negócios**

1. Na Skype para painel de controle do Business Server, clique em **Roteamento de voz**e clique em **Configuração de tronco**.
2. Na guia **Configuração de tronco** , você verá uma lista de todos os seus tronco coleções de configurações do; para cada conjunto de valores para as propriedades de **nome**, **escopo**, **estado**e **bypass de mídia** , juntamente com o número de **usos da PSTN**, **as regras de número de chamada**e **regras de número de chamada** associado você verá com a coleção. Para ver detalhes adicionais sobre uma coleção de definições de configuração de tronco, clique no conjunto de interesse, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**. Observe que você pode visualizar informações detalhadas apenas para uma coleção de definições de configuração de tronco por vez.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de tronco SIP usando cmdlets do Windows PowerShell

Configuração de tronco configurações podem ser exibidas usando Skype para Business Server PowerShell e o cmdlet Get-CsTrunkConfiguration de SIP. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog do Lync Server Windows PowerShell "Rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell" em http://go.microsoft.com/fwlink/p/?linkId=255876. SUBSTITUIR OU REMOVER ESTE LINK.


**Para exibir informações de configuração de tronco SIP**

Para exibir informações sobre todas as suas definições de configuração de tronco SIP, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:

`Get-CsTrunkConfiguration`

Isso retornará informações parecidas com:

```
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
Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



