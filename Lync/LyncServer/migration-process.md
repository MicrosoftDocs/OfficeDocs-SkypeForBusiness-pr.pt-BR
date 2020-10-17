---
title: Processo de migração
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf45be5e5d30a1c8a69a634837bc63c2768b193
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515118"
---
# <a name="migration-process"></a>Processo de migração

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-17_

O procedimento de migração recomendado e com suporte para o Lync Server 2013 é migração lado a lado. Este tópico descreve porquê você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.

<div>

## <a name="side-by-side-migration"></a>Migração lado a lado

Em praticamente cada migração, você deve usar o caminho de migração lado a lado. Em uma migração lado a lado, você implanta um novo servidor com o Lync Server 2013 juntamente com um servidor correspondente que está executando o Lync Server 2010 e transfere operações para o novo servidor. Se for necessário reverter para o Lync Server 2010, você terá que alterar as operações de volta para os servidores originais. Lembre-se de que nessa situação, quaisquer novas reuniões agendadas com os clientes atualizados não funcionarão e também seria necessário fazer o downgrade dos clientes.

</div>

<div>

## <a name="coexistence-testing"></a>Teste de coexistência

Após a implantação do Lync Server 2013 em paralelo com o Lync Server 2010, a implantação representa um estado de teste de coexistência do Lync Server 2013 e do Lync Server 2010. Durante este estado, é importante testar e garantir que os serviços estejam iniciados, que cada site possa ser administrado e que os clientes possam se comunicar com usuários atuais e herdados. Antes da migração de todos os usuários, é muito importante entender o estado de cada implantação e garantir que cada uma delas esteja funcional e funcionando adequadamente. Normalmente, a fase de teste de coexistência existe durante o teste piloto do Lync Server 2013. Os usuários herdados são movidos para o Lync Server 2013 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente. Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Lync Server 2013, e os pools e aplicativos herdados do Lync Server 2010 são removidos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

