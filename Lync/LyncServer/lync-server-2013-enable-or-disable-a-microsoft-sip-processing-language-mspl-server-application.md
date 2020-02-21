---
title: 'Lync Server 2013: habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c19f9918aa1740c8ac80e2c2a51466f5bf2022b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Você pode usar o painel de controle do Lync Server para habilitar ou desabilitar aplicativos de servidor do Microsoft SIP Processing Language (MSPL) que são executados no seu ambiente do Lync Server 2013. Esses aplicativos são aplicativos somente com scripts que usam uma linguagem de scripts em vez do API do Microsoft Lync 2013 Preview.

Nem todos os scripts podem ser habilitados ou desabilitados. Por exemplo, o script DefaultRouting está habilitado e essa opção não pode ser alterada para DefaultRouting.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Para habilitar ou desabilitar um aplicativo de servidor do MSPL

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Topologia** e em **Aplicativo de Servidor**.

4.  Na página **Aplicativo de Servidor**, clique no título de uma coluna para classificar os aplicativos, se for necessário, e clique no aplicativo de servidor que você deseja modificar.

5.  Clique em **Ação**.

6.  Clique em **Habilitar aplicativo** ou **Desabilitar aplicativo** (ou seja, se o script suportar essa opção).

</div>

<div>

## <a name="see-also"></a>Confira também


[Marcar um aplicativo de idioma de processamento SIP da Microsoft (MSPL) como crítico ou não crítico no Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL) no Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gerenciando a topologia do Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

