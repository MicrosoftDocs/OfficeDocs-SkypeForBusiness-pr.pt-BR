---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Os telefones de área comuns são telefones IP que costumam residir em um espaço de trabalho compartilhado ou em uma área comum, como um lobby, uma cozinha ou um chão de fábrica. Os telefones de área comuns não precisam estar conectados a um computador para fornecer a funcionalidade de comunicação unificada do Skype for Business Server. Depois de migrar uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum comum. Usando o Shell de gerenciamento do Skype for Business Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comuns do herdado e, em seguida, moverá esses objetos para o pool do Skype for Business Server 2019.
ms.openlocfilehash: 123f0a73da65e7d661541c6c4bec65481bf12f0c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238022"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="de3fc-106">Migrar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="de3fc-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="de3fc-107">Os telefones de área comuns são telefones IP que costumam residir em um espaço de trabalho compartilhado ou em uma área comum, como um lobby, uma cozinha ou um chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="de3fc-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="de3fc-108">Os telefones de área comuns não precisam estar conectados a um computador para fornecer a funcionalidade de comunicação unificada do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="de3fc-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="de3fc-109">Depois de migrar uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum comum.</span><span class="sxs-lookup"><span data-stu-id="de3fc-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="de3fc-110">Usando o Shell de gerenciamento do Skype for Business Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comuns herdados e, em seguida, moverá esses objetos para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="de3fc-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="de3fc-111">Migrar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="de3fc-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="de3fc-112">No servidor front-end do Skype for Business Server 2019, abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="de3fc-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="de3fc-113">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="de3fc-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="de3fc-114">Para verificar se todos os objetos de contato foram movidos para o pool do Skype for Business Server 2019, no Shell de gerenciamento do Skype for Business Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="de3fc-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="de3fc-115">Verifique se todos os objetos de contato agora estão associados ao pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="de3fc-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

