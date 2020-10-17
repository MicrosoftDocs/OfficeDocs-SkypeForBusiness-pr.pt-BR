---
title: 'Lync Server 2013: Configurando o escape de caixa postal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c3faf28bdd85f32de1560d35aaf35392fef9746
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516948"
---
# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Configurando o escape de caixa postal no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

Quando um usuário configura ligação simultânea para um celular, um chamador geralmente é roteado para a caixa postal pessoal do usuário, caso o celular esteja desligado, sem bateria ou fora de área. Com o Lync Server 2013, os usuários podem optar por ter chamadas relacionadas à empresa roteadas para seu sistema de caixa postal corporativo. Especificamente, um temporizador pode ser configurado e, se a chamada for atendida pela caixa postal da operadora dentro do intervalo de tempo definido, o Lync Server será desconectado do sistema de caixa postal da operadora (e da caixa postal do usuário), enquanto os pontos de extremidade restantes do usuário no sistema corporativo continuam a tocar. Desta maneira, o chamador será roteado automaticamente para a caixa postal corporativa do usuário.

Essa configuração é realizada usando o cmdlet do Shell de gerenciamento do Lync Server, **set-CsVoicePolicy**, no nível de política de voz, com os parâmetros a seguir.

<div>

## <a name="to-configure-voice-mail-escape"></a>Para configurar o escape de caixa postal

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:
    
      - **EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape
    
      - **PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.

</div>

<div>

## <a name="example"></a>Exemplo

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>Consulte também


[Configurando políticas de voz e registros de uso de PSTN para autorizar recursos e privilégios de chamada no Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

