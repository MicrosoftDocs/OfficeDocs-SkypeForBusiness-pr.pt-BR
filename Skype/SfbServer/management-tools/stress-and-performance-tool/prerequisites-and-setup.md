---
title: Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Exigências e pré-requisitos da Ferramenta de Stress and Performance do Skype for Business Server 2015. Como instalar e configurar a Ferramenta de Stress and Performance.
ms.openlocfilehash: f52d92022e09314a8f9467cd939f67b2827cc153
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816170"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="ab4fd-104">Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ab4fd-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="ab4fd-p102">Exigências e pré-requisitos da Ferramenta de Stress and Performance do Skype for Business Server 2015. Como instalar e configurar a Ferramenta de Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-p102">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool. How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ab4fd-107">Antes de executar a Ferramenta de Stress and Performance, saiba quais são os requisitos de hardware, software e configuração do sistema lendo as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="ab4fd-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="ab4fd-108">Requisitos de hardware do cliente</span><span class="sxs-lookup"><span data-stu-id="ab4fd-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="ab4fd-109">Requisitos de software do cliente</span><span class="sxs-lookup"><span data-stu-id="ab4fd-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="ab4fd-110">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="ab4fd-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="ab4fd-111">Além disso, disponibilizamos, abaixo, a seção [Instalação da Ferramenta de Stress and Performance do Skype for Business Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="ab4fd-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="ab4fd-112">Requisitos de hardware do cliente</span><span class="sxs-lookup"><span data-stu-id="ab4fd-112">Client hardware requirements</span></span>
<span data-ttu-id="ab4fd-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4fd-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="ab4fd-114">Quando você executar a Ferramenta de Stress and Performance no Skype for Business Server 2015, estes requisitos de hardware deverão ser atendidos, no mínimo, para cada 4500 usuários em seu teste:</span><span class="sxs-lookup"><span data-stu-id="ab4fd-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="ab4fd-115">Adaptador rede de 1 gigabit</span><span class="sxs-lookup"><span data-stu-id="ab4fd-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="ab4fd-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="ab4fd-116">8 GB RAM</span></span>
    
- <span data-ttu-id="ab4fd-117">2 CPUs dual-core</span><span class="sxs-lookup"><span data-stu-id="ab4fd-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="ab4fd-118">Requisitos de software do cliente</span><span class="sxs-lookup"><span data-stu-id="ab4fd-118">Client software requirements</span></span>
<span data-ttu-id="ab4fd-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4fd-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="ab4fd-120">Os sistemas operacionais compatíveis com a Ferramenta de Stress and Performance são:</span><span class="sxs-lookup"><span data-stu-id="ab4fd-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="ab4fd-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ab4fd-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="ab4fd-122">Windows Server 2008 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="ab4fd-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="ab4fd-123">Além disso, os computadores precisam atender aos seguintes requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="ab4fd-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="ab4fd-124">O Microsoft .NET 4.5 Framework deverá estar instalado.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="ab4fd-125">Baixe a estrutura .NET 4,5 aqui.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- <span data-ttu-id="ab4fd-126">O recurso Experiência desktop deverá estar habilitado no Windows.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="ab4fd-127">O Microsoft Visual C++ 2013 (x64) deverá estar instalado.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="ab4fd-128">Baixe o Visual C++ 2013 aqui</span><span class="sxs-lookup"><span data-stu-id="ab4fd-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- <span data-ttu-id="ab4fd-129">O Skype for Business Server 2015 deverá estar devidamente implantado.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="ab4fd-130">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="ab4fd-130">Configuration requirements</span></span>
<span data-ttu-id="ab4fd-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4fd-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="ab4fd-132">Você precisará dessas configurações adicionais para executar corretamente a Ferramenta de Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="ab4fd-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="ab4fd-133">Você deve fazer logon no servidor como membro do grupo do Domínio ou Administrador Local.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="ab4fd-134">Você não pode instalar a ferramenta de Criação de usuário do Skype for Business Server 2015 (UserProvisioningTool.exe) em um servidor Front End ou Standard Edition no qual as contas de usuários ficarão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="ab4fd-135">Quando a ferramenta Criação de Usuário é executada várias vezes, cada usuário que estiver habilitado para o Microsoft Unified Communications precisa ter um número de telefone exclusivo.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="ab4fd-136">O tamanho do arquivo da página precisa ser gerenciado pelos sistemas ou ter pelo menos 1,5 vez a quantidade de RAM do sistema do computador.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ab4fd-137">Instalação da Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ab4fd-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="ab4fd-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4fd-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="ab4fd-p105">A instalação não poderia ser mais simples. Você precisa executar o arquivo do instalador do Windows, **CapacityPlanningTool.msi**, em cada computador cliente que você utilizará para simular o tráfego de usuários e em um Servidor Front-End em cada pool onde você criará usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="ab4fd-p105">Installing couldn't be simpler. You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="ab4fd-141">Para baixar o. msi, juntamente com os scripts de exemplo mencionados em nossos outros artigos, acesse o link do centro de download: [Skype for Business Server 2015, stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="ab4fd-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

