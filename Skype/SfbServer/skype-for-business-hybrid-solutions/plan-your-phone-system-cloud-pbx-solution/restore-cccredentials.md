---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824237"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="f7563-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="f7563-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="f7563-104">O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="f7563-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="f7563-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 2,1.</span><span class="sxs-lookup"><span data-stu-id="f7563-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="f7563-106">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="f7563-106">Detailed Description</span></span>

<span data-ttu-id="f7563-107">O cmdlet Restore-CcCredentials limpa todas as credenciais e solicita que você insira novamente todas as credenciais usadas para a implantação atual do Skype for Business Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f7563-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f7563-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f7563-108">Parameters</span></span>

<span data-ttu-id="f7563-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7563-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f7563-110">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f7563-110">Input Types</span></span>

<span data-ttu-id="f7563-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f7563-111">None.</span></span> <span data-ttu-id="f7563-112">O cmdlet Restore-CcCredentials não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="f7563-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f7563-113">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="f7563-113">Return Types</span></span>

<span data-ttu-id="f7563-114">Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f7563-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="f7563-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f7563-115">Example</span></span>

<span data-ttu-id="f7563-116">O exemplo a seguir restaura todas as credenciais da implantação do conector de nuvem atual:</span><span class="sxs-lookup"><span data-stu-id="f7563-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="f7563-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f7563-117">See also</span></span>

[<span data-ttu-id="f7563-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="f7563-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="f7563-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="f7563-119">Set-CcCredential</span></span>](set-cccredential.md)
  

