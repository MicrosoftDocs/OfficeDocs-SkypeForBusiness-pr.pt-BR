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
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 95ad00be416a53e6e861ce4e9f235bded8e8075a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990976"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="dbb7a-103">Configurar a rede para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="dbb7a-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="dbb7a-104">Depois de habilitar a transmissão de [reunião do Skype](enable-skype-meeting-broadcast.md) para a transmissão de reunião do Skype, você precisa configurar sua rede.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="dbb7a-105">Siga este procedimento se quiser manter o webinars e outras difusões para pessoas de fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="dbb7a-106">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="dbb7a-107">Para ignorar esta etapa e adicionar outra empresa à sua Federação para poder convidá-las para difusões, siga as etapas em [permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="dbb7a-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="dbb7a-108">Etapa 1: configurar domínios permitidos</span><span class="sxs-lookup"><span data-stu-id="dbb7a-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="dbb7a-109">Use **um** dos seguintes métodos para configurar os domínios permitidos:</span><span class="sxs-lookup"><span data-stu-id="dbb7a-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="dbb7a-110">**Método 1: usar o centro de administração**</span><span class="sxs-lookup"><span data-stu-id="dbb7a-110">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="dbb7a-111">Vá para o centro de administração e, em seguida, na barra de navegação à esquerda, clique em **configurações** > de**Serviços &amp; e suplementos**e, em seguida, escolha **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-111">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="dbb7a-112">Na página **compartilhamento externo** em **exceções de domínio**, selecione **todos os domínios estão bloqueados, exceto**e insira os seguintes domínios, separados por uma vírgula (,):</span><span class="sxs-lookup"><span data-stu-id="dbb7a-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="dbb7a-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dbb7a-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="dbb7a-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dbb7a-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="dbb7a-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dbb7a-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="dbb7a-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="dbb7a-116">resources.lync.com</span></span>

3. <span data-ttu-id="dbb7a-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="dbb7a-118">**Método 2: usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dbb7a-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="dbb7a-119">No **menu iniciar**, clique com o botão direito do mouse em **Windows PowerShell** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="dbb7a-120">Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="dbb7a-121">Etapa 2: adicionar domínios de transmissão de reunião do Skype, URLs e endereços IP</span><span class="sxs-lookup"><span data-stu-id="dbb7a-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="dbb7a-122">A segunda etapa no processo de instalação é para você primeiro adicionar domínios que são necessários e adicionar endereços IP e URLs necessários para que a transmissão de reunião do Skype funcione.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="dbb7a-123">**Adicione as URLs e os endereços IP do ponto de extremidade do Skype for Business online necessários vendo quais são necessários** [aqui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="dbb7a-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="dbb7a-124">Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas</span><span class="sxs-lookup"><span data-stu-id="dbb7a-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="dbb7a-125">Se você tiver uma organização do Skype for Business Online e uma implantação local do Lync Server 2010, do Microsoft Lync Server 2013 e do Skype for Business Server 2015 e tiver usuários online e local, há outras etapas de configuração que serão necessárias adição aos itens acima para permitir que sua organização local se comunique com o Skype for Business Online e permita que todos os usuários ingressem em uma transmissão de reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="dbb7a-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="dbb7a-126">Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="dbb7a-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbb7a-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dbb7a-127">Related topics</span></span>

[<span data-ttu-id="dbb7a-128">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="dbb7a-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="dbb7a-129">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="dbb7a-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="dbb7a-130">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="dbb7a-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



