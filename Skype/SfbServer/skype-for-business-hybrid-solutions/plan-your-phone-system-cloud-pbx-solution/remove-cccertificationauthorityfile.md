---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: O Remove-CcCertificationAuthorityFile cmdlet remove o arquivo de backup do serviço de autoridade de certificação na pasta ac sob o diretório de compartilhamento de site do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824287"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="ed502-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="ed502-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="ed502-104">O cmdlet Remove-CcCertificationAuthorityFile remove o arquivo de backup do serviço de autoridade de certificação " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" na pasta CA no diretório de compartilhamento de site do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="ed502-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="ed502-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ed502-105">Parameters</span></span>

<span data-ttu-id="ed502-106">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ed502-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ed502-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ed502-107">Examples</span></span>
<span data-ttu-id="ed502-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ed502-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ed502-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="ed502-109">Example 1</span></span>

<span data-ttu-id="ed502-110">O exemplo a seguir remove o arquivo de backup do serviço de autoridade de certificação " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" na pasta CA sob o diretório de compartilhamento de site:</span><span class="sxs-lookup"><span data-stu-id="ed502-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="ed502-111">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="ed502-111">Input Types</span></span>
<span data-ttu-id="ed502-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed502-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ed502-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ed502-113">None.</span></span> <span data-ttu-id="ed502-114">O Remove-CcCertificationAuthorityFile cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="ed502-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ed502-115">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="ed502-115">Return Types</span></span>
<span data-ttu-id="ed502-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed502-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ed502-117">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ed502-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ed502-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed502-118">See also</span></span>
<span data-ttu-id="ed502-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed502-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ed502-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="ed502-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

