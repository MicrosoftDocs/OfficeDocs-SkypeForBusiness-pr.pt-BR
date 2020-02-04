---
title: 'Lync Server 2013: iniciar ou parar serviços do Lync Server'
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
ms.openlocfilehash: a986f0bef8c41cf5113e99504369974562e294a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Iniciar ou parar os serviços do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-05_

Você pode usar o painel de controle do Lync Server para iniciar ou parar todos os serviços do Lync Server 2013 em execução em um computador específico ou para iniciar ou parar um serviço específico.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Para iniciar ou parar todos os serviços do Lync Server em um computador

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013. Você pode determinar se você atribuiu o CsServerAdministrator ou a função RBAC CsAdministrator executando um comando semelhante ao seguinte:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.

4.  Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços que você deseja iniciar ou parar e, em seguida, clique nele.

5.  Clique em **ação**.

6.  Clique em **Iniciar todos os serviços** ou **parar todos os serviços**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Para iniciar ou parar um serviço específico

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.

4.  Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.

5.  Clique em **Propriedades**.

6.  Classifique a lista de serviços, se necessário, e clique no serviço que você deseja iniciar ou parar.

7.  Clique em **ação**.

8.  Clique em **Iniciar serviço** ou **parar serviço**.

9.  Clique em **Fechar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Evitar sessões para serviços no Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Gerenciando a topologia do Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

