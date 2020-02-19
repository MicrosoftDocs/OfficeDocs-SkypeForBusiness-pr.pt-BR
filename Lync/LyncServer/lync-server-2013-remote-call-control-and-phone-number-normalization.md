---
title: 'Lync Server 2013: controle de chamada remota e normalização de número de telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ddf66011a992c9ed306a1fb6652f63133ecb123
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Normalização de controle de chamada remota e de número de telefone no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-22_

Os clientes do Lync baixam regras de normalização de número de telefone como parte do download de arquivo do serviço de catálogo de endereços (ABS). Em cenários de controle de chamada remota, as regras de normalização de número de telefone do Serviço de Catálogo de Endereços são aplicadas a chamadas recebidas e realizadas de controle de chamada remota. Para as chamadas recebidas para um usuário com o controle de chamada remota habilitado, primeiro o número de telefone do chamador é normalizado no formato E.164 pelo gateway SIP/CSTA ou PBX (Central Privada de Comutação Telefônica). Quando o Lync Server 2013 recebe a chamada do gateway, ele realiza a pesquisa de número reverso (RNL) no número de telefone do chamador em relação ao número normalizado na lista de contatos do Microsoft Office Outlook do receptor ou na lista de endereços global (GAL) armazenada no o serviço de catálogo de endereços. Se a pesquisa de número reversa encontrar uma correspondência, o chamador será identificado pelo nome na notificação de chamada recebida.

Para chamadas de controle de chamada remota de saída, o Lync aplica as regras de normalização do número de telefone do serviço de catálogo de endereços ao número discado antes de rotear a chamada para o gateway SIP/CSTA.

Para obter detalhes sobre como criar regras de normalização de número de telefone para controle de chamada remota, consulte [Dial Plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migrando as regras de normalização do número de telefone

Se você estiver migrando os usuários que antes estavam habilitados para controle de chamada remota, consulte os seguintes tópicos na documentação Migração:

  - Para o Lync Server 2010, consulte [Migrate Address Book](migrate-address-book.md) na documentação de migração.

  - Para o Communications Server 2007 R2, consulte [Migrate Address Book](migrate-address-book_1.md) na documentação de migração.

</div>

</div>

<span> </span>

</div>

</div>

</div>

