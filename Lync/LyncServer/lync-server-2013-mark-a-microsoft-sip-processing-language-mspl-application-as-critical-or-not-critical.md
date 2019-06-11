---
title: 'Lync Server 2013: marque um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Marcar um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Os aplicativos do servidor Microsoft SIP Processing Language (MSPL) são aplicativos somente script que usam a linguagem de script MSPL em vez da API do Microsoft Lync 2010. Alguns aplicativos do MSPL Server são especificados como críticos. Se um script for essencial, o script deve iniciar durante a inicialização do sistema para que o Lync Server 2013 seja iniciado. Se o script falhar enquanto o Lync Server estiver em execução, o servidor não será desligado, mas ele para de enviar o tráfego para o script e gravará erros no log de eventos.

Você pode usar o painel de controle do Lync Server para marcar os aplicativos do servidor do Microsoft SIP Processing Language (MSPL) como críticos ou desmarcá-los.

Nem todos os scripts dão suporte a essa opção. Por exemplo, o script defaultrouting é marcado como Critical, e essa opção não pode ser alterada para defaultrouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Para marcar ou desmarcar um aplicativo de servidor MSPL como crítico

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **aplicativo para servidor**.

4.  Na página **aplicativo do servidor** , clique em um título de coluna para classificar os aplicativos, se necessário, e clique no aplicativo servidor que você deseja modificar.

5.  Clique em **ação**.

6.  Clique em **Marcar como crítica** ou desmarcar **como crítica** (ou seja, se o script der suporte a essa opção).

</div>

<div>

## <a name="see-also"></a>Confira também


[Habilitar ou desabilitar um aplicativo de servidor Microsoft SIP Processing Language (MSPL) no Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Exibir aplicativos de servidor do Idioma de Processamento SIP da Microsoft (MSPL) no Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gerenciando a topologia do Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

