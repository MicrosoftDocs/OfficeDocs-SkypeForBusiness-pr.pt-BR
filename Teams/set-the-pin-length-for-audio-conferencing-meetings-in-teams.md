---
title: Definir o tamanho do PIN para reuniões de Audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Saiba os parâmetros para o tamanho e os requisitos de um PIN e veja como definir o tamanho das reuniões em Microsoft Teams.
ms.openlocfilehash: 3b50c555121e960ddf350e8c28079552a5589f9f
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537232"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Definir o tamanho do PIN para reuniões de audioconferência no Microsoft Teams

Ao configurar a audioconferência para Microsoft Teams, você receberá uma ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone definido será incluído nos convites de reunião para o Microsoft Teams app.
  
A ponte de audioconferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone. Ele atende o chamador com prompts de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações e pedir que os chamadores gravem seu nome. **As configurações** de ponte da Microsoft permitem alterar as configurações para notificações de reunião e a experiência de junção de reunião e definir o tamanho dos PINs usados pelos organizadores da reunião. Os organizadores da reunião usam PINs para iniciar reuniões se não puderem ingressar na reunião usando o Microsoft Teams app.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar o tamanho do PIN

 **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações de** ponte, em Comprimento **do PIN,** selecione o número de dígitos que você deseja para o PIN.

4. Clique em **Salvar**.

> [!NOTE]
> [!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião. 

## <a name="want-to-know-more-about-pin-settings"></a>Deseja saber mais sobre configurações de PIN?

- PiNs podem ter de 4 a 12 dígitos; o padrão é 5. Somente números são usados para criar PINs. Letras e caracteres especiais não são usados.
    
- Um PIN só é necessário para o organizador da reunião quando um Microsoft Teams usuário ainda não iniciou a reunião. Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.
    
- As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)