---
title: 'Lync Server 2013: configurar números de telefone não atribuídos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc319539c9dfe3de79f9cce62391ecd2886e8a1c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="5e892-102">Configurar números de telefone não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e892-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e892-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5e892-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5e892-104">O Lync Server permite que você configure o que acontece com as chamadas de entrada para números de telefone que são válidos para a sua organização, mas não estão atribuídos a um usuário ou telefone.</span><span class="sxs-lookup"><span data-stu-id="5e892-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="5e892-105">Para configurar a manipulação dessas chamadas, configure uma tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="5e892-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="5e892-106">Você pode usar a tabela para encaminhar as chamadas para um aplicativo de comunicado ou para um servidor de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5e892-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="5e892-p102">O modo como você configura a tabela de números não atribuídos depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação dos dois tipos de números. A tabela de números não atribuídos pode incluir números atribuídos e não atribuídos, mas é invocada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuídos, será possível especificar a ação que ocorre quando alguém deixa sua organização, sem precisar reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao consumidor, poderá incluir o número antigo do serviço de atendimento ao consumidor na tabela e atribuí-lo a um anúncio que fornece o novo número.</span><span class="sxs-lookup"><span data-stu-id="5e892-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5e892-113">Antes de configurar a tabela de números não atribuídos, você já deve ter um ou mais comunicados definidos ou um atendedor automático de UM do Exchange configurado.</span><span class="sxs-lookup"><span data-stu-id="5e892-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="5e892-114">Para obter detalhes sobre como criar comunicados, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5e892-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="5e892-115">Para ver se você definiu as configurações do UM do Exchange, execute o cmdlet <STRONG>Get-CsExUmContact</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5e892-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="5e892-116">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span><span class="sxs-lookup"><span data-stu-id="5e892-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5e892-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5e892-117">In This Section</span></span>

  - [<span data-ttu-id="5e892-118">Criar ou modificar um intervalo de números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e892-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="5e892-119">Excluir um intervalo de números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e892-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

