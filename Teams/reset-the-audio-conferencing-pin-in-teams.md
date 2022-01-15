---
title: Redefinir o PIN de audioconferência no Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Saiba como redefinir o PIN de Audioconferência de um usuário no Microsoft Teams e saiba fatos importantes sobre PINs.
ms.openlocfilehash: 841d4f562529f9c1f078a0c5eeaa2b022712ca44
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055141"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Redefinir o PIN de audioconferência no Microsoft Teams

Um PIN é um código que é criado para cada Microsoft Teams usuário habilitado para audioconferência. Os PINs de audioconferência são usados pelos organizadores da reunião para identificar que eles são o organizador da reunião e permitir que eles iniciem uma reunião por telefone. Se eles usarem o Microsoft Teams para iniciar a reunião, um PIN não será necessário. Se os usuários esquecerem o PIN e não puderem encontrá-lo no email que foi enviado para eles quando eles foram habilitados para audioconferência, um administrador pode redefinir seu PIN ou pode redefinir seu próprio PIN.
  
As reuniões podem ser iniciadas quando um usuário autenticado ingressar usando o aplicativo Microsoft Teams ou quando o organizador ingressar com seu PIN pelo telefone. Quando uma reunião exige que um PIN seja acionada, os usuários que ingressarem no telefone serão colocados no lobby e ouvirão música em espera até que o organizador os admita. Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.

## <a name="reset-a-users-pin"></a>Redefinir o PIN de um usuário

Usando o Microsoft Teams de administração:

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Clique **em Editar**.

3. Em **Audioconferência,** clique em **Redefinir PIN**.

4. Clique **em Redefinir**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>Fazer com que um usuário redefinir seu próprio PIN

1. Fazer o usuário ir para [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp) .
2. Clique **em Redefinir PIN**.

> [!NOTE]
> Para GCCH, vá para: [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp) .
> Para DoD, vá para: [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp) .

## <a name="what-else-should-you-know-about-pins"></a>O que mais você deve saber sobre PINs?

- Para fins de segurança, o PIN só é mostrado a um administrador uma vez, quando o PIN é redefinido. Depois que o PIN for redefinido por um administrador, o PIN será listado como *********.

- O envio automático de emails para usuários está habilitado por padrão e os usuários receberão um email com seu PIN quando eles estão habilitados para audioconferência ou quando o PIN for redefinido. Mas se você tiver desabilitado o envio automático de emails, um email de redefinição de PIN não será enviado para um usuário e você terá que enviar manualmente as informações de PIN para o usuário.

- Quando uma reunião é iniciada, o organizador precisa admitir que todos os usuários PSTN no lobby participem da reunião. Por exemplo, se dois participantes PSTN tentarem ingressar em uma reunião antes de começar, eles serão colocados no lobby e ouvirão música em espera, e quando o organizador da reunião ingressar usando seu PIN por telefone, a reunião será iniciada e o organizador poderá usar o comando na reunião (pressione *21) para admitir todos os usuários PSTN no lobby.

- A configuração padrão é não permitir que uma reunião seja iniciada por chamadores anônimos.

- Quando você habilita um usuário para audioconferência, por padrão, eles são enviados emails que incluem informações de conferência e seu PIN. O usuário deve ter uma caixa de correio Microsoft 365 ou Office 365, pois quando um PIN for redefinido, um novo PIN será enviado para o usuário por email para seu endereço SMTP principal (alias) definido para o usuário.

- Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização. PINs podem ter somente de 4 a 12 dígitos, o padrão é 5. Se você alterar a configuração do tamanho do PIN, a configuração será aplicada somente aos PINs recém-gerados e não será aplicada à configuração do PIN para usuários existentes que estejam habilitados para audioconferência. Consulte [Definir o tamanho do PIN para reuniões de Audioconferência.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)

- O email por padrão será definido como o endereço SMTP Microsoft 365 ou Office 365 SMTP principal do usuário. Você pode enviar um email para um endereço não Microsoft 365 ou não Office 365 como um endereço de email do Hotmail ou MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso será útil se os usuários não têm uma caixa de correio Exchange no Microsoft 365 ou Office 365.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir a ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md)
