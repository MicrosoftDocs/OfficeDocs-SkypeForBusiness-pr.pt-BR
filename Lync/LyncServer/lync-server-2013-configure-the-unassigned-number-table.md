---
title: 'Lync Server 2013: Configurar a tabela de número não atribuído'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="2006c-102">Configurar a tabela de número não atribuído no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2006c-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2006c-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="2006c-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="2006c-104">No Lync Server 2013, você pode especificar o que acontece com as chamadas recebidas para números de telefone válidos para a sua organização, mas que não estão atribuídas a um usuário ou telefone.</span><span class="sxs-lookup"><span data-stu-id="2006c-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="2006c-105">Os chamadores podem ouvir uma mensagem ou podem ser roteados para outro destino, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="2006c-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="2006c-p102">O modo como você configura a tabela de números não atribuída depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuída pode incluir números atribuídos e não atribuídos, mas é chamada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuída, você poderá especificar a ação que ocorre sempre que alguém deixa sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu atendimento ao cliente, poderá incluir o número antigo de atendimento ao cliente na tabela, e atribuí-lo a um anúncio que fornece o novo número.</span><span class="sxs-lookup"><span data-stu-id="2006c-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2006c-112">Antes de configurar a tabela numérica não atribuída, seu sistema já deve ter comunicados definidos ou uma configuração de atendedor automático de Unificação de mensagens do Exchange (um).</span><span class="sxs-lookup"><span data-stu-id="2006c-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="2006c-113">Quando alguém chama um número não atribuído, o Lync Server procura a tabela número não atribuído da parte superior para a inferior e usa o primeiro intervalo correspondente.</span><span class="sxs-lookup"><span data-stu-id="2006c-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="2006c-114">Portanto, uma ação que você deseja executar como última alternativa deve ser especificada para o último intervalo na tabela.</span><span class="sxs-lookup"><span data-stu-id="2006c-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2006c-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2006c-115">In This Section</span></span>

<span data-ttu-id="2006c-116">[Criar ou modificar um intervalo de números não atribuídos no Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [criar um anúncio no Lync Server 2013](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="2006c-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

