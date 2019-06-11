---
title: 'Lync Server 2013: habilitar ou desabilitar um aplicativo de servidor Microsoft SIP Processing Language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7ff3379f0e32166ceb263e1dbda46117b6984a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Habilitar ou desabilitar um aplicativo de servidor Microsoft SIP Processing Language (MSPL) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Você pode usar o painel de controle do Lync Server para habilitar ou desabilitar aplicativos do servidor Microsoft SIP Processing Language (MSPL) que são executados em seu ambiente do Lync Server 2013. Esses aplicativos são aplicativos somente de script que usam uma linguagem de script em vez da API do Microsoft Lync 2013 Preview.

Nem todos os scripts podem ser habilitados ou desabilitados. Por exemplo, o script defaultrouting está habilitado e essa opção não pode ser alterada para defaultrouting.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Para habilitar ou desabilitar um aplicativo de servidor MSPL

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **aplicativo para servidor**.

4.  Na página **aplicativo do servidor** , clique em um título de coluna para classificar os aplicativos, se necessário, e clique no aplicativo servidor que você deseja modificar.

5.  Clique em **ação**.

6.  Clique em **habilitar aplicativo** ou em **desabilitar aplicativo** (ou seja, se o script der suporte a essa opção).

</div>

<div>

## <a name="see-also"></a>Confira também


[Marcar um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico no Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Exibir aplicativos de servidor do Idioma de Processamento SIP da Microsoft (MSPL) no Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gerenciando a topologia do Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

