---
title: Verificar a coexistência do pool piloto com o pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f361882d0994b8e3add5447dbcaaffe2b75127d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificar a coexistência do pool piloto com o pool herdado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Depois de implantar o pool piloto, você deve verificar a coexistência de dois pools usando ferramentas administrativas para exibir as informações dos pools. Para os pools do Lync Server 2013 e pools herdados, você deve usar o painel de controle do Lync Server 2013 e as ferramentas do construtor de topologia.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Verificar se os serviços do Lync Server 2013 foram iniciados

1.  No servidor front-end do Lync Server 2013, navegue até o mini-aplicativo\\serviços de ferramentas administrativas.

2.  Verifique se os serviços a seguir estão sendo executados no servidor Front End:

**Serviços do Lync Server 2013**

![Lista de serviços do Lync Server iniciado](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Lista de serviços do Lync Server iniciado")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Abra o painel de controle do Lync Server 2013

A partir do servidor front-end na sua implantação do Lync Server 2013, abra o painel de controle do Lync Server 2013 e selecione o pool 2010 do Lync Server. Repita o procedimento para abrir o pool do Lync Server 2013.

**Abre o Painel de controle do Lync Server 2013**

![Caixa de diálogo Selecionar URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Caixa de diálogo Selecionar URL")

<div>


> [!IMPORTANT]  
> No Lync Server 2013, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel de controle do Lync Server.



</div>

Essa topologia agora inclui as funções de servidor do Lync Server 2010 e do Lync Server 2013.

**Página de Topologia do Painel de Controle do Lync Server 2013**

![Painel de controle do Lync Server-página de topologia](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Painel de controle do Lync Server-página de topologia")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Não tente abrir a topologia no construtor de topologias do Lync Server 2010

Se você tentar abrir a topologia usando o construtor de topologias do Lync Server 2010, encontrará o erro abaixo. A topologia só pode ser exibida usando o construtor de topologias do Lync Server 2013. O construtor de topologias do Lync Server 2013 deve ser usado para criar pools para o Lync Server 2013 e o Lync Server 2010.

**Mensagem de erro do Construtor de Topologia do Lync Server 2010**

![Erro de snap do MMC do Lync Server Topology Builder](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Erro de snap do MMC do Lync Server Topology Builder")

</div>

</div>

<span> </span>

</div>

</div>

</div>

