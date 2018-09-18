---
title: Instalar o Microsoft Teams usando MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Os administradores podem usar o Teams MSI para implantar em massa o Microsoft Teams para usuários ou computadores selecionados.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882034"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="5b904-103">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="5b904-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="5b904-104">Para usar o System Center Configuration Manager, a Política de Grupo ou qualquer mecanismo de distribuição de terceiros para ampla implantação, a Microsoft oferece arquivos MSI (de [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa do Teams para usuários ou computadores selecionados.</span><span class="sxs-lookup"><span data-stu-id="5b904-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="5b904-105">Os administradores podem usar esses arquivos para implantar o Teams remotamente, de modo que os usuários não precisem baixar manualmente o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="5b904-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="5b904-106">Quando implantado, o Teams iniciará automaticamente para todos os usuários que fizerem login naquela máquina.</span><span class="sxs-lookup"><span data-stu-id="5b904-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="5b904-107">Recomendamos a implantação do pacote no computador para que todos os novos usuários da máquina também se beneficiem da implantação.</span><span class="sxs-lookup"><span data-stu-id="5b904-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="5b904-108">Para saber mais sobre o SCCM, consulte [Introdução ao System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="5b904-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="5b904-109">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="5b904-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="5b904-110">Recupere o pacote mais recente.</span><span class="sxs-lookup"><span data-stu-id="5b904-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="5b904-111">Use os padrões pré-preenchidos pelo MSI.</span><span class="sxs-lookup"><span data-stu-id="5b904-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="5b904-112">Implante nos computadores quando possível.</span><span class="sxs-lookup"><span data-stu-id="5b904-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="5b904-113">Como o pacote Microsoft Teams MSI funciona</span><span class="sxs-lookup"><span data-stu-id="5b904-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="5b904-114">O Teams MSI colocará um instalador em Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="5b904-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="5b904-115">Sempre que um usuário fizer login em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo Teams será instalada na pasta appdata desse usuário.</span><span class="sxs-lookup"><span data-stu-id="5b904-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="5b904-116">Se o usuário já tiver o aplicativo Teams instalado na pasta appdata, o instalador do MSI ignorará o processo para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="5b904-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="5b904-117">Não use o MSI para implantar atualizações, pois o cliente atualizará automaticamente quando detectar que há uma nova versão disponível no serviço.</span><span class="sxs-lookup"><span data-stu-id="5b904-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="5b904-118">Para reimplantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="5b904-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="5b904-119">Se você implantar uma versão mais antiga do pacote MSI, o cliente atualizará automaticamente para o usuário quando possível.</span><span class="sxs-lookup"><span data-stu-id="5b904-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="5b904-120">Se for implantada uma versão muito antiga, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams.</span><span class="sxs-lookup"><span data-stu-id="5b904-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="5b904-121">Não recomendamos mudar os locais de instalação padrão, pois isso pode interromper o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="5b904-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="5b904-122">Uma versão muito antiga pode impedir que os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="5b904-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="5b904-123">Requisitos do computador de destino</span><span class="sxs-lookup"><span data-stu-id="5b904-123">Target computer requirements</span></span>

- <span data-ttu-id="5b904-124">.NET framework 4.5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="5b904-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="5b904-125">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="5b904-125">Windows 7 or later</span></span>
- <span data-ttu-id="5b904-126">3 GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="5b904-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="5b904-127">Procedimento de limpeza e reimplantação</span><span class="sxs-lookup"><span data-stu-id="5b904-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="5b904-128">Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI rastreará que o usuário desinstalou o aplicativo Teams e não instalará mais o Teams para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="5b904-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="5b904-129">Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b904-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="5b904-130">Desinstale o aplicativo Teams instalado para todos os perfis de usuário.</span><span class="sxs-lookup"><span data-stu-id="5b904-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="5b904-131">Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="5b904-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="5b904-132">Reimplante o pacote MSI no computador específico.</span><span class="sxs-lookup"><span data-stu-id="5b904-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="5b904-133">Você pode usar nosso [Script de limpeza de implantação do Microsoft Teams](.\scripts\Powershell-script-teams-deployment-clean-up.md) via SCCM para concluir as etapas 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="5b904-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

