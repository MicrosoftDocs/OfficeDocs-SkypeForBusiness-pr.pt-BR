---
title: 'Lync Server 2013: segurança de dados de emparelhamento do pool de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26759c982723fd656ac3456aad630bc695a7343e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="68ff7-102">Segurança de dados de emparelhamento do pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ff7-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ff7-103">_**Última modificação do tópico:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="68ff7-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="68ff7-104">O serviço de backup é um mecanismo de replicação de dados introduzido no Lync Server 2013 que transfere o conteúdo de conferência e dados de usuários entre dois pools de front-ends emparelhados em dois data centers para fins de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="68ff7-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="68ff7-105">Os dados dos usuários contêm as SIP URIs dos usuários, bem como listas de contatos e configurações.</span><span class="sxs-lookup"><span data-stu-id="68ff7-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="68ff7-106">O conteúdo de conferência inclui carregamentos do Microsoft PowerPoint 2010, bem como quadros de comunicações usados em conferências.</span><span class="sxs-lookup"><span data-stu-id="68ff7-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="68ff7-107">Do pool de origem, os dados dos usuários e o conteúdo das conferências são exportados do armazenamento local, compactados, transferidos para o Pool de destino, onde são descompactados e importados ao armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="68ff7-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="68ff7-108">O Serviço de Backup pressupõe que o link de comunicação entre os dois data centers está dentro da rede da empresa, protegida da Internet.</span><span class="sxs-lookup"><span data-stu-id="68ff7-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="68ff7-109">Ele não criptografa os dados transferidos entre os dois data centers, nem está encapsulado de forma nativa em um protocolo protegido, como HTTPS.</span><span class="sxs-lookup"><span data-stu-id="68ff7-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="68ff7-110">Portanto, o ataque de "intrusos" de pessoal interno na rede da empresa é possível.</span><span class="sxs-lookup"><span data-stu-id="68ff7-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="68ff7-111">Avaliação dos riscos à segurança</span><span class="sxs-lookup"><span data-stu-id="68ff7-111">Evaluating Security Risks</span></span>

<span data-ttu-id="68ff7-112">Qualquer empresa que implanta o Lync Server 2013 em vários data centers e usa o recurso de recuperação de desastres deve garantir que o tráfego entre data centers seja protegido pela intranet corporativa.</span><span class="sxs-lookup"><span data-stu-id="68ff7-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="68ff7-113">As empresas que se preocupam com proteção interna contra ataques devem proteger os links de comunicação entre os data centers.</span><span class="sxs-lookup"><span data-stu-id="68ff7-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="68ff7-p103">A presunção de que os data centers de uma empresa estão protegidos atrás da Intranet da empresa é padrão. Há muitos outros tipos de dados empresariais sensíveis transferidos entre esses data centers. A infraestrutura de TI da empresa corre grande perigo se esses links entre os data centers não forem protegidos.</span><span class="sxs-lookup"><span data-stu-id="68ff7-p103">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard. There are many other types of corporate sensitive data transferred among these data centers. The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="68ff7-p104">Embora exista o risco de ataques de "intrusos" na rede da empresa, ele é relativamente limitado em comparação a expor o tráfego à Internet. Especificamente, os dados dos usuários expostos pelo Serviço de Backup (como SIP URIs) estão geralmente disponíveis para todos os funcionários da empresa através de outros meios como o Catálogo de Endereços Global do Exchange ou outro software de diretório. Portanto, o foco deve estar em proteger a WAN entre os dois data centers quando o Serviço de Backup é usado para copiar dados entre dois Pools emparelhados.</span><span class="sxs-lookup"><span data-stu-id="68ff7-p104">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet. Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software. Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="68ff7-120">Mitigação dos riscos à segurança</span><span class="sxs-lookup"><span data-stu-id="68ff7-120">Mitigating Security Risks</span></span>

<span data-ttu-id="68ff7-121">Há várias maneiras de aprimorar a proteção de segurança para o tráfego do serviço de backup, variando de restringir o acesso aos data centers para proteger o transporte de WAN entre os dois data centers.</span><span class="sxs-lookup"><span data-stu-id="68ff7-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="68ff7-122">Na maioria dos casos, as empresas que estão implantando o Lync Server 2013 talvez já tenham a infraestrutura de segurança necessária em vigor.</span><span class="sxs-lookup"><span data-stu-id="68ff7-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="68ff7-123">Para empresas que procuram orientações, a Microsoft oferece uma solução como um exemplo de como criar uma infraestrutura de ti segura.</span><span class="sxs-lookup"><span data-stu-id="68ff7-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="68ff7-124">No entanto, isso não significa que é a única solução, nem significa que ela é a solução preferida para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68ff7-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="68ff7-125">Recomendamos que os clientes corporativos escolham a solução adequada às suas necessidades específicas, com base em sua infraestrutura de segurança de ti e seus requisitos. O exemplo de solução da Microsoft emprega IPSec e diretiva de grupo para o isolamento de servidor e domínio.</span><span class="sxs-lookup"><span data-stu-id="68ff7-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="68ff7-126">Para obter detalhes, [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544)consulte.</span><span class="sxs-lookup"><span data-stu-id="68ff7-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="68ff7-127">Para perguntas e comentários, entre em contato com secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="68ff7-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="68ff7-128">Outra solução possível é usar o IPSec apenas para ajudar a proteger os dados enviados pelo próprio serviço de backup.</span><span class="sxs-lookup"><span data-stu-id="68ff7-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="68ff7-129">Se você escolher esse método, deverá configurar as regras IPSec para o protocolo SMB para os servidores a seguir, em que o pool A e o pool B são dois pools de front-ends emparelhados.</span><span class="sxs-lookup"><span data-stu-id="68ff7-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="68ff7-130">O serviço SMB (TCP/445) de cada servidor front-end no pool A para o repositório de arquivos usado pelo pool B.</span><span class="sxs-lookup"><span data-stu-id="68ff7-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="68ff7-131">O serviço SMB (TCP/445) de cada servidor front-end no pool B para o repositório de arquivos usado pelo pool A.</span><span class="sxs-lookup"><span data-stu-id="68ff7-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="68ff7-132">O IPsec não se destina a substituir a segurança no nível do aplicativo, como SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="68ff7-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="68ff7-133">Uma vantagem de usar o IPsec é que ele pode fornecer segurança de tráfego de rede para aplicativos existentes sem precisar alterá-los.</span><span class="sxs-lookup"><span data-stu-id="68ff7-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="68ff7-134">As empresas que desejam apenas proteger o transporte entre os dois data centers devem consultar seus respectivos fornecedores de hardware de rede sobre maneiras de configurar conexões WAN seguras usando o equipamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="68ff7-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

