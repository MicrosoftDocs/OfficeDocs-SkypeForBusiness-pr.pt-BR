---
title: 'Lync Server 2013: Normalização de controle de chamada remota e de número de telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86de318cb1e72fce8fb6f42ff7698db5974034fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Normalização de controle de chamada remota e de número de telefone no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-22_

Os clientes do Lync baixam as regras de normalização do número de telefone como parte do download do arquivo ABS (serviço de catálogo de endereços). Em cenários de controle de chamada remota, as regras de normalização do número de telefone do serviço de catálogo de endereços são aplicadas às chamadas de controle de chamada remota de entrada e saída. Para chamadas recebidas para um usuário habilitado para controle de chamada remota, o número de telefone do chamador é inicialmente normalizado para o formato E. 164 pelo gateway de SIP/CSTA ou PBX (Agência telefônica privada). Quando o Lync Server 2013 recebe a chamada do gateway, ele executa a pesquisa de número reverso (RNL) no número de telefone do chamador em relação ao número normalizado na lista de contatos do Microsoft Office Outlook ou a GAL (lista de endereços global) do Microsoft Office Outlook que está armazenada em o serviço de catálogo de endereços. Se a pesquisa de número reverso localizar uma correspondência com êxito, o chamador será identificado por nome na notificação de chamada de entrada.

Para chamadas de controle de chamadas remotas de saída, o Lync aplica as regras de normalização de número de telefone do serviço de catálogo de endereços para o número discado antes de rotear a chamada para o gateway SIP/CSTA.

Para obter detalhes sobre como criar regras de normalização de número de telefone para o controle de chamada remota, consulte [regras de discagem e planos de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migrando regras de normalização de número de telefone

Se você estiver migrando usuários anteriormente habilitados para controle de chamada remota, consulte os tópicos a seguir na documentação de migração:

  - Para o Lync Server 2010, consulte [migrar catálogo de endereços](migrate-address-book.md) na documentação de migração.

  - Para o Communications Server 2007 R2, confira migrar o [Catálogo de endereços](migrate-address-book_1.md) na documentação de migração.

</div>

</div>

<span> </span>

</div>

</div>

</div>

