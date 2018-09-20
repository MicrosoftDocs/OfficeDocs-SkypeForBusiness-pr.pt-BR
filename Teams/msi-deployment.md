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
ms.openlocfilehash: 7aaf355c1f1fc65855c7bffb7c5632929a084b88
ms.sourcegitcommit: 3a7d2131717327d9b2d16848758e31e10326a0bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2018
ms.locfileid: "24057599"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="bc880-103">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="bc880-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="bc880-104">Para usar o System Center Configuration Manager ou política de grupo ou qualquer mecanismos de distribuição de terceiros para implantação em larga escala, a Microsoft forneceu arquivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa de equipes para selecionar os usuários ou computadores.</span><span class="sxs-lookup"><span data-stu-id="bc880-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="bc880-105">Os administradores podem usar esses arquivos para implantar remotamente equipes para que os usuários não precisam baixar manualmente o aplicativo de equipes.</span><span class="sxs-lookup"><span data-stu-id="bc880-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="bc880-106">Quando implantado, equipes gerará automaticamente lançamento para todos os usuários que entram nesta máquina.</span><span class="sxs-lookup"><span data-stu-id="bc880-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="bc880-107">(É possível desabilitar depois de instalar o aplicativo de início automático.</span><span class="sxs-lookup"><span data-stu-id="bc880-107">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="bc880-108">[Veja abaixo](#disable-auto-lanuch-for-the-msi-installer).) Recomendamos que você implante o pacote para o computador, para que todos os novos usuários do computador também serão beneficiados com essa implantação.</span><span class="sxs-lookup"><span data-stu-id="bc880-108">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="bc880-109">Para saber mais sobre SCCM, consulte [Introdução para o System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="bc880-109">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="bc880-110">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="bc880-110">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="bc880-111">Recupere o pacote mais recente.</span><span class="sxs-lookup"><span data-stu-id="bc880-111">Retrieve the latest package.</span></span>
2. <span data-ttu-id="bc880-112">Use os padrões pré-preenchido pelo MSI.</span><span class="sxs-lookup"><span data-stu-id="bc880-112">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="bc880-113">Implante em computadores quando possível.</span><span class="sxs-lookup"><span data-stu-id="bc880-113">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="bc880-114">Como funciona ao pacote MSI de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc880-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="bc880-115">O MSI equipes colocará um instalador em arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="bc880-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="bc880-116">Sempre que um usuário se conecta em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo equipes será instalada na pasta de appdata desse usuário.</span><span class="sxs-lookup"><span data-stu-id="bc880-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="bc880-117">Se um usuário já tiver o aplicativo de equipes instalado na pasta appdata, o instalador MSI irá ignorar o processo para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="bc880-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="bc880-118">Não use o MSI para implantar atualizações, pois o cliente irá atualizar automaticamente quando detecta que uma nova versão é disponibilizada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="bc880-118">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="bc880-119">Para reimplantar o instalador mais recente use o processo de reimplantando MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="bc880-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="bc880-120">Se você implantar uma versão mais antiga do pacote do MSI, o cliente será atualizado automaticamente sempre que possível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="bc880-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="bc880-121">Se uma versão antiga muito obtém implantada, o MSI irá disparar uma atualização do aplicativo antes que o usuário seja capaz de usar equipes.</span><span class="sxs-lookup"><span data-stu-id="bc880-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="bc880-122">Não recomendamos que você altere os locais de instalação padrão, como isso poderia quebrará o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="bc880-122">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="bc880-123">Ter uma versão antiga muito eventualmente bloqueará os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="bc880-123">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="bc880-124">Requisitos do computador de destino</span><span class="sxs-lookup"><span data-stu-id="bc880-124">Target computer requirements</span></span>

- <span data-ttu-id="bc880-125">.NET framework 4.5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="bc880-125">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="bc880-126">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="bc880-126">Windows 7 or later</span></span>
- <span data-ttu-id="bc880-127">3 GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="bc880-127">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="bc880-128">Limpeza e o procedimento de reimplantação</span><span class="sxs-lookup"><span data-stu-id="bc880-128">Clean up and redeployment procedure</span></span>
<span data-ttu-id="bc880-129">Se um usuário desinstala equipes de seu perfil de usuário, o instalador MSI irá controlar que o usuário tiver desinstalado o aplicativo de equipes e não são mais instalar equipes para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="bc880-129">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="bc880-130">Para reimplantar equipes para esse usuário em um computador particular, onde ele foi desinstalado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc880-130">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="bc880-131">Desinstale o aplicativo de equipes instalado para cada perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="bc880-131">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="bc880-132">Após a desinstalação, exclua o diretório recursivamente em % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="bc880-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="bc880-133">Reimplante o pacote MSI nesse computador específico.</span><span class="sxs-lookup"><span data-stu-id="bc880-133">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="bc880-134">Você pode usar o nosso script de [implantação de equipes da Microsoft limpar](.\scripts\Powershell-script-teams-deployment-clean-up.md) para realizar as etapas 1 e 2 por meio do SCCM.</span><span class="sxs-lookup"><span data-stu-id="bc880-134">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>  
                    
## <a name="disable-auto-lanuch-for-the-msi-installer"></a><span data-ttu-id="bc880-135">Desabilitar lanuch automático para o instalador MSI</span><span class="sxs-lookup"><span data-stu-id="bc880-135">Disable auto lanuch for the MSI installer</span></span>

<span data-ttu-id="bc880-136">Se você deseja desabilitar o recurso de início automático, insira o seguinte prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="bc880-136">If you want to disable auto launch, enter the following command prompt:</span></span>

`msiexec /i Teams_windows.exe OPTIONS="noAutoStart=false"`

