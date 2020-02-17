---
title: 'Lync Server 2013: marcar um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50dea89feb7e72c5076e58a38136d24b1b34499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Marcar um aplicativo de idioma de processamento SIP da Microsoft (MSPL) como crítico ou não crítico no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Os aplicativos de servidor do Microsoft SIP Processing Language (MSPL) são aplicativos de script que usam a linguagem de script do MSPL em vez da API do Microsoft Lync 2010. Alguns aplicativos de servidor do MSPL são especificados como críticos. Se um script for crítico, o script deve ser iniciado durante a inicialização do sistema para que o Lync Server 2013 seja iniciado. Se o script falhar enquanto o Lync Server estiver em execução, o servidor não será desligado, mas interromperá o envio de tráfego para o script e gravará erros no log de eventos.

Você pode usar o painel de controle do Lync Server para marcar aplicativos de servidor do Microsoft SIP Processing Language (MSPL) como críticos ou desmarcá-los.

Nem todos os scripts oferecem suporte a essa opção. Por exemplo, o script defaultrouting é marcado como crítico, e essa opção não pode ser alterada para defaultrouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Para marcar ou desmarcar um aplicativo de servidor do MSPL como crítico

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Topologia** e em **Aplicativo de Servidor**.

4.  Na página **Aplicativo de Servidor**, clique no título de uma coluna para classificar os aplicativos, se for necessário, e clique no aplicativo de servidor que você deseja modificar.

5.  Clique em **Ação**.

6.  Clique em **Marcar como crítico** ou **desmarcar como crítico** (ou seja, se o script suportar essa opção).

</div>

<div>

## <a name="see-also"></a>Confira Também


[Habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) no Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL) no Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gerenciando a topologia do Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

