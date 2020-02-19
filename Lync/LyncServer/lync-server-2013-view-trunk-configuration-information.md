---
title: 'Lync Server 2013: exibir informações de configuração do tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b1e232cda56258a530f1cd0f5a0106d9b7725ca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Exibir informações de configuração de tronco no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

  - Se o bypass de mídia deve ser habilitado nos troncos.

  - As condições nas quais os pacotes RTCP são enviados.

  - Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala o Microsoft Lync Server 2013, uma coleção global de definições de configuração do tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>Para exibir informações de configuração do tronco SIP usando o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **Roteamento de voz** e em **configuração de tronco**.

2.  Na guia **configuração de tronco** , você verá uma lista de todas as definições de configuração de tronco; para cada coleção, você verá os valores das propriedades de **nome**, **escopo**, **estado**e **bypass de mídia** , juntamente com o número de **usos de PSTN**, regras de número de **chamada**e **regras de número chamadas** associadas à coleção. Para exibir informações adicionais sobre um coleção de configurações de tronco, clique na coleção de interesse, clique em **Editar** e depois clique em **Exibir detalhes**. Observe que você pode exibir informações detalhadas somente de uma coleção de configurações de tronco por vez.

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração do tronco SIP usando os cmdlets do Windows PowerShell

As definições de configuração do tronco SIP podem ser exibidas usando o Lync Server PowerShell e o cmdlet Get-CsTrunkConfiguration. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>Para exibir informações de configuração do tronco SIP

  - Para exibir informações sobre todas as suas definições de configuração de tronco SIP, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsTrunkConfiguration
    
    Isto retorna informações semelhantes à seguinte:
    
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

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

