---
title: 'Lync Server 2013: Executando transações sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489b8a02d829f4f12038e3f07559166c1c015b80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Executar transações sintéticas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-18_

As transações sintéticas geralmente são conduzidas de duas maneiras. Você pode usar os cmdlets CsHealthMonitoringConfiguration para configurar usuários de teste para cada um dos seus pools de registradores. Esses usuários de teste são um par de usuários que foram pré-configurados para uso com transações sintéticas. (Geralmente são contas de teste e não contas que pertencem a usuários reais.) Com os usuários de teste configurados para um pool, você pode executar uma transação sintéticada nesse pool sem ter que especificar as identidades de (e fornecer as credenciais) das contas de usuário envolvidas no teste.

Ou você pode executar uma transação sintética usando contas de usuário reais. Por exemplo, se dois usuários não conseguem trocar mensagens de chat, você pode executar uma transação sintética usando essas duas contas de usuário (em vez de um par de contas de teste) e, em seguida, tentar diagnosticar e solucionar o problema. Se você decidir conduzir uma transação sintética usando contas de usuário reais, deverá fornecer os nomes de logon e senhas para cada usuário.

<div>

## <a name="see-also"></a>Confira também


[Configurando os usuários de teste de nó do Inspetor e configurações de configuração no Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Instruções de configuração especiais para transações sintéticas no Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

