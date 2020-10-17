---
title: 'Lync Server 2013: validar configurações do sistema de nomes de domínio para balanceamento de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc346dba48de1914f9aa5684d114e2f3466396f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508608"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Validar configurações do sistema de nomes de domínio para balanceamento de carga no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-02_

Para suportar o FQDN usado pelo balanceamento de carga DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão atualmente implantados.

Além disso, se você estiver usando o balanceamento de carga DNS para os pools de borda, serão necessárias as seguintes entradas DNS:

  - Para o serviço de borda de acesso do Lync Server, você deve ter uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de acesso do Lync Server (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso do Lync Server em um dos servidores de borda no pool.

  - Para o serviço de borda de Webconferência do Lync Server, você deve ter uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de Webconferência do Lync Server (por exemplo, webconf.contoso.com) para o endereço IP do serviço de borda de Webconferência do Lync Server em um dos servidores de borda do pool.

  - Para o serviço de borda de áudio/vídeo do Lync Server, você deve ter uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo do Lync Server (por exemplo, av.contoso.com) para o endereço IP do serviço de borda de áudio/vídeo do Lync Server em um dos servidores de borda no pool.

  - Se quiser usar o balanceamento de carga DNS na interface interna do pool de borda, você deve adicionar um registro DNS que resolva o FQDN interno do pool de borda para o endereço IP de cada servidor no pool.

Para verificar se o DNS está retornando os valores corretos para o balanceamento de carga DNS, você deve usar a ferramenta nslookup. Para retornar todos os valores de um registro DNS com Nslookup, execute o comando:

`nslookup <FQDN >`

Você deve executar esse comando para cada FQDN usado na configuração de balanceamento de carga DNS para verificar se cada conjunto de registros para balanceamento de carga DNS retornou todas as entradas corretas.

</div>

<span> </span>

</div>

</div>

</div>

