---
title: 'Lync Server 2013: suporte à unificação de mensagens (UM) do Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd46b19ea52b56b70cc5bd4c459f2260a97306d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="98f5a-102">Suporte à unificação de mensagens (UM) do Exchange no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98f5a-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98f5a-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="98f5a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="98f5a-104">O Lync Server 2013 oferece suporte à integração com a Unificação de mensagens (UM) do Exchange para combinar mensagens de voz e mensagens de email em uma única infraestrutura de mensagens.</span><span class="sxs-lookup"><span data-stu-id="98f5a-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="98f5a-105">No Exchange 2013, o UM do Exchange consiste no serviço UM do Exchange, que é instalado e executado no servidor de caixa de correio, e o roteador de chamada de UM, que é instalado e executado no servidor de acesso para cliente.</span><span class="sxs-lookup"><span data-stu-id="98f5a-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="98f5a-106">Para as implantações do Lync Server 2013 Enterprise Voice, o Exchange UM combina mensagens de voz e mensagens de email em um único repositório que pode ser acessado por um telefone (ou seja, Outlook Voice Access) ou um computador.</span><span class="sxs-lookup"><span data-stu-id="98f5a-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="98f5a-107">O Exchange UM e o Lync Server 2013 trabalham juntos para fornecer atendimento de chamadas, Outlook Voice Access e serviços de atendedor automático para usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="98f5a-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="98f5a-108">Além do suporte para integração com implantações locais do UM do Exchange, o Lync Server 2013 oferece suporte à integração com a UM do Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="98f5a-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="98f5a-109">Isso permite que você forneça mensagens de voz aos seus usuários se migrar alguns ou todos eles para um provedor de serviço do Exchange hospedado, como o Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="98f5a-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="98f5a-110">O Lync Server 2013 oferece suporte às seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="98f5a-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="98f5a-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="98f5a-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="98f5a-112">Microsoft Exchange Server 2010 (obrigatório) ou com o Service Pack mais recente (recomendado)</span><span class="sxs-lookup"><span data-stu-id="98f5a-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="98f5a-113">Microsoft Exchange Server 2007 com Service Pack 1 (SP1) (obrigatório) ou Service Pack mais recente (recomendado)</span><span class="sxs-lookup"><span data-stu-id="98f5a-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="98f5a-114">Você não pode colocar o UM do Exchange com o Lync Server 2013 ou um banco de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98f5a-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="98f5a-115">Você pode instalar o UM do Exchange e o Lync Server 2013 em florestas separadas.</span><span class="sxs-lookup"><span data-stu-id="98f5a-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98f5a-116">O Exchange UM pode não ser necessário para implantações do Enterprise Voice que tenham um PBX implantado, pois o PBX pode continuar a fornecer caixa postal e serviços relacionados a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="98f5a-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="98f5a-117">Se você eventualmente desativar o PBX (por exemplo, se você implantar o tronco SIP para conectividade PSTN (rede telefônica pública comutada), deverá reconfigurar o UM do Exchange para fornecer caixa postal aos usuários que usavam o sistema de caixa postal do PBX.</span><span class="sxs-lookup"><span data-stu-id="98f5a-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="98f5a-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="98f5a-118">In This Section</span></span>

  - [<span data-ttu-id="98f5a-119">Componentes e topologias para Unificação de mensagens no local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98f5a-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="98f5a-120">Suporte à integração de UM do Exchange hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98f5a-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

