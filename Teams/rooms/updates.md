---
title: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: O administrador pode aprender sobre como gerenciar atualizações do Windows e atualizações de recursos do Windows para Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117359"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="23c29-103">Gerenciar atualizações do Windows</span><span class="sxs-lookup"><span data-stu-id="23c29-103">Manage Windows Updates</span></span>

<span data-ttu-id="23c29-104">As Salas do Microsoft Teams são executados no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebem as mesmas versões do sistema operacional e atualizações do Windows como um computador de área de trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="23c29-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="23c29-105">As Atualizações do Windows podem ser gerenciadas conforme discutido nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="23c29-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="23c29-106">Abordagem prática</span><span class="sxs-lookup"><span data-stu-id="23c29-106">Hands-off approach</span></span> 

- <span data-ttu-id="23c29-107">Por padrão, as atualizações são baixadas diretamente do Windows Updates automaticamente e instaladas durante o horário de folga.</span><span class="sxs-lookup"><span data-stu-id="23c29-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="23c29-108">Atualizações não adiáveis instalam o primeiro dia da versão automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23c29-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="23c29-109">Atualizações de qualidade e drivers baixam e instalam o primeiro dia automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23c29-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="23c29-110">Atualizações de recursos.</span><span class="sxs-lookup"><span data-stu-id="23c29-110">Feature Updates.</span></span> <span data-ttu-id="23c29-111">Consulte as anotações a seguir.</span><span class="sxs-lookup"><span data-stu-id="23c29-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="23c29-112">Atualizações do Windows para Empresas (GPO ou Intune)</span><span class="sxs-lookup"><span data-stu-id="23c29-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="23c29-113">[Download do Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb)</span><span class="sxs-lookup"><span data-stu-id="23c29-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="23c29-114">As atualizações são baixadas do Windows Update ou do WSUS, mas com atrasos configurados após a data de lançamento original.</span><span class="sxs-lookup"><span data-stu-id="23c29-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="23c29-115">Você pode usar várias OUs ou políticas filtradas para criar "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais serão instalados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="23c29-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="23c29-116">A confiabilidade e o desempenho podem ser testados em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar as Atualizações do Windows no Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="23c29-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="23c29-117">O WSUS e o Windows Updates para Empresas podem ser configurados ao [mesmo](/windows/deployment/update/waas-integrate-wufb) tempo se você desejar o gerenciamento de largura de banda e o controle que o Windows Updates for Business fornece.</span><span class="sxs-lookup"><span data-stu-id="23c29-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="23c29-118">Atualizações de recursos.</span><span class="sxs-lookup"><span data-stu-id="23c29-118">Feature updates.</span></span> <span data-ttu-id="23c29-119">Consulte as anotações a seguir.</span><span class="sxs-lookup"><span data-stu-id="23c29-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="23c29-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="23c29-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="23c29-121">[Download do WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="23c29-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="23c29-122">Muito parecido com o Windows Update para Empresas, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou toda a implantação.</span><span class="sxs-lookup"><span data-stu-id="23c29-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="23c29-123">Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso.</span><span class="sxs-lookup"><span data-stu-id="23c29-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="23c29-124">Atualizações de recursos.</span><span class="sxs-lookup"><span data-stu-id="23c29-124">Feature updates.</span></span> <span data-ttu-id="23c29-125">Consulte as anotações a seguir.</span><span class="sxs-lookup"><span data-stu-id="23c29-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="23c29-126">Atualizações de recursos</span><span class="sxs-lookup"><span data-stu-id="23c29-126">Feature updates</span></span>

<span data-ttu-id="23c29-127">Ao contrário das atualizações de Qualidade e Não Adiáveis, o Windows 10 "Atualizações de Recursos" (versões principais do sistema operacional) só será instalado depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="23c29-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="23c29-128">Mesmo que a atualização seja lançada no Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou manualmente pressionado, um dispositivo microsoft room Systems não permitirá que a atualização não testada seja instalada.</span><span class="sxs-lookup"><span data-stu-id="23c29-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="23c29-129">As Salas do Microsoft Teams funcionam "in-locar" com uma abordagem prática e não instalarão um Windows Update ou reiniciarão um dispositivo automaticamente para um Windows Update.</span><span class="sxs-lookup"><span data-stu-id="23c29-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="23c29-130">Os sistemas baixam uma atualização e aguardam a próxima reinicialização para instalá-la.</span><span class="sxs-lookup"><span data-stu-id="23c29-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="23c29-131">A menos que alguém o reinicia manualmente, a instalação só acontece na reinicialização automática noturna.</span><span class="sxs-lookup"><span data-stu-id="23c29-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="23c29-132">As Atualizações do Windows devem ser transparentes na sala e a operação normal nunca deve ser interrompida pelas Atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="23c29-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="23c29-133">Se você optar por ingressar em dispositivos de junção de domínio, use o Microsoft Endpoint Configuration Manager ou o WSUS.</span><span class="sxs-lookup"><span data-stu-id="23c29-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="23c29-134">Preste atenção especial a políticas ou ações que resultam em uma atualização de dispositivo ou reinicialização forçada durante o horário comercial.</span><span class="sxs-lookup"><span data-stu-id="23c29-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="23c29-135">Os sistemas em sua implantação não devem ser reiniciados durante o uso ou alerta sobre as Atualizações do Windows pela interface do usuário durante o horário de uso, revise sua configuração se esse comportamento acontecer.</span><span class="sxs-lookup"><span data-stu-id="23c29-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>