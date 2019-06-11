---
title: 'Lync Server 2013: atribuindo escopo da política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c44bef383690856d873d64ab6218b0f14219e73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>Atribuindo o escopo da política de localização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-06_

Assim como em outras políticas do Lync Server, as políticas de localização podem ser atribuídas em vários níveis de escopo: global, site e usuário. No entanto, o escopo das políticas de localização em nível de usuário tem um pouco diferente do que as outras políticas do Lync Server. Não apenas as políticas de localização por usuário podem ser aplicadas a objetos de ponto de extremidade (como usuários e objetos de contato de telefone comum), também podem ser aplicadas a sites de rede do Lync Server. Os sites de rede são agrupamentos de subredes de cliente associadas com um local geográfico (mas não necessariamente deve ser todas as subredes em um site central ou site de filial). Qualquer cliente conectado às subredes de um site de rede obtém automaticamente a política de local atribuída a este site de rede. Em casos onde uma política de local a nível de usuário é atribuída ao usuário e a um site de rede, a política de local baseada em site de rede substitui qualquer configuração de política por usuário.

Cada local de rede possui uma política de rede atribuída e cada política possuirá diferentes valores de Usos de PSTN, URIs de notificação e URIs de conferência atribuídos.

<div>


> [!NOTE]  
> O motivo para esta política especial se comportar desta forma é porque quando um usuário hospedado em um pool em um local de escritório visita outro local e precisa fazer uma chamada de emergência, as configurações de roteamento de chamada E9-1-1 adequadas para este local de rede serão aplicadas não importando a qual pool ou local o usuário está atribuído.



</div>

</div>

<span> </span>

</div>

</div>

</div>

