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
ms.openlocfilehash: fd0a114bcd434e624937b323fbfa787d252db96ffafb701c3f13ff3a677b7118
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339279"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Baixar e instalar o módulo Teams PowerShell

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> A versão pública Teams do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) mais recente é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento Teams e Skype for Business PowerShell online.


1. Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte Conexão para todos os serviços Microsoft 365 ou [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do skype for business online usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
