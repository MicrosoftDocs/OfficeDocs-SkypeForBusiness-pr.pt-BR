---
title: 'Lync Server 2013: Migrar usuários para o repositório unificado de contatos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a57ea93af90176009fff43ed4dcca9f1880a658
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="f2f48-102">Migrar usuários para o repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2f48-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2f48-103">_**Tópico da última modificação:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="f2f48-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="f2f48-104">Os contatos de um usuário são migrados automaticamente para o servidor Exchange 2013 quando o usuário:</span><span class="sxs-lookup"><span data-stu-id="f2f48-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="f2f48-105">For atribuído com uma política de serviços do usuário com UcsAllowed definido para True.</span><span class="sxs-lookup"><span data-stu-id="f2f48-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="f2f48-106">Foi provisionado com uma caixa de correio do Exchange 2013 e entrou na caixa de correio pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="f2f48-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="f2f48-107">Conecta-se usando um cliente avançado do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f2f48-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="f2f48-108">Se o usuário fizer logon com um cliente do Lync 2010 ou anterior, ou se o usuário não estiver conectado a um servidor do Exchange 2013, a política de serviços do usuário será ignorada e os contatos do usuário permanecerão no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2f48-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="f2f48-109">É possível determinar se os contatos do usuário foram migrados usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="f2f48-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="f2f48-110">Verifique a chave do registro no computador cliente:</span><span class="sxs-lookup"><span data-stu-id="f2f48-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="f2f48-111">HKey\_Current\_user\\software\\Microsoft\\Office\\15,0\\Lync\\\<SIP URL\>\\UCS</span><span class="sxs-lookup"><span data-stu-id="f2f48-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="f2f48-112">Se os contatos do usuário estiverem armazenados no Exchange 2013, essa chave contém um valor de InUCSMode com um valor de 2165.</span><span class="sxs-lookup"><span data-stu-id="f2f48-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="f2f48-113">Execute o cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="f2f48-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="f2f48-114">Na linha de comando do Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="f2f48-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="f2f48-115">Se o **Test-CsUnifiedContactStore** tiver êxito, os contatos do usuário foram migrados para o repositório de contatos unificados.</span><span class="sxs-lookup"><span data-stu-id="f2f48-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

