---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Telefones de área comum são IP telefones que mais frequentemente residirem em um espaço de trabalho compartilhado ou área comum, como um andar lobby, cozinha ou fábrica. Telefones de área comum não precisará ser conectado a um computador para fornecer que funcionalidade de comunicação unificada de Unificação de Skype para Business Server. Após migrar uma implantação para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado. Usando o Skype para Business Server Management Shell você irá primeiro recuperar todos os objetos de contato associados a telefones de área comum herdado e mova esses objetos para o Skype para Business Server 2019 pool.
ms.openlocfilehash: d17e15224a9124eaf3e9fd6696e6ecd9265044eb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231662"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="680b3-106">Migrar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="680b3-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="680b3-107">Telefones de área comum são IP telefones que mais frequentemente residirem em um espaço de trabalho compartilhado ou área comum, como um andar lobby, cozinha ou fábrica.</span><span class="sxs-lookup"><span data-stu-id="680b3-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="680b3-108">Telefones de área comum não precisará ser conectado a um computador para fornecer que funcionalidade de comunicação unificada de Unificação de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="680b3-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="680b3-109">Após migrar uma implantação para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado.</span><span class="sxs-lookup"><span data-stu-id="680b3-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="680b3-110">Usando Skype do Shell de gerenciamento do servidor de negócios, você será primeiro recuperar todos os objetos de contato associados a telefones de área comum herdado e mova esses objetos para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="680b3-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="680b3-111">Migrar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="680b3-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="680b3-112">Em Skype para o servidor de negócios 2019 Front-End Server, abra Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="680b3-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="680b3-113">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="680b3-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="680b3-114">Para verificar se todos os objetos de contato foram movidos para o Skype para Business Server 2019 pool, no Skype do Shell de gerenciamento do servidor de negócios, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="680b3-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="680b3-115">Verifique se todos os objetos de contato estão agora associados com o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="680b3-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

