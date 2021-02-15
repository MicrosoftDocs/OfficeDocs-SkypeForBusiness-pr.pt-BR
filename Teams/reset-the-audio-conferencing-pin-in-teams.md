---
title: Redefinir o PIN de audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Saiba como redefinir o PIN de Audioconferência de um usuário no Microsoft Teams e saiba fatos importantes sobre PINs.
ms.openlocfilehash: 3f1055551edb45ac422052476196f01ee4d2765d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237461"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Redefinir o PIN de audioconferência no Microsoft Teams

Um PIN é um código composto de números que é criado para cada usuário do Microsoft Teams habilitado para audioconferência. Os PINs de audioconferência são usados pelos organizadores da reunião para identificá-los e permitir que iniciem uma reunião por telefone. Se usarem o aplicativo Microsoft Teams para iniciar a reunião, o PIN não será necessário. Se o usuário esquecer o PIN e não conseguir encontrá-lo no e-mail enviado quando ele foi habilitado para a audioconferência, um administrador precisará redefinir o PIN ou ele poderá redefinir o próprio PIN.
  
As reuniões podem ser iniciadas quando um usuário autenticado ingressar usando o aplicativo Microsoft Teams ou quando o organizador ingressar com o PIN por telefone. Se a reunião exigir um PIN para ser iniciada, os usuários que entrarem por telefone serão colocados no lobby e esperarão ouvindo música até que a reunião seja iniciada. Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.

## <a name="reset-a-users-pin"></a>Redefinir o PIN de um usuário

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Clique **em Editar.**

3. Em **Audioconferência,** clique em **Redefinir PIN.**

4. Clique **em Redefinir.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Fazer com que um usuário redefinir seu próprio PIN

1. Fazer o usuário ir para [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Clique **em Redefinir PIN.** 


## <a name="what-else-should-you-know-about-pins"></a>O que mais você deve saber sobre PINs?

- Para fins de segurança, o PIN é mostrado apenas uma vez para um administrador, quando o PIN é redefinido. Depois que o PIN for redefinido por um administrador, o PIN será listado como ***********.
    
- O envio automático de emails para os usuários está habilitado por padrão, e os usuários receberão um email com seu PIN quando eles estão habilitados para audioconferência ou quando o PIN é redefinido. Mas se você tiver desabilitado o envio automático de emails, um email de redefinição de PIN não será enviado para um usuário e você terá que enviar manualmente as informações do PIN para o usuário.
    
- Quando uma reunião é iniciada, todos os usuários no lobby ingressarão automaticamente. Por exemplo, se dois participantes tentarem ingressar em uma reunião antes de começar, eles serão colocados no lobby e ouvirão música em espera e, quando o organizador da reunião ingressar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby ingressarão na reunião.
    
- A configuração padrão é não permitir que uma reunião seja iniciada por chamadores anônimos.
    
- Quando você habilita um usuário para audioconferência, por padrão, ele é enviado emails que incluem informações de conferência e seu PIN. O usuário deve ter uma caixa de correio do Microsoft 365 ou do Office 365, pois quando um PIN é redefinido, um novo PIN é enviado ao usuário por email para seu endereço SMTP principal (alias) definido para o usuário.
    
- Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização. PINs podem ter somente de 4 a 12 dígitos, o padrão é 5. Se você alterar a configuração do tamanho do PIN, a configuração será aplicada somente aos PINs recém-gerados e não será aplicada à configuração do PIN para usuários existentes que estejam habilitados para audioconferência. Consulte [Definir a duração do PIN para reuniões de Audioconferência.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- O email por padrão será definido como o endereço SMTP principal do Microsoft 365 ou office 365 do usuário. Você pode enviar um email para um endereço que não seja do Microsoft 365 ou não do Office 365, como um endereço de email hotmail ou MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso é útil se os usuários não têm uma caixa de correio do Exchange no Microsoft 365 ou no Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir a ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md)
