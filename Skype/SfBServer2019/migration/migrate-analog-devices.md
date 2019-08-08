---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O Skype for Business Server oferece suporte a dispositivos analógicos. Especificamente, os dispositivos analógicos suportados são telefones de áudio analógicos e máquinas de fax analógicas. Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos no ambiente do Skype for Business Server. Depois de migrar para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos. Use o Shell de gerenciamento do Skype for Business Server para recuperar primeiro todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mova esses objetos para o pool do Skype for Business Server 2019.
ms.openlocfilehash: 486c49c0ace00b798520ebae939c0c2070a99783
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238036"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="31369-107">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="31369-107">Migrate analog devices</span></span>

<span data-ttu-id="31369-108">O Skype for Business Server oferece suporte a dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="31369-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="31369-109">Especificamente, os dispositivos analógicos suportados são telefones de áudio analógicos e máquinas de fax analógicas.</span><span class="sxs-lookup"><span data-stu-id="31369-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="31369-110">Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos no ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="31369-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="31369-111">Depois de migrar para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="31369-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="31369-112">Use o Shell de gerenciamento do Skype for Business Server para recuperar primeiro todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mova esses objetos para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="31369-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="31369-113">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="31369-113">To migrate analog devices</span></span>

1. <span data-ttu-id="31369-114">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="31369-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="31369-115">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="31369-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="31369-116">Verifique se todos os objetos de contato foram movidos para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="31369-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="31369-117">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="31369-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="31369-118">Verifique se todos os objetos de contato agora estão associados ao pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="31369-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


