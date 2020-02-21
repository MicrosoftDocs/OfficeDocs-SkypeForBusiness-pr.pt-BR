---
title: 'Lync Server 2013: verificar comunicações com um cliente do Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03aae75cfdb3e179347d14c6f42a90ffe060fad7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Verificar comunicações com um cliente do Lync Online no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-08_

Para permitir que os usuários do Lync em sua organização se comuniquem com os usuários de um cliente do Microsoft Lync Online 2010, você deve concluir as seguintes etapas:

  - Atender a todos os pré-requisitos. Isso incluir a implantação de seus servidores internos e de borda, habilitação do suporte á federação para sua organização e configuração das contas de usuário. Para obter detalhes, consulte [pré-requisitos para federação com um cliente do Lync Online no Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Configurar o suporte ao acesso de domínio em sua implantação interna. Isso inclui a criação de uma entrada de provedor de host e a configuração da implantação para permitir o acesso do domínio do cliente do Lync Online. Para obter detalhes, consulte [Configurar o suporte de Federação para um domínio do Lync Online no Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Configurar suas contas de usuário para suportar a federação. Para obter detalhes, consulte [Configurar o acesso do usuário para federação com um cliente do Lync Online no Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Depois que você concluir todas essas etapas e o administrador do cliente do Lync Online 2010 concluir todas as configurações de seus serviços online para dar suporte à Federação com sua organização, verifique as comunicações com o teste de comunicações entre um usuário em sua organização e um usuário do cliente do Lync Online. Se a comunicação não tiver êxito, use a ferramenta de registro em log do servidor de borda para capturar arquivos de log e rastreamento a fim de solucionar o problema. Para obter detalhes sobre como usar a ferramenta de registro em log, confira [abrir as ferramentas administrativas do Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md) na documentação operações. Para obter detalhes sobre a ferramenta de registro em log, consulte a documentação da ferramenta de registro em log [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)do Lync Server 2010 na biblioteca do TechNet em.

</div>

<span> </span>

</div>

</div>

</div>

