---
title: 'Lync Server 2013: alta disponibilidade de compartilhamento de arquivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67fc8cfffc0b5dbecaf6da212b3a8e5414b18ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Alta disponibilidade de compartilhamento de arquivos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-03-30_

Para garantir alta disponibilidade para o compartilhamento de arquivos do Lync Server em um único Data Center, você pode usar o sistema de arquivos distribuídos (DFS). O DFS suporta failover de um servidor de arquivos para outro dentro do mesmo data center. Para uma implantação de larga escala, recomendamos usar servidores de arquivos dedicados, emparelhados com o uso do DFS.

Dependendo do tamanho da sua rede e da quantidade de resiliência desejada, você pode usar um par de servidores para hospedar todos os compartilhamentos de arquivos em um site ou usar um par por pool de front-end.

O DFSS é o melhor mecanismo de replicação de arquivos, sem objetivo de tempo recuperado (RTO) publicado ou compromisso de objetivo de ponto de recuperação (RPO). O failover entre os servidores DFS deve ser concluído rapidamente, mas o atraso na replicação de dados pode impedir que os usuários possam continuar trabalhando em andamento quando o failover ocorrer.

Se você usar o DFS e o repositório de dados no compartilhamento for essencial, será preciso fazer backup dos compartilhamentos de arquivos com frequência, como cada 4 a 8 horas. Quando um compartilhamento de arquivos cai e a replicação não está atualizada, é possível usar o backup para recuperar o conteúdo no servidor com falha para o outro servidor emparelhado com o que está indisponível.

</div>

<span> </span>

</div>

</div>

</div>

