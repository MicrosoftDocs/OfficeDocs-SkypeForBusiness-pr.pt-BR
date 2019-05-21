---
title: Exibir informações de configuração de tronco no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274867"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Exibir informações de configuração de tronco no Skype for Business Server

As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.

- Se o desvio de mídia deve ser ativado nos troncos.
- As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.
- Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.

Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).

**Para ver as informações de configuração do tronco SIP usando o painel de controle do Skype for Business Server**

1. No painel de controle do Skype for Business Server, clique em **Roteamento de voz**e, em seguida, clique em **configuração de tronco**.
2. Na guia **configuração de tronco** , você verá uma lista de todas as suas coleções de definições de configuração de tronco; para cada coleção, você verá os valores para as propriedades **nome**, **escopo**, **estado**e **ignorar mídia** , juntamente com o número de **usos de PSTN**, **as regras de número de chamada**e **as regras de número chamadas** associadas com a coleção. Para ver detalhes adicionais sobre uma coleção de definições de configuração de tronco, clique na coleção de interesse, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**. Observe que você pode exibir informações detalhadas apenas para um conjunto de configurações de tronco de configuração de tronco de cada vez.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de tronco SIP usando cmdlets do Windows PowerShell

As configurações de tronco SIP podem ser exibidas usando o Skype for Business Server PowerShell e o cmdlet Get-CsTrunkConfiguration. Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o http://go.microsoft.com/fwlink/p/?linkId=255876Microsoft Lync Server 2010 usando o PowerShell remoto" em. SUBSTITUIR OU REMOVER ESTE LINK.


**Para ver as informações de configuração do tronco SIP**

Para ver as informações sobre todas as suas configurações de tronco SIP, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:

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
Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



