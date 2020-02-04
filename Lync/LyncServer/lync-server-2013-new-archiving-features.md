---
title: 'Lync Server 2013: Novos recursos de Arquivamento'
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
ms.openlocfilehash: 1509a0857b54673ab20783f69b34b59c6d2afde8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Novos recursos de Arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

O arquivamento no Lync Server 2013 pode arquivar os seguintes tipos de conteúdo:

  - Mensagens instantâneas de ponto a ponto

  - Conferências (reuniões) que são mensagens instantâneas com vários participantes

  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)

Além disso, o arquivamento no Lync Server 2013 oferece novos recursos que melhoram a implantação e a eficiência das operações. Esses novos recursos consistem em:

  - **Colocação do arquivamento em servidores front-end.**    O Lync Server 2013 não tem uma função de servidor de arquivamento separada. O arquivamento é um recurso opcional disponível em todos os servidores front-end em uma implantação do Enterprise Edition e em servidores de edição padrão, que pode ser implementado configurado para um pool ou um site.

  - **Integração com o Microsoft Exchange.**    Ao implantar o arquivamento, você pode integrar o armazenamento de dados para arquivamento com o armazenamento existente do Exchange 2013 para todos os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio no bloqueio in-loco, para que você não precise implantar bancos de dados do SQL Server separados para arquivar dados do Lync. Se você não tiver uma implantação do Exchange 2013 ou se preferir não integrá-la, ou se tiver usuários do Lync 2013 que não são hospedados no Exchange 2013 com suas caixas de correio no bloqueio in-loco, você pode implantar bancos de dados de arquivamento separados usando o SQL Server para stor arquivar dados de comunicações do Lync. Você pode usar os bancos de dados de armazenamento do Microsoft Exchange Integration e Lync Server 2013 se quiser usar a integração do Microsoft Exchange para alguns, mas não para todos os usuários da sua implantação. Para obter detalhes sobre o bloqueio in-loco, consulte "bloqueio in-loco [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)" em.

  - **Espelhamento da SQL Store.**    Ao implantar o arquivamento, você pode habilitar o espelhamento de banco de dados do SQL Server para o banco de dados de arquivamento.

  - **Arquivamento de quadros de comunicações e sondagens.**    Agora, o conteúdo arquivado da conferência inclui quadros de comunicações e sondagens que são compartilhados durante a reunião.

Os seguintes tipos de conteúdo não são arquivados:

  - Transferências de arquivo de ponto a ponto

  - Áudio e vídeo de mensagens instantâneas e conferências de ponto a ponto

  - Compartilhamento de aplicativos para mensagens instantâneas e conferências ponto a ponto

<div>

## <a name="see-also"></a>Confira também


[Planejando Arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

