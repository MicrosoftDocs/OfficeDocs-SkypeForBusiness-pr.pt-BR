---
title: Requisitos técnicos do Lync Server 2013 para IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3484dd6ff1404d5d2a4adf77c4ab27a5a29e66b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533808"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Requisitos técnicos para IPv6 no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-30_

Se você planeja configurar o Lync Server 2013 para IPv6, tenha em mente os seguintes requisitos:

  - Para usar endereços IPv6 com o Lync Server, você precisa criar registros de DNS (sistema de nomes de domínio) para registros que devem ser descobertos e resolvidos para um endereço IPv6. O DNS IPv6 usa um registros de host AAAA (quad-A). Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6. Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.
    
    É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6. Se o cliente ou servidor não usar IPv6, o registro não será referenciado. As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.

  - Cada endereço IPv6 possui um escopo. Os três escopos que você pode usar para o endereçamento IPv6 são endereços globais IPv6 (semelhantes aos endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhantes aos intervalos de endereços IPv4 privados) e endereços de link local IPv6 (semelhante aos endereços IP privados automáticos no Windows Server para IPv4). Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo.

<div>


> [!IMPORTANT]  
> O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para ajudar a garantir que os endereços que você atribui no nível do servidor do Windows e no nível do Lync Server 2013 funcione conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.



</div>

<div>

## <a name="see-also"></a>Confira também


[Arquitetura de endereçamento de IP versão 6](https://tools.ietf.org/html/rfc4291)  
[Formato de endereço de unicast global IPv6](https://tools.ietf.org/html/rfc3587)  
[Endereços exclusivos de unicast IPv6 locais](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

