---
title: 'Lync Server 2013: habilitar estacionamento de chamada para usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b86c562f9ccec700ead45f837d231f97ced10e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Habilitar estacionamento de chamada para usuários no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-11_

Os usuários não podem estacionar chamadas ou recuperar chamadas estacionadas até que sejam habilitados para estacionamento de chamada na política de voz.

<div>


> [!NOTE]  
> Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.



</div>

Você pode habilitar o estacionamento de chamadas no escopo global ou no escopo do site ou do usuário. O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global. Se você tiver várias políticas de voz, revise todas as políticas para habilitar o estacionamento de chamadas, e não apenas a política global.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Para usar o painel de controle do Lync Server para habilitar o estacionamento de chamada para usuários

1.  Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Roteamento de Voz**.

4.  Clique na guia **Política de Voz**.

5.  Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.

6.  Sob **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.

7.  Clique em **OK** para salvar a política de voz

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar cmdlets para habilitar o estacionamento de chamada para usuários

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Por exemplo, para habilitar o estacionamento de chamada para a política de voz global padrão:
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

