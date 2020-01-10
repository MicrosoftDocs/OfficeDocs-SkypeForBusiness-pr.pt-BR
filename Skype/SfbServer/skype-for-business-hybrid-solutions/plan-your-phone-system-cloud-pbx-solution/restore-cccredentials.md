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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003241"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="ce16b-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="ce16b-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="ce16b-104">O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="ce16b-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="ce16b-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 2,1.</span><span class="sxs-lookup"><span data-stu-id="ce16b-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="ce16b-106">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="ce16b-106">Detailed Description</span></span>

<span data-ttu-id="ce16b-107">O cmdlet Restore-CcCredentials limpa todas as credenciais e solicita que você insira novamente todas as credenciais usadas para a implantação atual do Skype for Business Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ce16b-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ce16b-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ce16b-108">Parameters</span></span>

<span data-ttu-id="ce16b-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ce16b-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ce16b-110">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ce16b-110">Input Types</span></span>

<span data-ttu-id="ce16b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ce16b-111">None.</span></span> <span data-ttu-id="ce16b-112">O cmdlet Restore-CcCredentials não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="ce16b-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ce16b-113">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="ce16b-113">Return Types</span></span>

<span data-ttu-id="ce16b-114">Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ce16b-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="ce16b-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ce16b-115">Example</span></span>

<span data-ttu-id="ce16b-116">O exemplo a seguir restaura todas as credenciais da implantação do conector de nuvem atual:</span><span class="sxs-lookup"><span data-stu-id="ce16b-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="ce16b-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ce16b-117">See also</span></span>

[<span data-ttu-id="ce16b-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="ce16b-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="ce16b-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="ce16b-119">Set-CcCredential</span></span>](set-cccredential.md)
  

