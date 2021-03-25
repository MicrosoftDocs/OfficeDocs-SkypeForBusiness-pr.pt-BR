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
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106507"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="da3b9-103">Configurar a rede para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="da3b9-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="da3b9-104">Depois de [habilitar a transmissão de](enable-skype-meeting-broadcast.md) reunião do Skype, você precisa configurar sua rede.</span><span class="sxs-lookup"><span data-stu-id="da3b9-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="da3b9-105">Faça esta etapa se quiser manter webinars e outras transmissões para pessoas fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="da3b9-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da3b9-106">O Skype for Business Online se aposentará em 31 de julho de 2021, quando o acesso ao serviço terminará.</span><span class="sxs-lookup"><span data-stu-id="da3b9-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="da3b9-107">Incentivamos os clientes a iniciar a atualização para o Microsoft Teams, o cliente principal para comunicações e trabalho em equipe no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da3b9-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="da3b9-108">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="da3b9-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="da3b9-109">Para ignorar essa etapa e, em vez disso, adicionar outra empresa à sua federação para que você possa convidá-los para transmissões, siga as etapas em Permitir que os usuários contatem usuários externos [do Skype for Business.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="da3b9-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="da3b9-110">Etapa 1: Configurar domínios permitidos</span><span class="sxs-lookup"><span data-stu-id="da3b9-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="da3b9-111">Use **um** dos seguintes métodos para configurar domínios permitidos:</span><span class="sxs-lookup"><span data-stu-id="da3b9-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="da3b9-112">**Método 1: Usar o centro de administração**</span><span class="sxs-lookup"><span data-stu-id="da3b9-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="da3b9-113">Vá para o centro de administração e, na nav esquerda, clique em **Configurações** Serviços de  >  **&amp; complementos** e escolha **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="da3b9-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="da3b9-114">Na página **compartilhamento** externo em **Exceções** de domínio, selecione Todos os domínios são **bloqueados,** exceto , e insira os domínios a seguir, separados com uma vírgula (,):</span><span class="sxs-lookup"><span data-stu-id="da3b9-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="da3b9-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="da3b9-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="da3b9-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="da3b9-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="da3b9-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="da3b9-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="da3b9-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="da3b9-118">resources.lync.com</span></span>

3. <span data-ttu-id="da3b9-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="da3b9-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="da3b9-120">**Método 2: use Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="da3b9-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="da3b9-121">No **Menu Iniciar,** clique com o botão direito **do mouse Windows PowerShell** clique em Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="da3b9-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="da3b9-122">Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="da3b9-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="da3b9-123">Etapa 2: Adicionar domínios de Transmissão de Reunião do Skype, URLs e endereços IP</span><span class="sxs-lookup"><span data-stu-id="da3b9-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="da3b9-124">A segunda etapa do processo de instalação é primeiro adicionar domínios necessários e, em seguida, adicionar endereços IP e URLs necessários para que a Transmissão de Reunião do Skype funcione.</span><span class="sxs-lookup"><span data-stu-id="da3b9-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="da3b9-125">**Adicione as URLs e endereços IP necessários** do ponto de extremidade do Skype for Business Online, vendo quais são necessários [aqui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="da3b9-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="da3b9-126">Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas</span><span class="sxs-lookup"><span data-stu-id="da3b9-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="da3b9-127">Se você tiver uma organização do Skype for Business Online e uma implantação local do Lync Server 2010, do Microsoft Lync Server 2013 e do Skype for Business Server 2015 e tiver usuários online e locais, há outras etapas de configuração que você precisará fazer além das acima para permitir que sua organização local se comunique com o Skype for Business Online e permita que todos os usuários insuportem uma Transmissão de Reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="da3b9-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="da3b9-128">Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="da3b9-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="da3b9-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="da3b9-129">Related topics</span></span>

[<span data-ttu-id="da3b9-130">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="da3b9-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="da3b9-131">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="da3b9-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="da3b9-132">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="da3b9-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)