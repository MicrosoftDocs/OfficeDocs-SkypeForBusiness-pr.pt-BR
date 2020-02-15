---
title: Pré-requisitos e configuração para a ferramenta de estresse e desempenho do Skype for stress
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
description: Requisitos ou pré-requisitos para a ferramenta de estresse e desempenho do Skype for Business Server 2015. Como instalar ou configurar a ferramenta de estresse e desempenho.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005976"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="678e8-104">Pré-requisitos e configuração para a ferramenta de estresse e desempenho do Skype for stress</span><span class="sxs-lookup"><span data-stu-id="678e8-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="678e8-105">Requisitos ou pré-requisitos para a ferramenta de estresse e desempenho do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="678e8-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="678e8-106">Como instalar ou configurar a ferramenta de estresse e desempenho.</span><span class="sxs-lookup"><span data-stu-id="678e8-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="678e8-107">Temos as seguintes seções de requisitos de configuração de hardware, software e sistema que você precisa conhecer antes de executar a ferramenta de estresse e desempenho:</span><span class="sxs-lookup"><span data-stu-id="678e8-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="678e8-108">Requisitos de hardware do cliente</span><span class="sxs-lookup"><span data-stu-id="678e8-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="678e8-109">Requisitos de software do cliente</span><span class="sxs-lookup"><span data-stu-id="678e8-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="678e8-110">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="678e8-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="678e8-111">Além disso, também temos uma seção abaixo para [instalar a ferramenta de estresse e desempenho do Skype for Business Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="678e8-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="678e8-112">Requisitos de hardware do cliente</span><span class="sxs-lookup"><span data-stu-id="678e8-112">Client hardware requirements</span></span>
<span data-ttu-id="678e8-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="678e8-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="678e8-114">Ao executar a ferramenta de estresse e desempenho em relação à implantação do Skype for Business Server 2015, você deverá, no mínimo, atender a todos os requisitos de hardware atendidos para cada 4500 usuários no teste:</span><span class="sxs-lookup"><span data-stu-id="678e8-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="678e8-115">adaptador de rede de 1 Gigabit</span><span class="sxs-lookup"><span data-stu-id="678e8-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="678e8-116">8 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="678e8-116">8 GB RAM</span></span>
    
- <span data-ttu-id="678e8-117">2 CPUs de núcleo dual</span><span class="sxs-lookup"><span data-stu-id="678e8-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="678e8-118">Requisitos de software do cliente</span><span class="sxs-lookup"><span data-stu-id="678e8-118">Client software requirements</span></span>
<span data-ttu-id="678e8-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="678e8-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="678e8-120">Os sistemas operacionais compatíveis com a ferramenta de estresse e desempenho são:</span><span class="sxs-lookup"><span data-stu-id="678e8-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="678e8-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="678e8-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="678e8-122">Windows Server 2008 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="678e8-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="678e8-123">Além disso, os computadores precisam atender aos seguintes requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="678e8-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="678e8-124">Você precisará do Microsoft .NET 4,5 Framework instalado.</span><span class="sxs-lookup"><span data-stu-id="678e8-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="678e8-125">Baixe a estrutura do .NET 4,5 aqui.</span><span class="sxs-lookup"><span data-stu-id="678e8-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="678e8-126">Você precisará do recurso experiência Desktop habilitado no Windows.</span><span class="sxs-lookup"><span data-stu-id="678e8-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="678e8-127">Você precisará do Microsoft Visual C++ 2013 (x64) instalado.</span><span class="sxs-lookup"><span data-stu-id="678e8-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="678e8-128">Baixe o Visual C++ 2013 aqui</span><span class="sxs-lookup"><span data-stu-id="678e8-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="678e8-129">Você precisará do Skype for Business Server 2015 implantado com êxito.</span><span class="sxs-lookup"><span data-stu-id="678e8-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="678e8-130">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="678e8-130">Configuration requirements</span></span>
<span data-ttu-id="678e8-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="678e8-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="678e8-132">Você precisará dessas configurações adicionais para executar a ferramenta de estresse e desempenho com êxito:</span><span class="sxs-lookup"><span data-stu-id="678e8-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="678e8-133">Você precisa fazer logon no servidor como membro do domínio ou do grupo do administrador local.</span><span class="sxs-lookup"><span data-stu-id="678e8-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="678e8-134">Você não pode instalar a ferramenta de criação de usuário do Skype for Business Server 2015 (UserProvisioningTool. exe) em qualquer servidor front-end ou servidor Standard Edition onde as contas de usuário residirão.</span><span class="sxs-lookup"><span data-stu-id="678e8-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="678e8-135">Quando a ferramenta de criação de usuário é executada várias vezes, cada usuário habilitado para o Microsoft Unified Communications precisa ter um número de telefone exclusivo.</span><span class="sxs-lookup"><span data-stu-id="678e8-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="678e8-136">O tamanho do arquivo de paginação deve ser gerenciado por sistemas ou deve ser pelo menos 1,5 vezes a quantidade de RAM no sistema do computador.</span><span class="sxs-lookup"><span data-stu-id="678e8-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="678e8-137">Instalando a ferramenta de estresse e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="678e8-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="678e8-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="678e8-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="678e8-139">A instalação não pôde ser mais simples.</span><span class="sxs-lookup"><span data-stu-id="678e8-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="678e8-140">Você precisa executar o arquivo do Windows Installer, **CapacityPlanningTool. msi**, em cada computador cliente que será usado para simular o tráfego do usuário e em um servidor front-end em cada pool onde você criará usuários e contatos.</span><span class="sxs-lookup"><span data-stu-id="678e8-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="678e8-141">Para baixar o. msi, junto com os exemplos de scripts mencionados em nossos outros artigos, vá para o link do centro de download: [Skype for Business Server 2015, ferramenta de estresse e desempenho](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="678e8-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

