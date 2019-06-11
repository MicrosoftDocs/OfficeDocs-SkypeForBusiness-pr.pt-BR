---
title: 'Lync Server 2013: Recursos obrigatórios para Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Recursos obrigatórios para Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-02-05_

A alta disponibilidade e a recuperação de desastres para o servidor de chat persistente exigem recursos adicionais além do que normalmente é necessário para operação completa. Antes de configurar o servidor de chat persistente para alta disponibilidade e recuperação de desastres, certifique-se de ter os seguintes recursos, além do que é necessário para a operação de servidor de chat persistente padrão. Para obter informações de configuração adicionais, consulte Configurando o [servidor de chat persistente no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Uma instância de banco de dados dedicada localizada no mesmo Data Center físico no qual o front-end de página inicial do serviço de servidor de chat persistente está localizado. Esse banco de dados funcionará como o espelho do SQL Server para o banco de dados de chat persistente principal. Opcionalmente, designe um SQL Server adicional para atuar como a testemunha de espelhamento se desejar um failover automatizado para o banco de dados espelho.

  - Uma instância de banco de dados dedicada localizada no outro data center físico. Este banco de dados funcionará como o banco de dados secundário de envio de logs do SQL Server para o banco de dados no centro de dados principal.

  - Uma instância de banco de dados dedicada para servir como o espelho do SQL Server para o banco de dados secundário. Opcionalmente, designe um SQL Server adicional para o servidor como testemunha de espelhamento. Ambos devem estar localizados no mesmo data center físico que o banco de dados secundário.

  - Se a conformidade com o servidor de chat persistente estiver habilitada, serão necessárias outras três instâncias de banco de dados dedicados. Sua distribuição é a mesma que a que foi descrita anteriormente para o banco de dados de chat persistente. Embora seja possível que o banco de dados de conformidade compartilhe a mesma instância do SQL Server que o banco de dados de chat persistente, recomendamos instâncias autônomas para alta disponibilidade e recuperação de desastres.

  - Um compartilhamento de arquivos deve ser criado e designado para os logs de transação de envio de logs do SQL Server. Todos os SQL Servers nos dois data centers que executam bancos de dados de chat persistente devem ter acesso de leitura/gravação a este compartilhamento de arquivos. Esse compartilhamento não está definido como parte de uma função FileStore.

  - Um compartilhamento de arquivo no servidor de banco de dados secundário para atuar como a pasta de destino dos logs de transação do SQL Server que são copiados do compartilhamento de arquivos do servidor primário.

<div>


> [!NOTE]  
> Os servidores de chat ativos persistentes em um pool de servidores de chat persistente devem residir no mesmo fuso horário do pool de Lync do próximo salto definido na topologia.



</div>

Os números a seguir fornecem exemplos sobre como o pool de servidores de chat inteiro persistente pode ser configurado nas duas topologias diferentes de pool estendidos:

  - Pool de servidores de chat persistentes ampliados quando os data centers estão localizados geográficos com alta largura de banda/baixa latência.

  - Pool de servidores de chat persistentes ampliados quando os centros de dados estiverem localizados na região de baixa largura de banda/alta latência.

A figura a seguir mostra uma topologia de pool de servidores de chat persistente com Stretch em que os data centers são localizados geográficos com alta largura de banda/baixa latência.

**Pool de servidores de chat persistentes ampliados quando os data centers estão localizados geográficos com alta largura de banda/baixa latência.**

![Exame de configuração HBW do pool do servidor de chat persistente] (images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Exame de configuração HBW do pool do servidor de chat persistente")

A figura a seguir mostra uma topologia de pool de servidores de chat persistente com Stretch em que os data centers são localizados geográficos com largura de banda baixa/alta latência.

**Pool de servidores de chat persistentes ampliados quando os centros de dados estiverem localizados na região de baixa largura de banda/alta latência.**

![Exame de configuração LBW do pool do servidor de chat persistente] (images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Exame de configuração LBW do pool do servidor de chat persistente")

</div>

<span> </span>

</div>

</div>

</div>

