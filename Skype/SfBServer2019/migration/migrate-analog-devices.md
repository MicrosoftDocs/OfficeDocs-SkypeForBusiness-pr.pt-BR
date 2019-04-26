---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server oferece suporte para dispositivos analógicos. Especificamente, os dispositivos analógicos com suporte são telefones áudio analógicos e máquinas de fax analógicos. Você pode configurar os gateways qualificados para o suporte ao uso de dispositivos analógicos na sua Skype para ambiente de servidor de negócios. Após migrar para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados com os dispositivos analógicos. Use Skype do Shell de gerenciamento do servidor de negócios para o primeiro recuperar todos os objetos associados com os dispositivos analógicos herdados do contato e mova esses objetos para o Skype para Business Server 2019 pool.
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238387"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="cae7a-107">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="cae7a-107">Migrate analog devices</span></span>

<span data-ttu-id="cae7a-108">Skype para Business Server oferece suporte para dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="cae7a-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="cae7a-109">Especificamente, os dispositivos analógicos com suporte são telefones áudio analógicos e máquinas de fax analógicos.</span><span class="sxs-lookup"><span data-stu-id="cae7a-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="cae7a-110">Você pode configurar os gateways qualificados para o suporte ao uso de dispositivos analógicos na sua Skype para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="cae7a-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="cae7a-111">Após migrar para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados com os dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="cae7a-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="cae7a-112">Use Skype do Shell de gerenciamento do servidor de negócios para o primeiro recuperar todos os objetos associados com os dispositivos analógicos herdados do contato e mova esses objetos para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="cae7a-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="cae7a-113">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="cae7a-113">To migrate analog devices</span></span>

1. <span data-ttu-id="cae7a-114">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="cae7a-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="cae7a-115">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="cae7a-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="cae7a-116">Verifique se todos os objetos de contato foram movidos para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="cae7a-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="cae7a-117">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="cae7a-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="cae7a-118">Verifique se todos os objetos de contato estão agora associados com o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="cae7a-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


