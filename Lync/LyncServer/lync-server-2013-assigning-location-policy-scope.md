---
title: 'Lync Server 2013: atribuindo escopo de política de local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69218c3f5399b62fc67fe0d538a98f1bdadd3cf4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>Atribuindo escopo de política de local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-06_

Como em outras políticas do Lync Server, as políticas de local podem ser atribuídas em vários níveis de escopo: global, site e usuário. No entanto, o escopo das políticas de local no nível do usuário se comporta um pouco diferente de outras políticas do Lync Server. Não apenas as políticas de local por usuário podem ser aplicadas a objetos de ponto de extremidade (como usuários e objetos de contato de telefone de área comum), elas também podem ser aplicadas aos sites de rede do Lync Server. Os sites de rede são agrupamentos de sub-redes de clientes associados a uma localidade geográfica (mas podem não ser necessariamente todas as sub-redes em todo o site central ou site de filial). Quaisquer clientes conectados às sub-redes em um site de rede automaticamente selecionam a política de local designada para o site de rede. Nos casos em que uma política de local de nível de usuário é atribuída a um usuário e a um local de rede, a política de local baseada no site de rede substitui qualquer configuração de política por usuário.

Cada site de rede possui uma política de local atribuída a ele e cada política terá diferentes valores para Usos do PSTN, URIs de Notificação e URIs da Conferência atribuídos a ela.

<div>


> [!NOTE]  
> O motivo para esse comportamento de escopo de política especial é que, quando um usuário hospedado em um pool em um site do Office visita outro site e precisa fazer uma chamada de emergência, as configurações de roteamento de chamadas E9-1-1 apropriadas para esse site de rede serão aplicadas, não importa qual pool ou site o u ser atribuído a.



</div>

</div>

<span> </span>

</div>

</div>

</div>

