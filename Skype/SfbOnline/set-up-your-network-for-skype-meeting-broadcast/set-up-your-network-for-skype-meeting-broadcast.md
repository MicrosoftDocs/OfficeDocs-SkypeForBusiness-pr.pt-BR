---
title: Configurar a rede para a Transmissão de Reunião do Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: da27110313765bb50df92e3bafb6f09ceae5f301
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237547"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="d312a-103">Configurar a rede para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="d312a-103">Set up your network for Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="d312a-104">Depois de [habilitar Reunião do Skype transmissão Reunião do Skype](enable-skype-meeting-broadcast.md) transmissão, você precisará configurar sua rede.</span><span class="sxs-lookup"><span data-stu-id="d312a-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="d312a-105">Faça esta etapa se quiser manter webinars e outras transmissões para pessoas fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d312a-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d312a-106">Skype for Business Online está se retirando em 31 de julho de 2021, quando o acesso ao serviço terminará.</span><span class="sxs-lookup"><span data-stu-id="d312a-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="d312a-107">Incentivamos os clientes a começar a atualização para Microsoft Teams, o cliente principal para comunicações e trabalho em equipe Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d312a-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="d312a-108">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="d312a-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="d312a-109">Para ignorar essa etapa e, em vez disso, adicionar outra empresa à sua federação para que você possa convidá-los para transmissões, siga as etapas em Permitir que os usuários contatem usuários externos Skype for Business [usuários](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="d312a-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="d312a-110">Etapa 1: Configurar domínios permitidos</span><span class="sxs-lookup"><span data-stu-id="d312a-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="d312a-111">Use **um** dos seguintes métodos para configurar domínios permitidos:</span><span class="sxs-lookup"><span data-stu-id="d312a-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="d312a-112">**Método 1: Usar o centro de administração**</span><span class="sxs-lookup"><span data-stu-id="d312a-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="d312a-113">Vá para o centro de administração e, na nav esquerda, clique em Configurações de serviços e escolha  >  **&amp;** **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="d312a-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="d312a-114">Na página **compartilhamento** externo em **Exceções** de domínio, selecione Todos os domínios são **bloqueados,** exceto , e insira os domínios a seguir, separados com uma vírgula (,):</span><span class="sxs-lookup"><span data-stu-id="d312a-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="d312a-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d312a-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="d312a-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d312a-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="d312a-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d312a-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="d312a-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="d312a-118">resources.lync.com</span></span>

3. <span data-ttu-id="d312a-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d312a-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="d312a-120">**Método 2: use Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d312a-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="d312a-121">No **Menu Iniciar,** clique com o botão direito **do mouse Windows PowerShell** clique em Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="d312a-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="d312a-122">Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="d312a-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="d312a-123">Etapa 2: Adicionar Reunião do Skype de transmissão, URLs e endereços IP</span><span class="sxs-lookup"><span data-stu-id="d312a-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="d312a-124">A segunda etapa no processo de instalação é primeiro adicionar domínios necessários e, em seguida, adicionar endereços IP e URLs que são necessárias para que Reunião do Skype Transmissão funcione.</span><span class="sxs-lookup"><span data-stu-id="d312a-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="d312a-125">**Adicione as URLs** e endereços IP do ponto de extremidade Skype for Business online, vendo quais são necessários [aqui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="d312a-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="d312a-126">Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas</span><span class="sxs-lookup"><span data-stu-id="d312a-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="d312a-127">Se você tiver uma organização do Skype for Business Online e uma implantação local do Lync Server 2010, do Microsoft Lync Server 2013 e do Skype for Business Server 2015 e tiver usuários online e no local, há outras etapas de instalação que você precisará fazer além das acima para permitir que sua organização local se comunique com o Skype for Business Online e permitir que todos os usuários insuportem uma transmissão Reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="d312a-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="d312a-128">Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="d312a-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d312a-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d312a-129">Related topics</span></span>

[<span data-ttu-id="d312a-130">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="d312a-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="d312a-131">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="d312a-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="d312a-132">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d312a-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
