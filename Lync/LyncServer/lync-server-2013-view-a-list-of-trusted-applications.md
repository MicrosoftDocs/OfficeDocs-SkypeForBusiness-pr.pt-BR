---
title: 'Lync Server 2013: exibir uma lista de aplicativos confiáveis'
description: 'Lync Server 2013: exibir uma lista de aplicativos confiáveis.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d45c682550640c3fc7284e0b60ca6844896b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574787"
---
# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Exibir uma lista de aplicativos confiáveis no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Você pode usar o painel de controle do Lync Server 2013 para exibir uma lista dos aplicativos confiáveis que você implantou no seu ambiente do Lync Server 2013. Um aplicativo confiável é um aplicativo baseado no SDK principal do Microsoft Unified Communications Managed API (UCMA) 3,0 Core que é confiável para o Lync Server 2013. Essa relação de confiança é resumida na seguinte lista:

  - Os aplicativos confiáveis não são desafiados para autenticação pelo Lync Server.

  - Os aplicativos confiáveis não são restringidos pelo Lync Server para transações SIP, conexões ou chamadas VoIP (Voice over Internet Protocol) de saída.

  - Aplicativos confiáveis podem representar qualquer usuário e podem participar de conferências sem que apareçam nas listas.

  - Os aplicativos confiáveis estão altamente disponíveis e resistentes.

No painel de controle do Lync Server, você pode ver o nome dos aplicativos, o pool em que eles são executados e a porta que eles utilizam.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  A partir de uma conta de usuário atribuída à função CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, faça logon em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Lync Server 2013, consulte [Planning for Role-Based Access Control in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **topologia** e em **aplicativo confiável**.

4.  Na página **aplicativo confiável** , clique em um cabeçalho de coluna para classificar os aplicativos, se necessário.

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

