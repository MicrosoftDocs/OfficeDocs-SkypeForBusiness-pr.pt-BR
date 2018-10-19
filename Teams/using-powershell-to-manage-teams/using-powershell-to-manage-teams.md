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
ms.openlocfilehash: 4c8eb0c37f71972bb20fac60706ff7a369d971d4
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678342"
---
# <a name="using-powershell-to-manage-teams"></a>Usando o PowerShell para gerenciar equipes

Recursos em equipes podem ser gerenciados usando o PowerShell ou Microsoft Teams e Skype para centro de administração de negócios. 

> ! [Nota] Nem todos os recursos em equipes podem ser gerenciados usando o módulo do conector de equipes. Você pode precisar usar o Skype para o Business connector. Consulte [Baixe e instale o Skype para conector Business Online](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

### <a name="step-1-prerequisites"></a>Etapa 1: pré-requisitos

Gerenciamento remoto do Microsoft Teams usando o PowerShell tem suporte apenas nos computadores de 64 bits executando um dos seguintes sistemas operacionais:
  
- Windows 10
- Windows 8.1
- Windows 8 
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008
- Windows 7
    
Além de um sistema operacional, o computador também deve estar executando o seguinte:
  
- PowerShell 3.0 ou superior
    
- Módulo de conector equipes do PowerShell


### <a name="step-2-install-powershell-30-or-higher"></a>Etapa 2: Instalar PowerShell 3.0 ou superior
[Use este tópico para obter ajuda](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a>Etapa 3: Baixar e instalar o módulo do conector de equipes
[Use este tópico para obter ajuda](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

Instale o módulo mais recente da Galeria do PowerShell usando: 
  
  Install-Module MicrosoftTeams

Ou, para obter mais informações, o pacote pode ser encontrado aqui:https://www.powershellgallery.com/packages/MicrosoftTeams/

### <a name="step-4-connect-using-the-teams-connector-module"></a>Etapa 4: Conectar usando o módulo do conector de equipes
[Use este tópico para obter ajuda](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a>Tópicos relacionados
- [Gerenciar recursos de equipes com o PowerShell](manage-features-with-powershell.md)
