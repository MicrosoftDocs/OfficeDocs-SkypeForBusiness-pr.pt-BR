---
title: 'Lync Server 2013: suporte aos serviços de domínio do Active Directory'
description: 'Lync Server 2013: suporte aos serviços de domínio do Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558677"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="32352-103">Suporte aos serviços de domínio do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32352-103">Active Directory Domain Services support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32352-104">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="32352-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="32352-105">O Lync Server 2013 usa o repositório de gerenciamento central para armazenar dados de configuração para servidores e serviços, em vez de confiar nos serviços de domínio do Active Directory para essas informações, como no passado.</span><span class="sxs-lookup"><span data-stu-id="32352-105">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="32352-106">O Lync Server 2013 ainda armazena o seguinte no AD DS:</span><span class="sxs-lookup"><span data-stu-id="32352-106">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="32352-107">**Extensões de esquema**</span><span class="sxs-lookup"><span data-stu-id="32352-107">**Schema extensions**</span></span>
    
      - <span data-ttu-id="32352-108">Extensões do objeto do usuário</span><span class="sxs-lookup"><span data-stu-id="32352-108">User object extensions</span></span>
    
      - <span data-ttu-id="32352-109">Extensões para o Lync Server 2010 e o Office Communications Server 2007 R2 classes para manter a compatibilidade com versões anteriores com suporte</span><span class="sxs-lookup"><span data-stu-id="32352-109">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="32352-110">**Dados** (armazenados no esquema estendido do Lync Server 2013 e em classes existentes)</span><span class="sxs-lookup"><span data-stu-id="32352-110">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="32352-111">URI do SIP do usuário e outras configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="32352-111">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="32352-112">Objetos de contato para aplicativos (por exemplo, o aplicativo de grupo de resposta e o aplicativo de atendedor de conferência)</span><span class="sxs-lookup"><span data-stu-id="32352-112">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="32352-113">Dados publicados para compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="32352-113">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="32352-114">Um ponto de controle de serviço (SCP) para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="32352-114">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="32352-115">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="32352-115">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="32352-116">Esta seção descreve os requisitos de suporte do AD DS para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32352-116">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="32352-117">Para obter detalhes sobre o suporte à topologia, consulte [topologias do Active Directory com suporte no Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="32352-117">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="32352-118">Sistemas operacionais do controlador de domínio com suporte</span><span class="sxs-lookup"><span data-stu-id="32352-118">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="32352-119">O Lync Server 2013 suporta controladores de domínio executando os seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="32352-119">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="32352-120">Sistema operacional Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="32352-120">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="32352-121">Sistema operacional Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="32352-121">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="32352-122">Windows Server 2008 R2 operating system</span><span class="sxs-lookup"><span data-stu-id="32352-122">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="32352-123">Sistema operacional Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="32352-123">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="32352-124">Windows Server 2008 Enterprise de 32 bits</span><span class="sxs-lookup"><span data-stu-id="32352-124">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="32352-125">As versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="32352-125">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="32352-126">As versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="32352-126">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="32352-127">Nível funcional de floresta e domínio</span><span class="sxs-lookup"><span data-stu-id="32352-127">Forest and Domain Functional Level</span></span>

<span data-ttu-id="32352-128">Você deve aumentar todos os domínios nos quais o Lync Server 2013 é implantado em um nível funcional de domínio do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="32352-128">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="32352-129">Todas as florestas nas quais você implanta o Lync Server 2013 devem ser elevadas para um nível funcional de floresta do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="32352-129">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="32352-130">Suporte para controladores de domínio Read-Only</span><span class="sxs-lookup"><span data-stu-id="32352-130">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="32352-131">O Lync Server 2013 oferece suporte a implantações de serviços de domínio do Active Directory que incluem controladores de domínio somente leitura ou servidores de catálogo global somente leitura, desde que haja controladores de domínio graváveis disponíveis.</span><span class="sxs-lookup"><span data-stu-id="32352-131">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="32352-132">Nomes de domínio</span><span class="sxs-lookup"><span data-stu-id="32352-132">Domain Names</span></span>

<span data-ttu-id="32352-133">O Lync Server não dá suporte a domínios com rótulo único.</span><span class="sxs-lookup"><span data-stu-id="32352-133">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="32352-134">Por exemplo, uma floresta com um domínio raiz chamado **contoso.local** é suportado, mas um domínio raiz chamado **local** não é suportado.</span><span class="sxs-lookup"><span data-stu-id="32352-134">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="32352-135">Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento da Microsoft, "informações sobre como configurar o Windows para domínios com nomes DNS de rótulo único" em [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .</span><span class="sxs-lookup"><span data-stu-id="32352-135">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32352-136">O Lync Server não dá suporte à renomeação de domínios.</span><span class="sxs-lookup"><span data-stu-id="32352-136">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="32352-137">Se for necessário renomear um domínio em que o Lync Server está implantado, primeiro você precisa desinstalar o Lync Server, renomear o domínio e, em seguida, reinstalar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32352-137">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="32352-138">Ambientes AD DS bloqueados</span><span class="sxs-lookup"><span data-stu-id="32352-138">Locked Down AD DS Environments</span></span>

<span data-ttu-id="32352-139">Em um ambiente do AD DS bloqueado, os usuários e os objetos de computador costumam ser colocados em unidades organizacionais (UOs) específicas com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de GPOs (objetos de política de grupo) para impor políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="32352-139">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="32352-140">O Lync Server 2013 pode ser implantado em um ambiente do Active Directory bloqueado.</span><span class="sxs-lookup"><span data-stu-id="32352-140">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="32352-141">Para obter detalhes sobre o que é necessário para implantar o Lync Server em um ambiente bloqueado, consulte [preparação de serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="32352-141">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

