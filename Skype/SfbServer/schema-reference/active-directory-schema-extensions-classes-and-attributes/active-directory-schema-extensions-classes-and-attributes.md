---
title: Extensões, classes e atributos do esquema do Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Esta seção de referência inclui as seguintes informações:'
ms.openlocfilehash: dc2d147791317134ee9abd3de723f1c53f8f625b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907098"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="89ae3-103">Extensões, classes e atributos do esquema do Active Directory</span><span class="sxs-lookup"><span data-stu-id="89ae3-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="89ae3-104">Esta seção de referência inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="89ae3-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="89ae3-105">Extensões de esquema Active Directory que são novas ou alteradas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="89ae3-106">Esquema do Active Directory contém definições formais de cada classe de objeto que podem ser criados em uma floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="89ae3-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="89ae3-107">O esquema também contém definições formais de todos os atributos que podem existir em um objeto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="89ae3-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="89ae3-108">O catálogo global do Active Directory contém réplicas de todos os objetos da floresta, além de um subconjunto dos atributos de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="89ae3-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="89ae3-109">Esta seção descreve as classes e atributos que são novas ou alteradas no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="89ae3-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="89ae3-110">Todas as classes usadas pelo Skype para Business Server, com uma descrição de cada</span><span class="sxs-lookup"><span data-stu-id="89ae3-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="89ae3-111">Todas os atributos usados pelo Skype para Business Server, com uma descrição de cada</span><span class="sxs-lookup"><span data-stu-id="89ae3-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="89ae3-112">Uma lista das classes usadas pelo Skype para Business Server, com os atributos que cada uma pode conter</span><span class="sxs-lookup"><span data-stu-id="89ae3-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="89ae3-113">Configurações globais e objetos, além de grupos universais de serviço e administração criados durante a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="89ae3-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="89ae3-114">Entradas de controle de acesso (ACEs) que são criadas nos domínio raiz e nos contêineres internos durante a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="89ae3-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="89ae3-115">Alterações feitas em uma unidade organizacional (UO) do Active Directory pelo cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="89ae3-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="89ae3-116">Alterações feitas em uma unidade Organizacional do Active Directory pelo cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="89ae3-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="89ae3-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="89ae3-117">In This Section</span></span>

- [<span data-ttu-id="89ae3-118">Alterações de esquema no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="89ae3-119">Classes de esquema e descrições Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="89ae3-120">Atributos de esquema e descrições Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="89ae3-121">Atributos de esquema por classe no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="89ae3-122">Alterações feitas pela preparação de floresta no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="89ae3-123">Alterações feitas pela preparação do domínio no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="89ae3-124">Alterações feitas por Grant-CsSetupPermission no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="89ae3-125">Alterações feitas por Grant-CsOUPermission no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="89ae3-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

