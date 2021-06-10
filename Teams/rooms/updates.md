---
title: Gerenciar Windows atualizações para Salas do Microsoft Teams
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
description: O administrador pode aprender sobre como gerenciar Windows atualizações e Windows de recursos para Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117359"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="55ae2-103">Gerenciar Windows atualizações</span><span class="sxs-lookup"><span data-stu-id="55ae2-103">Manage Windows Updates</span></span>

<span data-ttu-id="55ae2-104">Salas do Microsoft Teams é executado em Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe as mesmas Windows atualizações e builds do sistema operacional como um computador de área de trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="55ae2-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="55ae2-105">Windows As atualizações podem ser gerenciadas conforme discutido nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="55ae2-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="55ae2-106">Abordagem prática</span><span class="sxs-lookup"><span data-stu-id="55ae2-106">Hands-off approach</span></span> 

- <span data-ttu-id="55ae2-107">Por padrão, as atualizações são baixadas diretamente Windows atualizações automaticamente e instaladas durante o horário de folga.</span><span class="sxs-lookup"><span data-stu-id="55ae2-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="55ae2-108">Atualizações não adiáveis instalam o primeiro dia da versão automaticamente.</span><span class="sxs-lookup"><span data-stu-id="55ae2-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="55ae2-109">Atualizações de qualidade e drivers baixam e instalam o primeiro dia automaticamente.</span><span class="sxs-lookup"><span data-stu-id="55ae2-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="55ae2-110">Atualizações de recursos.</span><span class="sxs-lookup"><span data-stu-id="55ae2-110">Feature Updates.</span></span> <span data-ttu-id="55ae2-111">Consulte as anotações a seguir.</span><span class="sxs-lookup"><span data-stu-id="55ae2-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="55ae2-112">Windows Atualizações para Empresas (GPO ou Intune)</span><span class="sxs-lookup"><span data-stu-id="55ae2-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="55ae2-113">[Windows download de Atualizações para Empresas](/windows/deployment/update/waas-manage-updates-wufb)</span><span class="sxs-lookup"><span data-stu-id="55ae2-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="55ae2-114">As atualizações são baixadas do Windows Update ou do WSUS, mas com atrasos configurados após a data de lançamento original.</span><span class="sxs-lookup"><span data-stu-id="55ae2-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="55ae2-115">Você pode usar várias OUs ou políticas filtradas para criar "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais serão instalados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="55ae2-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="55ae2-116">A confiabilidade e o desempenho podem ser testados em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar Windows atualizações no Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="55ae2-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="55ae2-117">O WSUS e Windows atualizações para [](/windows/deployment/update/waas-integrate-wufb) Empresas podem ser configuradas ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle Windows Atualizações para Empresas fornece.</span><span class="sxs-lookup"><span data-stu-id="55ae2-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="55ae2-118">Atualizações de recursos.</span><span class="sxs-lookup"><span data-stu-id="55ae2-118">Feature updates.</span></span> <span data-ttu-id="55ae2-119">Consulte as anotações a seguir.</span><span class="sxs-lookup"><span data-stu-id="55ae2-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="55ae2-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="55ae2-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="55ae2-121">[Download do WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="55ae2-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="55ae2-122">Assim como Windows Atualizar para Empresas, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou toda a implantação.</span><span class="sxs-lookup"><span data-stu-id="55ae2-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="55ae2-123">Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso.</span><span class="sxs-lookup"><span data-stu-id="55ae2-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="55ae2-124">Atualizações de recursos.</span><span class="sxs-lookup"><span data-stu-id="55ae2-124">Feature updates.</span></span> <span data-ttu-id="55ae2-125">Consulte as anotações a seguir.</span><span class="sxs-lookup"><span data-stu-id="55ae2-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="55ae2-126">Atualizações de recursos</span><span class="sxs-lookup"><span data-stu-id="55ae2-126">Feature updates</span></span>

<span data-ttu-id="55ae2-127">Ao contrário das atualizações de Qualidade e Não Adiáveis, Windows 10 "Atualizações de Recursos" (versões principais do sistema operacional) só serão instaladas depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55ae2-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="55ae2-128">Mesmo que a atualização seja lançada no Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou manualmente pressionado, um dispositivo microsoft room Systems não permitirá que a atualização não testada seja instalada.</span><span class="sxs-lookup"><span data-stu-id="55ae2-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="55ae2-129">Salas do Microsoft Teams funciona "fora da caixa" com uma abordagem prática e não instalará um Windows Update ou reiniciará um dispositivo automaticamente para uma atualização Windows.</span><span class="sxs-lookup"><span data-stu-id="55ae2-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="55ae2-130">Os sistemas baixam uma atualização e aguardam a próxima reinicialização para instalá-la.</span><span class="sxs-lookup"><span data-stu-id="55ae2-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="55ae2-131">A menos que alguém o reinicia manualmente, a instalação só acontece na reinicialização automática noturna.</span><span class="sxs-lookup"><span data-stu-id="55ae2-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="55ae2-132">Windows As atualizações devem ser transparentes na sala e a operação normal nunca deve ser interrompida por Windows Atualizações.</span><span class="sxs-lookup"><span data-stu-id="55ae2-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="55ae2-133">Se você optar por ingressar em dispositivos de domínio, use Microsoft Endpoint Configuration Manager ou WSUS.</span><span class="sxs-lookup"><span data-stu-id="55ae2-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="55ae2-134">Preste atenção especial a políticas ou ações que resultam em uma atualização de dispositivo ou reinicialização forçada durante o horário comercial.</span><span class="sxs-lookup"><span data-stu-id="55ae2-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="55ae2-135">Os sistemas em sua implantação não devem ser reiniciados durante o uso ou alerta sobre Windows atualizações na interface do usuário durante o horário de uso, revise sua configuração se esse comportamento acontecer.</span><span class="sxs-lookup"><span data-stu-id="55ae2-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>