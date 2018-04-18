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
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: eafd27bf8ee8d8ae2c533501d50806f7d271b48d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="d2016-103">Configurar a rede para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="d2016-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="d2016-104">Depois de [Habilitar transmissão de reunião Skype](enable-skype-meeting-broadcast.md) transmissão do Skype reunião, você precisa configurar sua rede.</span><span class="sxs-lookup"><span data-stu-id="d2016-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="d2016-105">Execute esta etapa se você deseja reter seminários na Web e outros difusões para pessoas fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d2016-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>
  
<span data-ttu-id="d2016-106">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="d2016-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="d2016-107">Para ignorar esta etapa e, em vez disso, adicione outra empresa à sua federação, portanto, poderá convidá-los para transmissões, siga as etapas em [Permitir que os usuários entrar em contato com o Skype externo para usuários comerciais](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="d2016-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>
  
## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="d2016-108">Etapa 1: Configurar os domínios permitidos</span><span class="sxs-lookup"><span data-stu-id="d2016-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="d2016-109">Use **um** dos métodos a seguir para configurar os domínios permitidos:</span><span class="sxs-lookup"><span data-stu-id="d2016-109">Use **one** of the following methods to set up allowed domains:</span></span>
  
### 

 <span data-ttu-id="d2016-110">**Método 1: Usar o Centro de administração do Office 365**</span><span class="sxs-lookup"><span data-stu-id="d2016-110">**Method 1: Use the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="d2016-111">Vá para o **Centro de administração do Office 365** e, em seguida, no painel de navegação esquerdo, clique em **configurações** > **serviços &amp; suplementos**e escolha **Skype para negócios**.</span><span class="sxs-lookup"><span data-stu-id="d2016-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>
    
2. <span data-ttu-id="d2016-112">Na página **compartilhamento externo** em **exceções de domínio**, selecione **todos os domínios são bloqueados, exceto**e insira os seguintes domínios, separados-os com uma vírgula (,):</span><span class="sxs-lookup"><span data-stu-id="d2016-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>
    
  - <span data-ttu-id="d2016-113">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="d2016-113">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="d2016-114">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="d2016-114">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="d2016-115">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="d2016-115">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="d2016-116">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="d2016-116">resources.lync.com</span></span>
    
3. <span data-ttu-id="d2016-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2016-117">Click **Save**.</span></span>
    
### 

 <span data-ttu-id="d2016-118">**Método 2: Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d2016-118">**Method 2: Use Windows PowerShell**</span></span>
  
- <span data-ttu-id="d2016-119">No **Menu Iniciar**, clique com botão direito **Do Windows PowerShell** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d2016-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="d2016-120">Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="d2016-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="d2016-121">Etapa 2: Adicionar domínios, URLs e IP transmissão do Skype reunião endereços</span><span class="sxs-lookup"><span data-stu-id="d2016-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="d2016-122">A segunda etapa no processo de instalação é primeiro adicionar domínios que são necessários e, em seguida, adicionar endereços IP e URLs que são necessários para a transmissão de reunião Skype trabalhar.</span><span class="sxs-lookup"><span data-stu-id="d2016-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>
  
- <span data-ttu-id="d2016-123">**Adicionar o Skype necessário para Business Online URLs de ponto de extremidade e endereços IP verificando quais são necessários** [aqui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="d2016-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required**[here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="d2016-124">Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas</span><span class="sxs-lookup"><span data-stu-id="d2016-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="d2016-125">Se você tiver um Skype para a organização Business Online e uma implantação local do Lync Server 2010, Microsoft Lync Server 2013 e Skype para Business Server 2015 e ambos os usuários online e no local, há outras etapas de instalação que você precisará fazer em adição àquelas acima para permitir que sua organização local para se comunicar com Skype para Business Online e permitir que todos os usuários possam criar e ingressar em uma reunião do Skype transmissão.</span><span class="sxs-lookup"><span data-stu-id="d2016-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="d2016-126">Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="d2016-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d2016-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d2016-127">Related topics</span></span>

[<span data-ttu-id="d2016-128">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="d2016-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)
  
[<span data-ttu-id="d2016-129">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="d2016-129">Office 365 URLs and IP address ranges</span></span>](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="d2016-130">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d2016-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
  
 
