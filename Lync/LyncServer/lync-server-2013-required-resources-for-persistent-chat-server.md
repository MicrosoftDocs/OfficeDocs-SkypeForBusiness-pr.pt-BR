---
title: 'Lync Server 2013: recursos necessários para o servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156a3ffef41782760124f0eb791cf2fdb71a1235
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511938"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Recursos necessários para o servidor de chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-02-05_

Alta disponibilidade e recuperação de desastre para servidor de chat persistente requer recursos adicionais além do que normalmente é necessário para operação completa. Antes de configurar o servidor de chat persistente para alta disponibilidade e recuperação de desastre, verifique se você tem os seguintes recursos além do que é necessário para a operação padrão de servidor de chat persistente. Para obter informações adicionais sobre a configuração, consulte [Configuring persistent chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Uma instância de banco de dados dedicada localizada no mesmo Data Center físico no qual o front-end do serviço servidor de chat persistente está localizado. Este banco de dados funcionará como o espelho do SQL Server para o banco de dados de chat persistente principal. Opcionalmente, designe um SQL Server adicional para servir como testemunha de espelhamento, se você quiser um failover automatizado para o banco de dados espelho.

  - Uma instância de banco de dados dedicada localizada no outro data Center físico. Este banco de dados servirá como banco de dados secundário de envio de logs do SQL Server para o banco de dados no data center primário.

  - Uma instância de banco de dados dedicada para servir como o espelho do SQL Server para o banco de dados secundário. Opcionalmente, designe um servidor SQL adicional para o servidor como testemunha de espelhamento. Ambos devem estar localizado no mesmo data Center físico que o banco de dados secundário.

  - Se a conformidade do servidor de chat persistente estiver habilitada, serão necessárias mais três instâncias de banco de dados dedicadas. Suas distribuições são as mesmas descritas anteriormente para o banco de dados de chat persistente. Embora seja possível que o banco de dados de conformidade compartilhe a mesma instância do SQL Server que o banco de dados de chat persistente, recomendamos instâncias autônomas para alta disponibilidade e recuperação de desastre.

  - Um compartilhamento de arquivos deve ser criado e designado para os logs de transação de envio de logs do SQL Server. Todos os SQL Servers em ambos os data centers que executam bancos de dados de chat persistente devem ter acesso de leitura/gravação a esse compartilhamento de arquivos. Este compartilhamento não está definido como parte de uma função FileStore.

  - Um compartilhamento de arquivos no servidor de banco de dados secundário para servir como a pasta de destino dos logs de transação do SQL Server que são copiados do compartilhamento de arquivos do servidor primário.

<div>


> [!NOTE]  
> Os servidores de chat persistente ativos em um pool de servidores de chat persistente devem residir no mesmo fuso horário que o pool de Lync do próximo salto definido na topologia.



</div>

Os seguintes números fornecem exemplos sobre como o pool de servidor de chat persistente inteiro pode ser configurado em duas topologias de pool estendidas diferentes:

  - Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com alta largura de banda/baixa latência.

  - Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com baixa largura de banda/alta latência.

A figura a seguir mostra uma topologia de pool de servidor de chat persistente estendido onde os data centers estão localizados geograficamente com alta largura de banda/baixa latência.

**Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com alta largura de banda/baixa latência.**

![Exame de configuração do pool do servidor de chat persistente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Exame de configuração do pool do servidor de chat persistente HBW")

A figura a seguir mostra uma topologia de pool de servidor de chat persistente estendido onde os data centers estão localizados geograficamente com baixa largura de banda/alta latência.

**Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com baixa largura de banda/alta latência.**

![Exame de configuração do pool do servidor de chat persistente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Exame de configuração do pool do servidor de chat persistente LBW")

</div>

<span> </span>

</div>

</div>

</div>

