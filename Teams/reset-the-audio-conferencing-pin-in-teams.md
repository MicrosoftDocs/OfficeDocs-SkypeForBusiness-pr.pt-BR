---
title: Redefinir o PIN de audioconferência no Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba o que você deve saber sobre PINs e como redefini-los no Microsoft Teams. '
ms.openlocfilehash: 7fe1ae3487caf9433b8f41753f6af9584a7d7f4d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206590"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Redefinir o PIN de audioconferência no Microsoft Teams

Um PIN é um código composto de números que é criado para cada usuário do Microsoft Teams habilitado para audioconferência. Os PINs de audioconferência são usados pelos organizadores da reunião para identificá-los e permitir que iniciem uma reunião por telefone. Se usarem o aplicativo Microsoft Teams para iniciar a reunião, o PIN não será necessário. Se o usuário esquecer o PIN e não conseguir encontrá-lo no e-mail enviado quando ele foi habilitado para a audioconferência, um administrador precisará redefinir o PIN ou ele poderá redefinir o próprio PIN.
  
As reuniões podem ser iniciadas quando um usuário autenticado entra usando o aplicativo Microsoft Teams ou quando o organizador entra com o PIN por telefone. Se a reunião exigir um PIN para ser iniciada, os usuários que entrarem por telefone serão colocados no lobby e esperarão ouvindo música até que a reunião seja iniciada. Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.

## <a name="reset-a-users-pin"></a>Redefinir o PIN de um usuário

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Redefinir PIN**.

4. Clique em **Redefinir**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Faça com que um usuário redefina seu próprio PIN

1. Solicite que o usuário acesse [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).
2. Clique em **Redefinir o PIN**. 


## <a name="what-else-should-you-know-about-pins"></a>O que mais você deve saber sobre PINs?

- Por motivos de segurança, o PIN só é mostrado para o administrador em uma ocasião: quando o PIN é redefinido. Depois que o PIN é redefinido por um administrador, o PIN será listado como * * *.
    
- Automaticamente enviando emails para usuários é habilitado por padrão e os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido. Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado a um usuário e você terá que enviar manualmente as informações de PIN para o usuário.
    
- Quando uma reunião for iniciada, todos os usuários do lobby serão conectados automaticamente. Por exemplo, se dois participantes tentarem participar de uma reunião antes que ela seja iniciada, eles serão colocados no lobby e esperarão ouvindo música. Quando o organizador da reunião participar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby entrarão na reunião.
    
- A configuração padrão é não permitir uma reunião ser iniciado por chamadores anônimos.
    
- Quando você habilita um usuário para conferência de áudio, por padrão, eles são enviados emails que incluem informações de conferência e o PIN. O usuário deve ter uma caixa de correio do Office 365, como quando um PIN é redefinido, um novo PIN será enviado ao usuário no email para seu endereço SMTP principal (alias) que está definido para o usuário.
    
- Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização. PINs podem ter somente de 4 a 12 dígitos, o padrão é 5. Se você alterar a configuração do tamanho do PIN, a configuração será aplicada somente aos PINs recém-gerados e não será aplicada à configuração do PIN para usuários existentes que estejam habilitados para audioconferência. Consulte [definir o comprimento do PIN para reuniões de conferência de áudio](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Por padrão, o email será definido como o endereço SMTP principal do Office 365 do usuário. Você pode enviar um email para um endereço que não seja do Office 365, como um endereço de email do Hotmail ou do MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso é útil se os usuários não tiverem uma caixa de correio do Exchange no Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir a ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md)
