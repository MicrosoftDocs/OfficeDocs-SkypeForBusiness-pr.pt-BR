---
title: 'Lync Server 2013: configurar a tabela de órbita de estacionamento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0f4de5568dc8d265acd412999aafc814c68dbc9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520358"
---
# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Configurar a tabela de órbita de estacionamento de chamadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-10_

O estacionamento de chamada usa órbitas para estacionamento de chamadas. Antes que os usuários possam estacionar e recuperar chamadas, você deve configurar a tabela de órbita de estacionamento de chamada. Você precisa especificar os intervalos de números de ramal (órbitas) que sua organização irá reservar para estacionamento de chamadas e definir o roteamento desses intervalos especificando o pool de estacionamento de chamadas que trata cada intervalo. Quando você define intervalos de órbita, a meta é ter órbitas suficientes para que qualquer uma das órbitas não seja reutilizada muito rapidamente, mas não muitas órbitas que você limite o número de extensões disponíveis para usuários ou outros serviços. Você pode criar vários intervalos de órbita de estacionamento de chamadas para cada pool do Lync Server onde o aplicativo de estacionamento de chamada é implantado. Cada intervalo de órbita de estacionamento de chamadas deve ter um nome globalmente exclusivo e um conjunto exclusivo de extensões.

<div>


> [!IMPORTANT]  
> Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente.



</div>

Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita.

<div>


> [!NOTE]  
> Não há suporte para a atribuição de números DID (discagem direta interna) como números de órbita na tabela de órbita de estacionamento de chamada.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

[Criar ou modificar um intervalo de órbita de estacionamento de chamada no Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

