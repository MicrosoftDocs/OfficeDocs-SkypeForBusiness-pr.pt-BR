---
title: Instalar usando o MSI Teams da Microsoft
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Os administradores podem usar o MSI equipes para em massa implantar Teams da Microsoft para selecionar usuários ou computadores.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a2031a567b96db6987c6c9c035631f17fd3d03f
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="8175a-103">Instalar usando o MSI Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8175a-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="8175a-104">Para usar o System Center Configuration Manager ou política de grupo ou qualquer 3º mecanismos de distribuição de terceiros para implantação em larga escala, a Microsoft forneceu arquivos MSI ( [32 bits](http://aka.ms/teams32bitmsi) e [64 bits](http://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa de equipes para selecionar os usuários ou máquinas.</span><span class="sxs-lookup"><span data-stu-id="8175a-104">To use System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or machines.</span></span> <span data-ttu-id="8175a-105">Os administradores podem usar esses arquivos para implantar remotamente equipes para que os usuários não precisam baixar manualmente o aplicativo de equipes.</span><span class="sxs-lookup"><span data-stu-id="8175a-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="8175a-106">Quando implantado, equipes gerará automaticamente lançamento para todos os usuários que entram nesta máquina.</span><span class="sxs-lookup"><span data-stu-id="8175a-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="8175a-107">Recomendamos que você implante o pacote para a máquina, para que todos os novos usuários do computador também serão beneficiados com essa implantação.</span><span class="sxs-lookup"><span data-stu-id="8175a-107">We recommend that you deploy the package to the machine, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="8175a-108">Para saber mais sobre SCCM, consulte [Introdução para o System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="8175a-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="8175a-109">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="8175a-109">Deployment Procedure (Recommended)</span></span>
1. <span data-ttu-id="8175a-110">Recuperar o último pacote</span><span class="sxs-lookup"><span data-stu-id="8175a-110">Retrieve the latest package</span></span>
2. <span data-ttu-id="8175a-111">Use os padrões pré-preenchido pelo MSI</span><span class="sxs-lookup"><span data-stu-id="8175a-111">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="8175a-112">Implantar máquinas quando possível</span><span class="sxs-lookup"><span data-stu-id="8175a-112">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="8175a-113">Como funciona ao pacote MSI de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8175a-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="8175a-114">O MSI equipes colocará um instalador em arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="8175a-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="8175a-115">Sempre que um usuário se conecta em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo equipes será instalada na pasta de appdata desse usuário.</span><span class="sxs-lookup"><span data-stu-id="8175a-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="8175a-116">Se um usuário já tiver o aplicativo de equipes instalado na pasta appdata, o instalador MSI irá ignorar o processo para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="8175a-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="8175a-117">Não use o MSI para implantar as atualizações, o cliente irá atualizar automaticamente quando detecta que uma nova versão é disponibilizada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="8175a-117">Do not use the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="8175a-118">Para reimplantar o instalador mais recente use o processo de reimplantando MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="8175a-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="8175a-119">Se você implantar uma versão mais antiga do pacote do MSI, o cliente será atualizado automaticamente sempre que possível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="8175a-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="8175a-120">Se uma versão antiga muito obtém implantada, o MSI irá disparar uma atualização do aplicativo antes que o usuário seja capaz de usar equipes.</span><span class="sxs-lookup"><span data-stu-id="8175a-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="8175a-121">Não recomendamos que você altere os locais de instalação padrão, como isso poderia quebrará o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="8175a-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="8175a-122">Que então eventualmente bloqueará os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="8175a-122">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="8175a-123">Requisitos de máquina de destino</span><span class="sxs-lookup"><span data-stu-id="8175a-123">Target machine requirements</span></span>

1. <span data-ttu-id="8175a-124">.NET framework 4.5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8175a-124">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="8175a-125">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8175a-125">Windows 7 or later</span></span>
2. <span data-ttu-id="8175a-126">3GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="8175a-126">3GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="8175a-127">Limpar up e reimplantação procedimento</span><span class="sxs-lookup"><span data-stu-id="8175a-127">Clean up and redeployment Procedure</span></span>
<span data-ttu-id="8175a-128">Se um usuário desinstala equipes de seu perfil de usuário, o instalador MSI irá controlar que o usuário tiver desinstalado o aplicativo de equipes e não são mais instalar equipes para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="8175a-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="8175a-129">Para reimplantar equipes para esse usuário em uma máquina específica, onde ele foi desinstalado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8175a-129">To redeploy Teams for this user on a particular machine where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="8175a-130">Desinstalar o aplicativo de equipes instalado para cada perfil de usuário</span><span class="sxs-lookup"><span data-stu-id="8175a-130">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="8175a-131">Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\\</span><span class="sxs-lookup"><span data-stu-id="8175a-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="8175a-132">Reimplantar o pacote MSI àquela máquina específica</span><span class="sxs-lookup"><span data-stu-id="8175a-132">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="8175a-133">Você pode usar o nosso script de [implantação de equipes da Microsoft limpar](.\scripts\Powershell-script-teams-deployment-clean-up.md) para realizar as etapas 1 e 2 por meio do SCCM.</span><span class="sxs-lookup"><span data-stu-id="8175a-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

