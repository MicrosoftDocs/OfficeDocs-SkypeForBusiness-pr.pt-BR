---
title: Evitar sessões de serviços
description: Impedir sessões de serviços.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563687"
---
# <a name="prevent-sessions-for-services"></a>Evitar sessões de serviços

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Você pode usar o painel de controle do Microsoft Lync Server 2010 para impedir novas sessões para todos os serviços do Lync Server 2010 em execução em um computador específico ou para impedir novas sessões para um serviço do Lync Server 2010 específico.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Para impedir novas sessões para todos os serviços do Lync Server em um computador

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra o Painel de Controle do Lync Server.

3.  Na barra de navegação à esquerda, clique em **Topologia** e, em seguida, clique em **Status**.

4.  Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando os serviços para os quais você deseja impedir novas sessões e clique nele.

5.  Clique em **Ação**.

6.  Clique em **Impedir novas sessões para todos os serviços**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para Impedir novas sessões para um serviço específico

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra o Painel de Controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Topologia** e em **Status**.

4.  Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.

5.  Clique em **Propriedades**.

6.  Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.

7.  Clique em **Ações**.

8.  Clique em **Impedir novas sessões para o serviço**.

9.  Clique em **Fechar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

