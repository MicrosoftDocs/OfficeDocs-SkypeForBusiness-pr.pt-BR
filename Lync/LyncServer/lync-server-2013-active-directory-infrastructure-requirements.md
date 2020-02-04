---
title: 'Lync Server 2013: Requisitos de infraestrutura do Active Directory'
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
ms.openlocfilehash: 75278700623ae7251fe7cebec36e959a38f325dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="bec67-102">Requisitos de infraestrutura do Active Directory para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec67-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bec67-103">_**Tópico da última modificação:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="bec67-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="bec67-104">Antes de iniciar o processo de preparação dos serviços de domínio Active Directory para o Lync Server 2013, certifique-se de que a sua infraestrutura do Active Directory atenda aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="bec67-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="bec67-105">Todos os controladores de domínio (que incluem todos os servidores de catálogo global) na floresta em que você implanta o Lync Server executam um dos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="bec67-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="bec67-106">Sistema operacional Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bec67-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="bec67-107">Sistema operacional Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="bec67-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="bec67-108">Sistema operacional Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="bec67-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="bec67-109">Sistema operacional Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="bec67-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="bec67-110">Windows Server 2008 Enterprise 32-bit</span><span class="sxs-lookup"><span data-stu-id="bec67-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="bec67-111">versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="bec67-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="bec67-112">versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="bec67-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="bec67-113">Todos os domínios nos quais você implanta o Lync Server são gerados para um nível funcional de domínio do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="bec67-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="bec67-114">A floresta na qual você implanta o Lync Server é gerada para um nível funcional da floresta do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="bec67-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bec67-115">Para alterar o nível funcional do domínio ou da floresta, consulte "elevando os níveis funcionais do domínio e da floresta <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>" na biblioteca do TechNet em.</span><span class="sxs-lookup"><span data-stu-id="bec67-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="bec67-116">Um catálogo global é implantado em cada domínio onde você implanta usuários ou computadores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bec67-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="bec67-117">O Lync Server 2013 dá suporte a grupos universais nos sistemas operacionais Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="bec67-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="bec67-118">Os membros dos grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínio e podem receber permissões em qualquer domínio na árvore ou floresta de domínio.</span><span class="sxs-lookup"><span data-stu-id="bec67-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="bec67-119">O suporte a grupos universais, combinado com delegação de administrador, simplifica o gerenciamento de uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bec67-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="bec67-120">Por exemplo, não é necessário adicionar um domínio a outro para permitir que um administrador os gerencie.</span><span class="sxs-lookup"><span data-stu-id="bec67-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

