---
title: 'Lync Server 2013: validar as configurações do sistema de nome de domínio para o balanceamento de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Validar as configurações de sistema de nome de domínio para o balanceamento de carga no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-02_

Para dar suporte ao FQDN usado pelo balanceamento de carga de DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores do pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão implantados no momento.

Além disso, se você estiver usando o balanceamento de carga de DNS para os pools de borda, serão necessárias as seguintes entradas DNS:

  - Para o serviço de borda de acesso do Lync Server, você deve ter uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de acesso do Lync Server (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso do Lync Server em um dos servidores de borda do pool.

  - Para o serviço de borda de conferência do Lync Server Web, você deve ter uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de Webconferência do Lync Server (por exemplo, webconf.contoso.com) para o endereço IP do serviço de borda de Webconferência do Lync Server em um dos servidores de borda do pool.

  - Para o serviço de borda de áudio/vídeo do Lync Server, você deve ter uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo do Lync Server (por exemplo, av.contoso.com) para o endereço IP do serviço de borda de áudio/vídeo do Lync Server em um dos servidores de borda do pool.

  - Se você quiser usar o balanceamento de carga de DNS na interface interna do pool de borda, será necessário adicionar um registro DNS, que resolve o FQDN interno do pool de bordas para o endereço IP de cada servidor do pool.

Para verificar se o DNS está retornando os valores corretos para o balanceamento de carga de DNS, você deve usar a ferramenta nslookup. Para retornar todos os valores de um registro DNS com o Nslookup, você deve executar o comando:

`nslookup <FQDN >`

Você deve executar esse comando para cada FQDN usado na configuração de balanceamento de carga de DNS para verificar se cada conjunto de registros para balanceamento de carga de DNS retornou todas as entradas corretas.

</div>

<span> </span>

</div>

</div>

</div>

