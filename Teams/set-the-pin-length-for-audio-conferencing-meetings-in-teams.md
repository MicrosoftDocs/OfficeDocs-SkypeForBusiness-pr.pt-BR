---
title: Definir o tamanho PIN para reuniões de conferência de áudio no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Saiba os parâmetros para o comprimento e os requisitos de PIN e veja como definir o tamanho para reuniões no Microsoft Teams.
ms.openlocfilehash: 0300bba9139bdf98315b8af4200dd729ff6e70a1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882987"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Definir o tamanho PIN para reuniões de conferência de áudio no Microsoft Teams

Quando você estiver configurando a audioconferência for Microsoft Teams, você receberá uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone que você definir será incluído em convites de reunião para o aplicativo Microsoft Teams.
  
A ponte de conferência de áudio atende uma chamada para pessoas que estão discando para uma reunião usando um telefone. Ela atende do chamador com prompts de voz de um atendedor automático e em seguida, dependendo de suas definições, pode reproduzir notificações e será feita aos chamadores a registrar seu nome. **Configurações de ponte da Microsoft** permitem que você alterar as configurações de notificações de reunião e experiência de ingresso na reunião e definir o tamanho dos pinos que são usados pelo organizadores de reunião. Organizadores de reunião usam PINs para iniciar reuniões, se eles não podem ingressar na reunião usando o app Teams da Microsoft.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar o tamanho do PIN

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**. 

3. No painel de **configurações de ponte** , em **tamanho do PIN**, selecione o número de dígitos que você deseja para o PIN.

4. Clique em **Salvar**.

> [!NOTE]
> [!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião. 

## <a name="want-to-know-more-about-pin-settings"></a>Quer saber mais sobre configurações de PIN?

- PINs podem ter entre 4 para 12 dígitos; o padrão é 5. Somente números são usados para criar PINs. Letras e caracteres especiais não são usados.
    
- Um PIN só é necessária para o organizador da reunião quando um usuário do Microsoft Teams já não tiver iniciado a reunião. Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.
    
- As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
