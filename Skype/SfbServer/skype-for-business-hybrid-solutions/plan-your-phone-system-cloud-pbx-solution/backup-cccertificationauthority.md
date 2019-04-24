---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: "O cmdlet Backup-CcCertificationAuthority \nfaz backup do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e salva na pasta AC no diretório de compartilhamento de site."
ms.openlocfilehash: 2f85a4da58a586852b3331f1f8e482ee17e29e02
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234548"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="11c86-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="11c86-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="11c86-104">O cmdlet Backup-CcCertificationAuthority 
faz backup do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e salva na pasta AC no diretório de compartilhamento de site.</span><span class="sxs-lookup"><span data-stu-id="11c86-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="11c86-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="11c86-105">Parameters</span></span>

<span data-ttu-id="11c86-106">Nenhum</span><span class="sxs-lookup"><span data-stu-id="11c86-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="11c86-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="11c86-107">Examples</span></span>
<span data-ttu-id="11c86-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="11c86-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="11c86-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="11c86-109">Example 1</span></span>

<span data-ttu-id="11c86-110">O exemplo seguinte faz backup do serviço de autoridade de certificação em um arquivo e salva na pasta AC no diretório de compartilhamento de site:</span><span class="sxs-lookup"><span data-stu-id="11c86-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="11c86-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="11c86-111">Detailed Description</span></span>
<span data-ttu-id="11c86-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="11c86-112"></span></span>

<span data-ttu-id="11c86-113">Backup de autoridade de certificação pode ser útil se você planeja reimplantar um aparelho de conector de nuvem com o mesmo certificado em caso de desastre, ou se você deseja mover o aparelho para novo hardware.</span><span class="sxs-lookup"><span data-stu-id="11c86-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="11c86-114">O comando salva a cópia do serviço de autoridade de certificação de nuvem conector do servidor AD para "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span><span class="sxs-lookup"><span data-stu-id="11c86-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="11c86-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="11c86-115">Input Types</span></span>
<span data-ttu-id="11c86-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="11c86-116"></span></span>

<span data-ttu-id="11c86-p102">Nenhum. O cmdlet Backup-CcCertificationAuthority não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="11c86-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="11c86-119">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="11c86-119">Return Types</span></span>
<span data-ttu-id="11c86-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="11c86-120"></span></span>

<span data-ttu-id="11c86-121">Nenhum </span><span class="sxs-lookup"><span data-stu-id="11c86-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="11c86-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11c86-122">See also</span></span>
<span data-ttu-id="11c86-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="11c86-123"></span></span>

[<span data-ttu-id="11c86-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="11c86-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

