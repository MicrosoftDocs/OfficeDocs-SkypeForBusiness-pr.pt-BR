---
title: 'Lync Server 2013: exibir uma lista de aplicativos confiáveis'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23866bfbc437d87911a84d065ae7f501c7d80466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Exibir uma lista de aplicativos confiáveis no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Você pode usar o painel de controle do Lync Server 2013 para exibir uma lista dos aplicativos confiáveis que você implantou em seu ambiente do Lync Server 2013. Um aplicativo confiável é um aplicativo baseado no SDK do núcleo do Microsoft Unified Communications Managed (UCMA) 3,0, que é confiável para o Lync Server 2013. Essa relação de confiança é resumida na seguinte lista:

  - Aplicativos confiáveis não são desafiados para autenticação pelo Lync Server.

  - Os aplicativos confiáveis não são restringidos pelo Lync Server para transações SIP, conexões ou chamadas de protocolo de voz por Internet (VoIP) de saída.

  - Aplicativos confiáveis podem representar qualquer usuário e podem participar de conferências sem que apareçam em escalas.

  - Aplicativos confiáveis são altamente disponíveis e resilientes.

No painel de controle do Lync Server, você pode ver o nome dos aplicativos, o pool onde eles são executados e a porta que eles usam.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  Usando uma conta de usuário atribuída à função do CsServerAdministrator, CsAdministrator, CsHelpDesk, ou CsViewOnlyAdministrator, faça logon em qualquer computador de sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Lync Server 2013, consulte [planejando o controle de acesso baseado em função no Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **topologia** e clique em **aplicativo confiável**.

4.  Na página **aplicativo confiável** , clique em um título de coluna para classificar os aplicativos, se necessário.

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando a topologia do Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

