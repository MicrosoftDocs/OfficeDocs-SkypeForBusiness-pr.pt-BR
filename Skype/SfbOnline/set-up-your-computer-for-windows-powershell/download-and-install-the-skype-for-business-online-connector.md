---
title: Baixar e instalar o módulo Skype for Business Conector Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Baixe, instale e use o conector Skype for Business Online para criar uma sessão Windows PowerShell remota que se conecta ao Skype for Business Online.
ms.openlocfilehash: e9429b385f83f6b76e211614f953f7d439df524e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238862"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="54821-103">Baixar e instalar o módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="54821-103">Download and install the Teams PowerShell module</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> <span data-ttu-id="54821-104">A versão pública Teams do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) mais recente é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento Teams e Skype for Business PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="54821-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="54821-105">Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="54821-105">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="54821-106">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="54821-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="54821-107">Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte Conexão para todos os serviços Microsoft 365 ou [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="54821-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="54821-108">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="54821-108">Related topics</span></span>
[<span data-ttu-id="54821-109">Configurar seu computador para gerenciamento do skype for business online usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54821-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
