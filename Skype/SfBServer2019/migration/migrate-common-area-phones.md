---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica. Os telefones de área comum não precisam estar conectados a um computador para fornecer a funcionalidade UC (comunicações unificadas) do Skype for Business Server. Após a migração de uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado. Usando o Shell de gerenciamento do Skype for Business Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comum herdados e, em seguida, moverá esses objetos para o pool do Skype for Business Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752703"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="5171f-106">Migrar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="5171f-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="5171f-107">Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica.</span><span class="sxs-lookup"><span data-stu-id="5171f-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="5171f-108">Os telefones de área comum não precisam estar conectados a um computador para fornecer a funcionalidade UC (comunicações unificadas) do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5171f-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="5171f-109">Após a migração de uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado.</span><span class="sxs-lookup"><span data-stu-id="5171f-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="5171f-110">Usando o Shell de gerenciamento do Skype for Business Server, você primeiro recupera todos os objetos de contato associados aos telefones de área comum herdados e move esses objetos para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5171f-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="5171f-111">Migrar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="5171f-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="5171f-112">No servidor front-end do Skype for Business Server 2019, abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5171f-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5171f-113">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5171f-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="5171f-114">Para verificar se todos os objetos de contato foram movidos para o pool do Skype for Business Server 2019, no Shell de gerenciamento do Skype for Business Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5171f-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="5171f-115">Verifique se todos os objetos de contato agora estão associados ao pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5171f-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

