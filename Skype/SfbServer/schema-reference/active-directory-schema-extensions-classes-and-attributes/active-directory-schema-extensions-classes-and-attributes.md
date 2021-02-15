---
title: Extensões, classes e atributos do esquema do Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Esta seção de referência inclui as seguintes informações:'
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831931"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="10891-103">Extensões, classes e atributos do esquema do Active Directory</span><span class="sxs-lookup"><span data-stu-id="10891-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="10891-104">Esta seção de referência inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="10891-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="10891-105">Extensões de esquema do Active Directory novas ou alteradas para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="10891-106">O esquema do Active Directory contém definições formais de cada classe de objeto que pode ser criadas em uma floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10891-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="10891-107">O esquema também contém definições formais de cada atributo que podem existir em um objeto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10891-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="10891-108">O catálogo global do Active Directory contém réplicas de todos os objetos da floresta, juntamente com um subconjunto dos atributos de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="10891-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="10891-109">Esta seção descreve as classes e atributos que são novos ou alterados no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="10891-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="10891-110">Todas as classes usadas pelo Skype for Business Server, com uma descrição de cada</span><span class="sxs-lookup"><span data-stu-id="10891-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="10891-111">Todos os atributos usados pelo Skype for Business Server, com uma descrição de cada</span><span class="sxs-lookup"><span data-stu-id="10891-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="10891-112">Uma lista das classes usadas pelo Skype for Business Server, com os atributos que cada uma pode conter</span><span class="sxs-lookup"><span data-stu-id="10891-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="10891-113">Configurações e objetos globais, além de grupos universais de serviço e administração criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="10891-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="10891-114">ACEs (entradas de controle de acesso) criadas na raiz do domínio e nos contêineres internos durante a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="10891-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="10891-115">Alterações feitas em uma OU (unidade organizacional) do Active Directory pelo cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="10891-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="10891-116">Alterações feitas em uma UO do Active Directory pelo cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="10891-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="10891-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="10891-117">In This Section</span></span>

- [<span data-ttu-id="10891-118">Alterações de esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="10891-119">Classes e descrições de esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="10891-120">Atributos e descrições de esquema no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="10891-121">Atributos de esquema por classe no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="10891-122">Alterações feitas pela preparação da floresta no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="10891-123">Alterações feitas pela preparação de domínio no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="10891-124">Alterações feitas pela Grant-CsSetupPermission no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="10891-125">Alterações feitas pela Grant-CsOUPermission no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="10891-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

