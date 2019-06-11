---
title: 'Lync Server 2013: configurar números de telefone não atribuídos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22441573c22a932c383c7821cce16d79b9767a7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="6e79f-102">Configurar números de telefone não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e79f-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e79f-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6e79f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6e79f-104">O Lync Server permite configurar o que acontece com as chamadas recebidas para números de telefone que sejam válidos para a sua organização, mas não são atribuídos a um usuário ou a um telefone.</span><span class="sxs-lookup"><span data-stu-id="6e79f-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="6e79f-105">Para configurar o tratamento dessas chamadas, configure uma tabela de número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="6e79f-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="6e79f-106">Você pode usar a tabela para direcionar as chamadas para um aplicativo de anúncio ou para um servidor de UM Exchange.</span><span class="sxs-lookup"><span data-stu-id="6e79f-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="6e79f-p102">Como configurar a tabela de números não atribuídos dependerá de como você deseja usá-la. Você pode configurar a tabela com todas as extensões válidas para a sua organização, somente com extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuídos pode incluir ambos, números atribuídos e não atribuídos, mas será invocada somente quando um chamador discar um número que não esteja atribuído atualmente. Se você incluir todas as extensões válidas na tabela de números não atribuídos, pode especificar a ação que ocorre sempre que alguém sair da sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, pode ajustar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao cliente, poderá incluir o número do atendimento ao cliente antigo na tabela e atribuí-lo a um comunicado que fornece o novo número.</span><span class="sxs-lookup"><span data-stu-id="6e79f-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e79f-113">Antes de configurar a tabela número não atribuído, você já deve ter um ou mais comunicados definidos ou um atendedor automático de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6e79f-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="6e79f-114">Para obter detalhes sobre como criar comunicados, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e79f-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="6e79f-115">Para ver se você configurou as configurações de UM do Exchange UM, execute o cmdlet <STRONG>Get-CsExUmContact</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="6e79f-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="6e79f-116">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span><span class="sxs-lookup"><span data-stu-id="6e79f-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e79f-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6e79f-117">In This Section</span></span>

  - [<span data-ttu-id="6e79f-118">Criar ou modificar um intervalo de números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e79f-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="6e79f-119">Excluir um intervalo de números não atribuído no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e79f-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

