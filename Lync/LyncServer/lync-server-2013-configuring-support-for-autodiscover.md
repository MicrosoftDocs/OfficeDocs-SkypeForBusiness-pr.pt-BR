---
title: 'Lync Server 2013: Configurando o suporte para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 779929d270fa4ae2f8eec59a954c2273ff61b44f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="9f18f-102">Configurando o suporte para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f18f-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f18f-103">_**Tópico da última modificação:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="9f18f-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="9f18f-104">O **serviço de descoberta automática** de serviços Web do Lync Server apareceu pela primeira vez na atualização cumulativa do lync Server 2010: de novembro de 2011.</span><span class="sxs-lookup"><span data-stu-id="9f18f-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="9f18f-105">Esta atualização foi acompanhada pela versão inicial dos clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="9f18f-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="9f18f-106">O serviço de descoberta automática expôs os serviços de mobilidade, conhecidos como o serviço MCX.</span><span class="sxs-lookup"><span data-stu-id="9f18f-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="9f18f-107">O serviço de descoberta automática age como um local único para que todos os clientes solicitem informações sobre quais serviços e recursos estão disponíveis, e como entrar em contato com o sevices – seja por um nome de domínio totalmente qualificado ou uma referência do localizador de recursos uniforme da Web.</span><span class="sxs-lookup"><span data-stu-id="9f18f-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="9f18f-108">A descoberta automática expõe diversos recursos, e cada cliente fará solicitações com base nos recursos que o cliente pode usar.</span><span class="sxs-lookup"><span data-stu-id="9f18f-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="9f18f-109">Por exemplo, um cliente do Lync da área de trabalho do 2013 usará o autodiscvoer para determinar os serviços Web externos, mas não usará os serviços de mobilidade (MCX).</span><span class="sxs-lookup"><span data-stu-id="9f18f-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="9f18f-110">Para definir e habilitar corretamente seus clientes para usar os recursos disponíveis para eles, os cenários que permitem que um cliente encontre e use entradas de descoberta automática devem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="9f18f-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="9f18f-111">Para usar o autodoscover, sua implantação requer que um proxy reverso publique os serviços Web do Lync Server, que os registros DNS são configurados para resolver consultas DNS para o serviço de descoberta automática do Lync e para serviços Web do Lync Server e para os serviços de certificado estão configurados corretamente para o seu cenário específico.</span><span class="sxs-lookup"><span data-stu-id="9f18f-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9f18f-112">Para obter detalhes técnicos sobre o que os elementos da solicitação/resposta do autodiscover fazem, consulte <A href="lync-server-2013-understanding-autodiscover.md">compreendendo a descoberta automática no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9f18f-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9f18f-113">As seguintes informações e tabelas definem, por cenário, quais configurações (se houver) que você precisa implementar para fornecer o uso completo e efetivo do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="9f18f-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="9f18f-114">As informações nos tópicos a seguir são específicas do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f18f-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="9f18f-115">Se você estiver procurando orientação sobre como planejar a mobilidade do Lync Server 2010, consulte [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span><span class="sxs-lookup"><span data-stu-id="9f18f-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="9f18f-116">Para implantar o Mobility para o Lync Server 2010, consulte[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="9f18f-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9f18f-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9f18f-117">In This Section</span></span>

  - [<span data-ttu-id="9f18f-118">Configurando o DNS para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f18f-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="9f18f-119">Configurando certificados para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f18f-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="9f18f-120">Configurando um proxy inverso para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f18f-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="9f18f-121">Configurando a descoberta automática no Lync Server 2013 para implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="9f18f-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

