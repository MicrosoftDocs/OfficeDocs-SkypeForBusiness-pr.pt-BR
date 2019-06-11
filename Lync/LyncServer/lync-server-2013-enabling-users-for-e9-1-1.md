---
title: 'Lync Server 2013: habilitando usuários para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Permitindo que os usuários do E9-1-1 no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-06_

Durante o registro do cliente, o Lync Server usa uma política de localização para configurar as propriedades E9-1-1 para usuários habilitados para Enterprise Voice. Esta política contém as configurações que definem como o E9-1-1 é implementado. Por exemplo, a política de localização contém informações como a cadeia de caracteres de discagem de emergência e se um usuário precisa ou não inserir um local manualmente se o serviço de informações de localização não fornecer uma conta automaticamente. Para obter uma definição completa de uma política de localização, consulte [definindo a política de localização do Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

O Lync Server pode atribuir uma política de localização a clientes com base na sub-rede ou aos usuários com base em uma política global, por site ou por usuário. Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.

  - **Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**  
    Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global. No entanto, ao atribuir uma política de localização a um site de rede do Lync Server e, em seguida, adicionar sub-redes ao site, você pode limitar o suporte a E9-1 a locais selecionados dentro da empresa e especificar o comportamento de roteamento E9-1-1 para cada site.

<!-- end list -->

  - **Você planeja habilitar usuários individuais por meio de uma política de usuário?**  
    Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.

<!-- end list -->

  - **Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**  
    Se os usuários forem atribuídos a uma política de local global, de site ou por usuário, eles poderão ser solicitados a inserir um local manualmente no cliente se o cliente não estiver localizado dentro de uma sub-rede definida ou se nenhum local tiver sido encontrado pelo serviço informações de localização. Para obter detalhes, consulte [definindo a experiência do usuário para adquirir manualmente um local no Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

