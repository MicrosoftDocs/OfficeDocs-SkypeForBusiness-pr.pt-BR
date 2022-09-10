---
title: Definir o tamanho do PIN para reuniões de Audioconferência
ms.author: heidip
author: MicrosoftHeidi
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
description: Conheça os parâmetros para o tamanho e os requisitos de um PIN e veja como definir o comprimento das reuniões no Microsoft Teams.
ms.openlocfilehash: e589a550eba48401612e183200e54f678f9890c4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641952"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Definir o tamanho do PIN para reuniões de audioconferência no Microsoft Teams

Ao configurar a audioconferência para o Microsoft Teams, você receberá uma ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone definido será incluído nos convites da reunião para o aplicativo Microsoft Teams.
  
A ponte de audioconferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone. Ele atende o chamador com prompts de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações e solicitar que os chamadores gravem seu nome. **As configurações de ponte da Microsoft** permitem que você altere as configurações para notificações de reunião e a experiência de ingresso na reunião e defina a duração dos PINs usados pelos organizadores da reunião. Os organizadores da reunião usam PINs para iniciar reuniões se não puderem ingressar na reunião usando o aplicativo Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar o tamanho do PIN

Usando o centro de administração do Microsoft Teams:

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.

3. No painel **Configurações da** Ponte, em Tamanho **do PIN**, selecione o número de dígitos desejados para o PIN.

4. Clique em **Salvar**.

> [!NOTE]
> [!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião.

## <a name="want-to-know-more-about-pin-settings"></a>Quer saber mais sobre as configurações de PIN?

- Os PINs podem ter de 4 a 12 dígitos; o padrão é 5. Somente números são usados para criar PINs. Letras e caracteres especiais não são usados.

- Um PIN só é necessário para o organizador da reunião quando um usuário do Microsoft Teams ainda não iniciou a reunião. Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.

- As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar o Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Microsoft 365 para Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
