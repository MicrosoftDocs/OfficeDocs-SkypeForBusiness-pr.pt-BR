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
ms.openlocfilehash: 2771a7a8b29cf410f9da5155e8f379bd7efe0e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processo de migração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

O procedimento de migração recomendado e com suporte para o Lync Server 2013 é o procedimento de migração lado a lado. Este tópico descreve porque você deve usar a migração lado a lado e também inclui informações sobre coexistência.

<div>

## <a name="side-by-side-migration"></a>Migração lado a lado

Em quase todas as migrações, você deve usar o caminho de migração lado a lado. Em uma migração lado a lado, implante um novo servidor com o Lync Server 2013 juntamente com um servidor correspondente executando o Office Communications Server 2007 R2 e, em seguida, transfira operações para o novo servidor. Se for necessário reverter para o Office Communications Server 2007 R2, você só poderá mudar as operações para os servidores originais. Lembre-se de que, nesta situação, todas as novas reuniões agendadas com clientes atualizados não funcionarão, e os clientes também precisariam ser rebaixados.

</div>

<div>

## <a name="coexistence-testing"></a>Teste de coexistência

Depois de implantar o Lync Server 2013 em paralelo com o Office Communications Server 2007 R2, a topologia representa um estado de teste de coexistência do Lync Server 2013 e do Office Communications Server 2007 R2. Nesse estado, é importante testar e garantir que os serviços sejam iniciados, que cada site pode ser administrado e os clientes podem se comunicar com os usuários atuais e herdados. Antes da migração de todos os usuários, é muito importante que você compreenda o estado de cada implantação e certifique-se de que cada implantação está funcional e funcionando corretamente. Geralmente, a fase de teste de coexistência existe durante o teste piloto do Lync Server 2013. Os usuários herdados são movidos para o Lync Server 2013 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente. Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Lync Server 2013, e os pools herdados e os aplicativos do Office Communications Server 2007 R2 são desativados.

</div>

</div>

<span> </span>

</div>

</div>

</div>

