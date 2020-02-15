---
title: Processo de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6eec7971665aa8e4494ca4509c92c406458cb08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processo de migração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-24_

O procedimento de migração recomendado e com suporte para o Lync Server 2013 é o procedimento de migração lado a lado. Este tópico descreve porque você deve usar a migração lado a lado e também inclui informações sobre coexistência.

<div>

## <a name="side-by-side-migration"></a>Migração lado a lado

Em praticamente cada migração, você deve usar o caminho de migração lado a lado. Em uma migração lado a lado, você implanta um novo servidor com o Lync Server 2013 juntamente com um servidor correspondente executando o Office Communications Server 2007 R2 e transfere operações para o novo servidor. Se for necessário reverter para o Office Communications Server 2007 R2, você terá que alterar as operações de volta para os servidores originais. Lembre-se de que nessa situação, quaisquer novas reuniões agendadas com os clientes atualizados não funcionarão e também seria necessário fazer o downgrade dos clientes.

</div>

<div>

## <a name="coexistence-testing"></a>Teste de coexistência

Depois de implantar o Lync Server 2013 em paralelo com o Office Communications Server 2007 R2, a topologia representa um estado de teste de coexistência do Lync Server 2013 e do Office Communications Server 2007 R2. Neste estado, é importante testar e verificar se os serviços foram inicializados, se cada site pode ser administrador e se os clientes pode se comunicar com usuários atuais e herdados. Antes da migração de todos os usuários, é importante entender o estado de cada implantação e verificar se cada implantação está pronta e funcionando corretamente. Normalmente, a fase de teste de coexistência existe durante o teste piloto do Lync Server 2013. Os usuários herdados são movidos para o Lync Server 2013 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente. Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Lync Server 2013, e os pools herdados e os aplicativos do Office Communications Server 2007 R2 são removidos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

