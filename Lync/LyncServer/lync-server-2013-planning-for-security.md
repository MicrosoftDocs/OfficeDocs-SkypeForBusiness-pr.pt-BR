---
title: 'Lync Server 2013: planejamento de segurança'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f99fbd5e511063d7687dbb9e1b9a73fa0cb6ab6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506998"
---
# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="b674e-102">Planejamento de segurança no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b674e-102">Planning for security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b674e-103">_**Última modificação do tópico:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="b674e-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="b674e-104">Use esta seção de segurança para avaliar e gerenciar riscos de segurança na sua implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b674e-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="b674e-105">Mesmo que sua implantação do Lync Server 2013 seja modesto, é provável que você tenha componentes em sua rede com sua própria documentação de segurança.</span><span class="sxs-lookup"><span data-stu-id="b674e-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="b674e-106">Portanto, é improvável que esta seção cubra todos os aspectos de segurança para todos os componentes e áreas pertinentes à sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b674e-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="b674e-107">Use esta seção como ponto de partida para lidar com a segurança da sua implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b674e-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="b674e-108">Ele fornece diretrizes gerais e práticas recomendadas para avaliar e gerenciar os riscos de segurança mais comuns.</span><span class="sxs-lookup"><span data-stu-id="b674e-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="b674e-109">Recursos de segurança e produtos adicionais são listados no final de cada tópico.</span><span class="sxs-lookup"><span data-stu-id="b674e-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b674e-110">A segurança é um tópico em constante evolução.</span><span class="sxs-lookup"><span data-stu-id="b674e-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="b674e-111">À medida que surgem novas ameaças e soluções, documentos, soluções, métodos e procedimentos desatualizados devem ser substituídos por materiais atualizados.</span><span class="sxs-lookup"><span data-stu-id="b674e-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b674e-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b674e-112">In This Section</span></span>

  - [<span data-ttu-id="b674e-113">Principais recursos de segurança no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b674e-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="b674e-114">Ameaças comuns à segurança em computação de dia moderno</span><span class="sxs-lookup"><span data-stu-id="b674e-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="b674e-115">Exclusões de verificação antivírus para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b674e-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="b674e-116">Estrutura de segurança para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b674e-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="b674e-117">Lidando com ameaças à sua infraestrutura principal do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b674e-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="b674e-118">Implantando uma porta e um alias não padrão do SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b674e-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

