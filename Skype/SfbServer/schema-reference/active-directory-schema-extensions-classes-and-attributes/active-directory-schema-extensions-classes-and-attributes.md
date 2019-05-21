---
title: Extensões, classes e atributos do esquema do Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Esta seção de referência inclui as seguintes informações:'
ms.openlocfilehash: 5934c9ffab8055de86cdaf3bcf507fa9c806f245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296739"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="c1c93-103">Extensões, classes e atributos do esquema do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c1c93-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="c1c93-104">Esta seção de referência inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="c1c93-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="c1c93-105">Extensões de esquema do Active Directory novas ou alteradas para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="c1c93-106">O esquema do Active Directory contém definições formais de cada classe de objeto que podem ser criadas em uma floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c1c93-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="c1c93-107">O esquema também contém definições formais de cada atributo que podem existir em um objeto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c1c93-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="c1c93-108">O catálogo global do Active Directory contém réplicas de todos os objetos da floresta, juntamente com um subconjunto de atributos para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="c1c93-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="c1c93-109">Esta seção descreve as classes e os atributos que são novos ou alterados no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1c93-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="c1c93-110">Todas as classes usadas pelo Skype for Business Server, com uma descrição de cada uma</span><span class="sxs-lookup"><span data-stu-id="c1c93-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="c1c93-111">Todos os atributos usados pelo Skype for Business Server, com uma descrição de cada um</span><span class="sxs-lookup"><span data-stu-id="c1c93-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="c1c93-112">Uma lista das classes usadas pelo Skype for Business Server, com os atributos que cada uma pode conter</span><span class="sxs-lookup"><span data-stu-id="c1c93-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="c1c93-113">Configurações e objetos globais, além dos grupos de administração e serviço universal criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="c1c93-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="c1c93-114">ACEs (entradas de controle de acesso) criadas na raiz do domínio e nos contêineres internos durante a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="c1c93-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="c1c93-115">Alterações feitas em uma UO (unidade organizacional) do Active Directory pelo cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="c1c93-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="c1c93-116">Alterações feitas em uma UO do Active Directory pelo cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="c1c93-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="c1c93-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c1c93-117">In This Section</span></span>

- [<span data-ttu-id="c1c93-118">Alterações de esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="c1c93-119">Descrições e classes de esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="c1c93-120">Atributos e descrições do esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="c1c93-121">Atributos de esquema por classe no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="c1c93-122">Alterações feitas pela preparação da floresta no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="c1c93-123">Alterações feitas pela preparação do domínio no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="c1c93-124">Alterações feitas pelo Grant-CsSetupPermission no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="c1c93-125">Alterações feitas pelo Grant-CsOUPermission no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1c93-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

