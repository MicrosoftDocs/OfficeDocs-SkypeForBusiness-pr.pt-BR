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
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="a5253-103">Instalar usando o MSI Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5253-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="a5253-104">Para aproveitar o System Center Configuration Manager ou política de grupo ou qualquer 3º mecanismos de distribuição de terceiros para implantação em larga escala, a Microsoft forneceu arquivos MSI ( [32 bits](http://aka.ms/teams32bitmsi) e [64 bits](http://aka.ms/teams64bitmsi)) para os administradores aproveitar durante a implantação em massa da Microsoft Teams para selecionar usuários ou máquinas.</span><span class="sxs-lookup"><span data-stu-id="a5253-104">To leverage System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) for admins to leverage during bulk deployment of Microsoft Teams to select users or machines.</span></span> <span data-ttu-id="a5253-105">Os administradores podem usar esses arquivos para implantar remotamente equipes para que os usuários não precisam baixar manualmente o aplicativo de equipes.</span><span class="sxs-lookup"><span data-stu-id="a5253-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="a5253-106">Quando implantado, equipes gerará automaticamente lançamento para todos os usuários que entrar nesta máquina.</span><span class="sxs-lookup"><span data-stu-id="a5253-106">When deployed, Teams will auto launch for all users who sign-in on that machine.</span></span> <span data-ttu-id="a5253-107">É recomendável que você implante o pacote para a máquina, para que todos os novos usuários para as máquinas também serão beneficiados com essa implantação.</span><span class="sxs-lookup"><span data-stu-id="a5253-107">It is recommended that you deploy the package to the machine, so all new users to the machines will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="a5253-108">Para saber mais sobre SCCM, consulte.</span><span class="sxs-lookup"><span data-stu-id="a5253-108">To learn more about SCCM, see.</span></span> [<span data-ttu-id="a5253-109">Introdução para o System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a5253-109">Introduction to System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a><span data-ttu-id="a5253-110">Procedimento de implantação (recomendações)</span><span class="sxs-lookup"><span data-stu-id="a5253-110">Deployment Procedure (Recommendations)</span></span>
1. <span data-ttu-id="a5253-111">Recuperar o último pacote</span><span class="sxs-lookup"><span data-stu-id="a5253-111">Retrieve the latest package</span></span>
2. <span data-ttu-id="a5253-112">Use os padrões pré-preenchido pelo MSI</span><span class="sxs-lookup"><span data-stu-id="a5253-112">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="a5253-113">Implantar máquinas quando possível</span><span class="sxs-lookup"><span data-stu-id="a5253-113">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="a5253-114">Como funciona ao pacote MSI de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5253-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="a5253-115">O MSI equipes colocará um instalador em arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="a5253-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="a5253-116">Sempre que um usuário se conecta em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo de equipes será instalada na pasta de appdata desse usuário.</span><span class="sxs-lookup"><span data-stu-id="a5253-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="a5253-117">Se um usuário já tiver o aplicativo de equipes instalado na pasta appdata, o instalador MSI irá ignorar o processo para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="a5253-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="a5253-118">Não utilizam o MSI para implantar atualizações, o cliente irá atualizar automaticamente quando detecta que uma nova versão é disponibilizada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="a5253-118">Do not leverage the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="a5253-119">Para reimplantar o instalador mais recente use o processo de reimplantando MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="a5253-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="a5253-120">Se você implantar uma versão mais antiga do pacote do MSI, o cliente será atualizado automaticamente sempre que possível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="a5253-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="a5253-121">Se uma versão antiga muito obtém implantada, o MSI irá disparar uma atualização do aplicativo antes que o usuário seja capaz de usar equipes.</span><span class="sxs-lookup"><span data-stu-id="a5253-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="a5253-122">Não é recomendável que você alterar qualquer localizações de instalação, como isso o fluxo de atualização pode ser desfeito.</span><span class="sxs-lookup"><span data-stu-id="a5253-122">It's not recommended you change any install locations as this could break the update flow.</span></span> <span data-ttu-id="a5253-123">Que então eventualmente bloqueará os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="a5253-123">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="a5253-124">Requisitos de máquina de destino:</span><span class="sxs-lookup"><span data-stu-id="a5253-124">Target machine requirements:</span></span>

1. <span data-ttu-id="a5253-125">.NET framework 4.5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="a5253-125">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="a5253-126">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="a5253-126">Windows 7 or later</span></span>
2. <span data-ttu-id="a5253-127">32GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="a5253-127">32GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-upredeployment-procedure"></a><span data-ttu-id="a5253-128">Limpar up\redeployment procedimento</span><span class="sxs-lookup"><span data-stu-id="a5253-128">Clean up\redeployment Procedure</span></span>
<span data-ttu-id="a5253-129">Se um usuário desinstala equipes a partir do seu perfil de usuário, o instalador MSI irá controlar que o usuário tiver desinstalado o aplicativo de equipes e não são mais instalar equipes para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="a5253-129">If a user uninstalls Teams from for their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="a5253-130">Para reimplantar equipes para esse usuário em uma máquina específica, onde ele foi desinstalado, você precisará:</span><span class="sxs-lookup"><span data-stu-id="a5253-130">To redeploy Teams for this user on a particular machine where it was uninstalled you will need to:</span></span>

1. <span data-ttu-id="a5253-131">Desinstalar o aplicativo de equipes instalado para cada perfil de usuário</span><span class="sxs-lookup"><span data-stu-id="a5253-131">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="a5253-132">Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\\</span><span class="sxs-lookup"><span data-stu-id="a5253-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="a5253-133">Reimplantar o pacote MSI àquela máquina específica</span><span class="sxs-lookup"><span data-stu-id="a5253-133">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="a5253-134">Você pode aproveitar o nosso script de [implantação de equipes da Microsoft limpar](.\scripts\Powershell-script-teams-deployment-clean-up.md) para realizar esta etapa 1 e 2 por meio do SCCM.</span><span class="sxs-lookup"><span data-stu-id="a5253-134">You can leverage our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish this steps 1 and 2 via SCCM.</span></span>                                

