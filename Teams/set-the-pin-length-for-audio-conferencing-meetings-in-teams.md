---
title: Definir o tamanho do PIN para reuniões de Audioconferência no Microsoft Teams
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Aprenda os parâmetros de tamanho e requisitos de um PIN e veja como definir o tamanho das reuniões no Microsoft Teams.
ms.openlocfilehash: 50c6ffe31e673dc7573ebb27f0eeb2ca78a30918
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571266"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Definir o tamanho do PIN para reuniões de Audioconferência no Microsoft Teams

Quando você estiver configurando a audioconferência para o Microsoft Teams, você receberá uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone que você definir será incluído nos convites da reunião para o aplicativo Microsoft Teams.
  
A ponte de audioconferência atende uma chamada feita por uma pessoa que discou para uma reunião utilizando um telefone. Ela atende o chamador com comandos de voz de um atendedor automático e, dependendo das suas configurações, pode reproduzir notificações e pedir para o chamador gravar o nome dele. As **configurações de ponte da Microsoft** permitem que você altere as configurações de notificação da reunião e a experiência de participação da reunião, além de definir o tamanho dos PINs usados pelos organizadores da reunião. Os organizadores da reunião usam PINs para iniciar reuniões se não conseguem entrar usando o aplicativo Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar o tamanho do PIN

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **configurações de ponte** , em **comprimento do pino**, selecione o número de dígitos que você deseja para o PIN.

4. Clique em **Salvar**.

> [!NOTE]
> [!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião. 

## <a name="want-to-know-more-about-pin-settings"></a>Quer saber mais sobre as configurações de PIN?

- Os pinos podem ter de 4 a 12 dígitos; o padrão é 5. Somente números são usados para criar PINs. Letras e caracteres especiais não são usados.
    
- Um PIN só é necessário para o organizador da reunião quando um usuário do Microsoft Teams ainda não iniciou a reunião. Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.
    
- As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
