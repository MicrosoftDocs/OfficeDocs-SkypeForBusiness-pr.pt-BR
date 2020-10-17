---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a7ddba431e1c921df9b3880ee9af73f71584b5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515918"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificar coexistência de pool piloto com pool herdado

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Verifique o pool na Ferramenta Administrativa do Office Communications Server 2007 R2

1.  Abra a ferramenta administrativa do Office Communications Server 2007 R2.

2.  Expanda o nó **Floresta**, expanda o nó **ServidoresStandard Edition** ou **Pools Enterprise** e expanda o pool ou o nome do servidor.

3.  Verifique se os serviços do Office Communications Server 2007 R2 estão em execução no pool.
    
    ![Console de administração do Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console de administração do Office Communications Server 2007 R2")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Verificar o pool piloto no painel de controle do Lync Server 2013

1.  A partir de uma conta de usuário que seja membro da função CsAdministrator, faça logon no servidor front-end do Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Clique em **Topologia**.

4.  Verifique se os servidores que você implantou estão presentes em seu pool piloto.
    
    ![Página de topologia do painel de controle do Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Página de topologia do painel de controle do Lync Server")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Verificar se os serviços do Lync Server 2013 foram iniciados

1.  No servidor front-end do Lync Server 2013, abra o applet de **Serviços** no grupo **Ferramentas administrativas** .

2.  Verifique se os serviços listados correspondem à lista na seguinte figura.
    
    ![Página de serviços mostrando os serviços do Lync iniciado](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Página de serviços mostrando os serviços do Lync iniciado")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

