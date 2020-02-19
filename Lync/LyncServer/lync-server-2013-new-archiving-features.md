---
title: 'Lync Server 2013: novos recursos de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e09284d78ead2e8cd4249c2dc54159284ddad43
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42127644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Novos recursos de arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

O arquivamento no Lync Server 2013 pode arquivar os seguintes tipos de conteúdo:

  - Mensagens instantâneas ponto a ponto

  - As conferências (reuniões) que são mensagens instantâneas de várias partes

  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, cargas, compartilhamento e alterações de visibilidade)

Além disso, o arquivamento no Lync Server 2013 oferece novos recursos que melhoram a implantação e a eficiência das operações. Esses novos recursos consistem em:

  - **Colocação do arquivamento em servidores front-end.**    O Lync Server 2013 não tem uma função de servidor de arquivamento separada. O Arquivamento é um recurso opcional disponível em todos os Servidores front-end em uma implantação Enterprise Edition e, nos servidores Standard Edition, que podem ser implementados e configurados para um pool ou site.

  - **Integração com o Microsoft Exchange.**    Ao implantar o arquivamento, você pode integrar o armazenamento de dados para arquivamento com seu armazenamento existente do Exchange 2013 para todos os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas em bloqueio in-loco, portanto, não é necessário implantar bancos de dados do SQL Server separados para arquivar dados do Lync. Se você não tiver uma implantação do Exchange 2013, ou se preferir não integrá-la, ou se você tiver usuários do Lync 2013 que não estejam hospedados no Exchange 2013 com suas caixas de correio colocadas em bloqueio in-loco, é possível implantar bancos de dados de arquivamento separados usando o SQL Server para o stor dados arquivados de comunicações do Lync. Você pode usar os bancos de dados de integração do Microsoft Exchange e do Lync Server 2013 se quiser usar a integração do Microsoft Exchange para alguns, mas não todos os usuários em sua implantação. Para obter detalhes sobre o bloqueio in-loco, consulte "bloqueio in-loco [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500)" em.

  - **Espelhamento do repositório SQL.**    Ao implantar o arquivamento, você pode habilitar o espelhamento de banco de dados do SQL Server para o banco de dados de arquivamento.

  - **Arquivamento de quadros de comunicações e pesquisas.**    O conteúdo de conferência arquivada agora inclui quadros de comunicações e pesquisas que são compartilhadas durante a reunião.

Os seguintes tipos de conteúdo não são arquivados:

  - Transferências de arquivo ponto a ponto

  - Áudio/vídeo para mensagens instantâneas ponto a ponto e conferências

  - Compartilhamento de aplicativos para mensagens instantâneas ponto a ponto e conferências

<div>

## <a name="see-also"></a>Confira também


[Planejamento para arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

