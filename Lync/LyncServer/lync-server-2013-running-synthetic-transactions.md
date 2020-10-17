---
title: 'Lync Server 2013: Executando transações sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 297e1ee6416fb534791a2459e10acaa87f86e205
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511088"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="37543-102">Executando transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37543-102">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37543-103">_**Última modificação do tópico:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="37543-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="37543-104">As transações sintéticas geralmente são conduzidas de duas maneiras.</span><span class="sxs-lookup"><span data-stu-id="37543-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="37543-105">Você pode usar os cmdlets do CsHealthMonitoringConfiguration para configurar os usuários de teste para cada um dos pools de registradores.</span><span class="sxs-lookup"><span data-stu-id="37543-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="37543-106">Esses usuários de teste são um par de usuários que foram pré-configurados para uso com transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="37543-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="37543-107">(Normalmente, são contas de teste e não contas que pertencem a usuários reais.) Com os usuários de teste configurados para um pool, você pode executar uma transação sintética nesse pool sem ter que especificar as identidades de (e fornecer as credenciais) das contas de usuário envolvidas no teste.</span><span class="sxs-lookup"><span data-stu-id="37543-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="37543-108">Ou você pode executar uma transação sintética usando contas de usuário reais.</span><span class="sxs-lookup"><span data-stu-id="37543-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="37543-109">Por exemplo, se dois usuários não podem trocar mensagens instantâneas, você pode executar uma transação sintética usando essas duas contas de usuário (em vez de um par de contas de teste) e, em seguida, tentar diagnosticar e resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="37543-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="37543-110">Se você decidir conduzir uma transação sintética usando contas de usuário reais, deverá fornecer os nomes de logon e as senhas para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="37543-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="37543-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="37543-111">See Also</span></span>


[<span data-ttu-id="37543-112">Configurando os usuários de teste do nó do Inspetor e definições de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37543-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="37543-113">Instruções especiais de configuração para transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37543-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

