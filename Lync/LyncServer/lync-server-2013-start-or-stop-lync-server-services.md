---
title: 'Lync Server 2013: iniciar ou parar serviços do Lync Server'
description: 'Lync Server 2013: iniciar ou parar serviços do Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541857"
---
# <a name="start-or-stop-lync-server-2013-services"></a>Iniciar ou interromper os serviços do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

Você pode usar o painel de controle do Lync Server para iniciar ou parar todos os serviços do Lync Server 2013 em execução em um computador específico ou para iniciar ou parar um serviço específico.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Para iniciar ou parar todos os serviços do Lync Server em um computador

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013. Você pode determinar se foi atribuído o CsServerAdministrator ou a função RBAC do CsAdministrator executando um comando semelhante ao seguinte:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Topologia** e em **Status**.

4.  Na página **Status**, classifique ou procure pela lista para encontrar o computador executando os serviços que você deseja iniciar ou parar e clique neles.

5.  Clique em **Ação**.

6.  Clique em **Iniciar todos os serviços** ou **Parar todos os serviços**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Para iniciar ou parar um serviço específico

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Topologia** e em **Status**.

4.  Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.

5.  Clique em **Propriedades**.

6.  Classifique a lista de serviços, se necessário e clique no serviço que você deseja iniciar ou parar.

7.  Clique em **Ação**.

8.  Clique em **Iniciar serviço** ou **Parar serviço**.

9.  Clique em **Fechar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Impedir sessões para serviços no Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Gerenciando a topologia do Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

