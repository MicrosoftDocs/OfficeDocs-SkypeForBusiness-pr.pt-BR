---
title: 'Lync Server 2013: exibir informações de configuração de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf496382ed33b95e8de9f387a8623fb0984ed28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Exibir informações de configuração de tronco no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. Essas configurações realizam atividades como especificar:

  - Se o desvio de mídia deve ser ativado nos troncos.

  - As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.

  - Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.

Ao instalar o Microsoft Lync Server 2013, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>Para ver as informações de configuração do tronco SIP usando o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **Roteamento de voz** e, em seguida, clique em **configuração de tronco**.

2.  Na guia **configuração de tronco** , você verá uma lista de todas as suas definições de configuração de tronco; para cada coleção, você verá os valores para as propriedades **nome**, **escopo**, **estado**e **ignorar mídia** , juntamente com o número de **usos de PSTN**, **as regras de número de chamada**e **as regras de número chamadas** associadas com a coleção. Para ver detalhes adicionais sobre uma coleção de definições de configuração de tronco, clique na coleção de interesse, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**. Observe que você pode exibir informações detalhadas apenas para um conjunto de configurações de tronco de configuração de tronco de cada vez.

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de tronco SIP usando cmdlets do Windows PowerShell

As configurações de tronco SIP podem ser exibidas usando o Lync Server PowerShell e o cmdlet Get-CsTrunkConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>Para ver as informações de configuração do tronco SIP

  - Para ver as informações sobre todas as suas configurações de tronco SIP, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsTrunkConfiguration
    
    Isso retornará informações parecidas com:
    
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

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

