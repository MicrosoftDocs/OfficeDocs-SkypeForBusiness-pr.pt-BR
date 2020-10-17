---
title: 'Lync Server 2013: requisitos de infraestrutura do Active Directory'
description: 'Lync Server 2013: requisitos de infraestrutura do Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62218605c9b3fac20743d0b6bb475515c9498f9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552357"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="12722-103">Requisitos de infraestrutura do Active Directory para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12722-103">Active Directory infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12722-104">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="12722-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="12722-105">Antes de iniciar o processo de preparação dos serviços de domínio do Active Directory para o Lync Server 2013, verifique se a sua infraestrutura do Active Directory atende aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="12722-105">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="12722-106">Todos os controladores de domínio (que incluem todos os servidores de catálogo global) na floresta onde você implanta o Lync Server executam um dos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="12722-106">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="12722-107">Sistema operacional Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="12722-107">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="12722-108">Sistema operacional Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="12722-108">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="12722-109">Windows Server 2008 R2 operating system</span><span class="sxs-lookup"><span data-stu-id="12722-109">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="12722-110">Sistema operacional Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="12722-110">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="12722-111">Windows Server 2008 Enterprise de 32 bits</span><span class="sxs-lookup"><span data-stu-id="12722-111">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="12722-112">versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="12722-112">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="12722-113">versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="12722-113">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="12722-114">Todos os domínios nos quais você implanta o Lync Server são gerados para um nível funcional de domínio do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="12722-114">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="12722-115">A floresta na qual você implanta o Lync Server é elevada para um nível funcional de floresta do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="12722-115">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12722-116">Para alterar o nível funcional da floresta ou domínio, consulte "elevando os níveis funcionais do domínio e da floresta" na biblioteca do TechNet em <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> .</span><span class="sxs-lookup"><span data-stu-id="12722-116">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="12722-117">Um catálogo global é implantado em todos os domínios onde você implanta computadores ou usuários do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12722-117">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="12722-118">O Lync Server 2013 oferece suporte aos grupos universais nos sistemas operacionais Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="12722-118">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="12722-119">Os membros de grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínios e podem receber permissões em qualquer domínio na árvore ou floresta de domínios.</span><span class="sxs-lookup"><span data-stu-id="12722-119">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="12722-120">O suporte a grupos universais, combinado com a delegação de administrador, simplifica o gerenciamento de uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12722-120">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="12722-121">Por exemplo, não é necessário adicionar um domínio para outro para permitir que um administrador gerencie os dois.</span><span class="sxs-lookup"><span data-stu-id="12722-121">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

