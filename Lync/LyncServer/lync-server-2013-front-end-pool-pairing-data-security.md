---
title: 'Lync Server 2013: Segurança de dados de emparelhamento do pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1a408aecedc14162271d5def1adc2bcebdfd82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="b6333-102">Segurança de dados de emparelhamento do pool Front End no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6333-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6333-103">_**Tópico da última modificação:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="b6333-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="b6333-104">O serviço de backup é um mecanismo de replicação de dados introduzido no Lync Server 2013 que transfere dados de usuários e conteúdo de conferência entre dois pools front-ends em dois data centers para fins de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="b6333-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="b6333-105">Os dados do usuário contêm URIs SIP do usuário, bem como as listas de contatos e as configurações.</span><span class="sxs-lookup"><span data-stu-id="b6333-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="b6333-106">O conteúdo da conferência inclui carregamentos do Microsoft PowerPoint 2010, bem como quadros de comunicações usados em conferências.</span><span class="sxs-lookup"><span data-stu-id="b6333-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="b6333-107">Do pool de origem, os dados do usuário e o conteúdo da conferência são exportados do armazenamento local, zipados, transferidos para o pool de destino, onde eles são descompactados e importados para armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="b6333-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="b6333-108">O Serviço de Backup pressupõe que o link de comunicações entre os dois data centers está dentro da rede corporativa que está protegida a partir da Internet.</span><span class="sxs-lookup"><span data-stu-id="b6333-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="b6333-109">Ele não criptografa os dados transferidos entre os dois data centers, nem é encapsulado nativamente em um protocolo seguro, como HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6333-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="b6333-110">Portanto, é possível que o ataque pelo meio Man do pessoal interno na rede da empresa seja possível.</span><span class="sxs-lookup"><span data-stu-id="b6333-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="b6333-111">Avaliando riscos de segurança</span><span class="sxs-lookup"><span data-stu-id="b6333-111">Evaluating Security Risks</span></span>

<span data-ttu-id="b6333-112">Qualquer empresa que implante o Lync Server 2013 em vários data centers e use o recurso de recuperação de desastres deve garantir que o tráfego entre o Data Center seja protegido pela intranet corporativa.</span><span class="sxs-lookup"><span data-stu-id="b6333-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="b6333-113">As empresas que se preocupam com a proteção interna contra ataques devem proteger os links de comunicação entre os data centers.</span><span class="sxs-lookup"><span data-stu-id="b6333-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="b6333-114">A pressuposição de que os dados centrais de uma empresa são protegidos por trás da intranet corporativa é padrão.</span><span class="sxs-lookup"><span data-stu-id="b6333-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="b6333-115">Há muitos outros tipos de dados confidenciais corporativos transferidos entre esses data centers.</span><span class="sxs-lookup"><span data-stu-id="b6333-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="b6333-116">A infraestrutura de ti da empresa está a perigo risco se esses links de Data Center não estiverem protegidos.</span><span class="sxs-lookup"><span data-stu-id="b6333-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="b6333-117">Embora exista o risco de ataques de "intrusos" na rede corporativa, ele é relativamente limitado em comparação a expor o tráfego à Internet.</span><span class="sxs-lookup"><span data-stu-id="b6333-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="b6333-118">Especificamente, os dados do usuário expostos pelo serviço de backup (como URIs SIP) estão disponíveis geralmente para todos os funcionários da empresa por meio de outros meios como o catálogo de endereços global pelo Exchange ou outro software de diretório.</span><span class="sxs-lookup"><span data-stu-id="b6333-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="b6333-119">Portanto, o foco deve estar na proteção da WAN entre os dois data centers quando o serviço de backup é usado para copiar dados entre os dois pools emparelhados.</span><span class="sxs-lookup"><span data-stu-id="b6333-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="b6333-120">Redução de riscos de segurança</span><span class="sxs-lookup"><span data-stu-id="b6333-120">Mitigating Security Risks</span></span>

<span data-ttu-id="b6333-121">Há muitas maneiras de melhorar a proteção de segurança para o tráfego do serviço de backup, desde a restrição do acesso a centros de dados até a proteção do transporte de WAN entre os dois data centers.</span><span class="sxs-lookup"><span data-stu-id="b6333-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="b6333-122">Na maioria dos casos, as empresas que implantam o Lync Server 2013 podem já ter a infraestrutura de segurança necessária implementada.</span><span class="sxs-lookup"><span data-stu-id="b6333-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="b6333-123">Para as empresas que buscam orientação, a Microsoft oferece uma solução como um exemplo de como criar uma infraestrutura de ti segura.</span><span class="sxs-lookup"><span data-stu-id="b6333-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="b6333-124">No entanto, isso não significa que essa é a única solução, nem significa que ela é a solução preferida para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6333-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="b6333-125">Recomendamos que os clientes corporativos escolham a solução adequada às suas necessidades específicas, com base em sua infraestrutura de segurança de ti e seus requisitos. O exemplo de solução da Microsoft emprega IPSec e a política de grupo para o isolamento de servidor e domínio.</span><span class="sxs-lookup"><span data-stu-id="b6333-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="b6333-126">Para obter detalhes, [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)consulte.</span><span class="sxs-lookup"><span data-stu-id="b6333-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="b6333-127">Para perguntas e comentários, entre em contato com a secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b6333-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="b6333-128">Outra solução possível é usar o IPSec apenas para ajudar a proteger os dados enviados pelo próprio Serviço de Backup.</span><span class="sxs-lookup"><span data-stu-id="b6333-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="b6333-129">Se você escolher este método, deverá configurar as regras do IPSec para o protocolo SMB nos seguintes servidores, onde Pool A e Pool B são dois Pools de Front-Ends emparelhados.</span><span class="sxs-lookup"><span data-stu-id="b6333-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="b6333-130">O Serviço SMB (TCP/445) de cada Servidor Front-End no Pool A para o Repositório de Arquivos usado pelo Pool B.</span><span class="sxs-lookup"><span data-stu-id="b6333-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="b6333-131">O Serviço SMB (TCP/445) de cada Servidor Front-End no Pool B para o Repositório de Arquivos usado pelo Pool A.</span><span class="sxs-lookup"><span data-stu-id="b6333-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b6333-132">O IPsec não deve ser usado para substituir a segurança no nível de aplicativo, como SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="b6333-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="b6333-133">Uma vantagem de usar o IPsec é que ele pode fornecer segurança ao tráfego da rede para os aplicativos existentes sem ter de alterá-los.</span><span class="sxs-lookup"><span data-stu-id="b6333-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="b6333-134">As empresas que desejam proteger o transporte entre os dois data centers devem consultar seus respectivos fornecedores de hardware de rede em relação à maneira de configurar conexões WAN seguras usando o equipamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b6333-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

