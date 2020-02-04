---
title: 'Lync Server 2013: Extensões, classes e atributos do esquema do Active Directory usado pelo Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ec6b3eff05ba27b41488aea49bb0347d058b6f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="aebbd-102">Extensões, classes e atributos do esquema do Active Directory usado pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aebbd-103">_**Tópico da última modificação:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="aebbd-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="aebbd-104">Esta seção de referência inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="aebbd-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="aebbd-105">Extensões de esquema do Active Directory novas ou alteradas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="aebbd-106">O esquema do Active Directory contém definições formais de cada classe de objeto que podem ser criadas em uma floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aebbd-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="aebbd-107">O esquema também contém definições formais de cada atributo que podem existir em um objeto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aebbd-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="aebbd-108">O catálogo global do Active Directory contém réplicas de todos os objetos da floresta, juntamente com um subconjunto de atributos para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="aebbd-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="aebbd-109">Esta seção descreve as classes e os atributos que são novos ou alterados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aebbd-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="aebbd-110">Todas as classes usadas pelo Lync Server, com uma descrição de cada</span><span class="sxs-lookup"><span data-stu-id="aebbd-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="aebbd-111">Todos os atributos usados pelo Lync Server, com uma descrição de cada um</span><span class="sxs-lookup"><span data-stu-id="aebbd-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="aebbd-112">Uma lista das classes usadas pelo Lync Server, com os atributos que cada uma pode conter</span><span class="sxs-lookup"><span data-stu-id="aebbd-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="aebbd-113">Configurações e objetos globais, além dos grupos de administração e serviço universal criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="aebbd-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="aebbd-114">ACEs (entradas de controle de acesso) criadas na raiz do domínio e nos contêineres internos durante a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="aebbd-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="aebbd-115">Alterações feitas em uma UO (unidade organizacional) do Active Directory pelo cmdlet Grant\_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="aebbd-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="aebbd-116">Alterações feitas em uma UO do Active Directory pelo cmdlet Grant\_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="aebbd-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aebbd-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="aebbd-117">In This Section</span></span>

  - [<span data-ttu-id="aebbd-118">Alterações de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="aebbd-119">Classes e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="aebbd-120">Atributos e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="aebbd-121">Atributos de esquema por classe no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="aebbd-122">Alterações feitas pela preparação da floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="aebbd-123">Alterações feitas por preparação do domínio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="aebbd-124">Alterações feitas pelo Grant-CsSetupPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="aebbd-125">Alterações feitas pelo Grant-CsOUPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebbd-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

