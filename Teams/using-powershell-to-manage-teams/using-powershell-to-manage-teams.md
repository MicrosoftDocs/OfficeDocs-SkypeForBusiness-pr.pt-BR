---
title: Usando o PowerShell para gerenciar equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Saiba como usar o Windows PowerShell para gerenciar todos os recursos encontrados no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0daff64e5a0f6f876de4adb7b60d913fbcce78cb
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016073"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="1f041-103">Usando o PowerShell para gerenciar equipes</span><span class="sxs-lookup"><span data-stu-id="1f041-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="1f041-104">Recursos em equipes podem ser gerenciados usando o PowerShell ou Microsoft Teams e Skype para centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="1f041-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="1f041-105">! [Nota] Nem todos os recursos em equipes podem ser gerenciados usando o módulo do conector de equipes.</span><span class="sxs-lookup"><span data-stu-id="1f041-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="1f041-106">Você pode precisar usar o Skype para o Business connector.</span><span class="sxs-lookup"><span data-stu-id="1f041-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="1f041-107">Consulte [Baixe e instale o Skype para conector Business Online](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="1f041-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="1f041-108">Etapa 1: pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1f041-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="1f041-109">Gerenciamento remoto do Microsoft Teams usando o PowerShell tem suporte apenas nos computadores de 64 bits executando um dos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="1f041-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="1f041-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1f041-110">Windows 10</span></span>
- <span data-ttu-id="1f041-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1f041-111">Windows 8.1</span></span>
- <span data-ttu-id="1f041-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1f041-112">Windows 8</span></span> 
- <span data-ttu-id="1f041-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1f041-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="1f041-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1f041-114">Windows Server 2012</span></span>
- <span data-ttu-id="1f041-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="1f041-115">Windows Server 2008</span></span>
- <span data-ttu-id="1f041-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1f041-116">Windows 7</span></span>
    
<span data-ttu-id="1f041-117">Além de um sistema operacional, o computador também deve estar executando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1f041-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="1f041-118">PowerShell 3.0 ou superior</span><span class="sxs-lookup"><span data-stu-id="1f041-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="1f041-119">Módulo de conector equipes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f041-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="1f041-120">Etapa 2: Instalar PowerShell 3.0 ou superior</span><span class="sxs-lookup"><span data-stu-id="1f041-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="1f041-121">Use este tópico para obter ajuda</span><span class="sxs-lookup"><span data-stu-id="1f041-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="1f041-122">Etapa 3: Baixar e instalar o módulo do conector de equipes</span><span class="sxs-lookup"><span data-stu-id="1f041-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="1f041-123">Use este tópico para obter ajuda</span><span class="sxs-lookup"><span data-stu-id="1f041-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="1f041-124">Aqui está o link de download do sabrina:https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="1f041-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="1f041-125">Etapa 4: Conectar usando o módulo do conector de equipes</span><span class="sxs-lookup"><span data-stu-id="1f041-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="1f041-126">Use este tópico para obter ajuda</span><span class="sxs-lookup"><span data-stu-id="1f041-126">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="1f041-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1f041-127">Related topics</span></span>
- [<span data-ttu-id="1f041-128">Gerenciar recursos de equipes com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f041-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)