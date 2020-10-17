---
title: 'Lync Server 2013: extensões, classes e atributos do esquema do Active Directory usados pelo Lync Server'
description: 'Lync Server 2013: extensões, classes e atributos do esquema do Active Directory usados pelo Lync Server.'
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
ms.openlocfilehash: beac778d3315573f4d5cc6cb9c827a3a2fce9d0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567947"
---
# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="2c79a-103">Extensões, classes e atributos do esquema do Active Directory usados pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-103">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c79a-104">_**Última modificação do tópico:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="2c79a-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="2c79a-105">Esta seção de referência inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="2c79a-105">This reference section includes the following information:</span></span>

  - <span data-ttu-id="2c79a-106">Extensões de esquema do Active Directory novas ou alteradas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-106">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="2c79a-107">O esquema do Active Directory contém definições formais de cada classe de objeto que pode ser criadas em uma floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c79a-107">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="2c79a-108">O esquema também contém definições formais de cada atributo que podem existir em um objeto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c79a-108">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="2c79a-109">O catálogo global do Active Directory contém réplicas de todos os objetos da floresta, juntamente com um subconjunto dos atributos de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="2c79a-109">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="2c79a-110">Esta seção descreve as classes e os atributos que são novos ou alterados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c79a-110">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="2c79a-111">Todas as classes usadas pelo Lync Server, com uma descrição de cada</span><span class="sxs-lookup"><span data-stu-id="2c79a-111">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="2c79a-112">Todos os atributos usados pelo Lync Server, com uma descrição de cada</span><span class="sxs-lookup"><span data-stu-id="2c79a-112">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="2c79a-113">Uma lista das classes usadas pelo Lync Server, com os atributos que cada uma pode conter</span><span class="sxs-lookup"><span data-stu-id="2c79a-113">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="2c79a-114">Configurações e objetos globais, além de grupos universais de serviço e administração criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="2c79a-114">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="2c79a-115">ACEs (entradas de controle de acesso) criadas na raiz do domínio e nos contêineres internos durante a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="2c79a-115">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="2c79a-116">Alterações feitas em uma OU (unidade organizacional) do Active Directory pelo \_ cmdlet Grant CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="2c79a-116">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="2c79a-117">Alterações feitas em uma OU do Active Directory pelo \_ cmdlet Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="2c79a-117">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2c79a-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2c79a-118">In This Section</span></span>

  - [<span data-ttu-id="2c79a-119">Alterações de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-119">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="2c79a-120">Classes e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-120">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="2c79a-121">Atributos e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-121">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="2c79a-122">Atributos de esquema por classe no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-122">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="2c79a-123">Alterações feitas pela preparação da floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-123">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="2c79a-124">Alterações feitas pela preparação do domínio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-124">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="2c79a-125">Alterações feitas por Grant-CsSetupPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-125">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="2c79a-126">Alterações feitas por Grant-CsOUPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79a-126">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

