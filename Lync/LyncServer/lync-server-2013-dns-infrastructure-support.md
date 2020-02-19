---
title: 'Lync Server 2013: suporte à infraestrutura de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5ede9d6af8c9f912a207c602c225c19c3dd1f38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Suporte à infraestrutura de DNS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-08_

O Lync Server 2013 requer o DNS (sistema de nomes de domínio) e o utiliza das seguintes maneiras:

  - Para descobrir pools ou servidores internos para a comunicação entre servidores.

  - Para permitir que os clientes descubram o pool de front-ends ou o servidor Standard Edition usado em diversas transações SIP.

  - Para associar URLs simples de conferências com os servidores que as hospedam.

  - Para permitir que os servidores e clientes externos se conectem aos servidores de borda ou ao proxy reverso HTTP para fazer uso de IM (mensagens instantâneas) ou conferências.

  - Para permitir que os dispositivos de UC (comunicações unificadas) que não estejam conectados descubram o pool de front-ends ou o servidor Standard Edition que está executando o serviço Web de atualização de dispositivo obtenham atualizações e enviem logs.

  - Para permitir que os clientes móveis descubram automaticamente os recursos dos serviços Web, sem exigir que os usuários insiram as URLs manualmente nas configurações do dispositivo.

  - Para o balanceamento de carga de DNS.

<div>


> [!NOTE]  
> O Lync Server 2013 não suporta nomes de domínio internacionalizados (IDNs).



</div>

<div>


> [!IMPORTANT]  
> O nome que você especifica deve ser idêntico ao nome do computador configurado no servidor. Por padrão, o nome de um computador que não esteja em um domínio é curto e não um FQDN (nome de domínio totalmente qualificado). O Construtor de Topologia utiliza FQDNs, não nomes curtos. Portanto, configure um sufixo DNS no nome do computador a ser implantado como um servidor de borda e que não esteja em um domínio. <STRONG>Use somente caracteres padrão</STRONG> (inclusive A–Z, a–z, 0–9 e hifens) quando atribuir FQDNs de seus Lync Servers, servidores de borda e pools. Não use caracteres Unicode ou sublinhados. Os caracteres incompatíveis em um FQDN frequentemente não são suportados no DNS externo e CAs públicos (isto é, quando o FQDN deve ser atribuído ao SN no certificado).



</div>

</div>

<span> </span>

</div>

</div>

</div>

