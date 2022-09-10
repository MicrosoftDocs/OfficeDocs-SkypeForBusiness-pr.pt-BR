---
title: Iniciar audioconferência por telefone sem um PIN no Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Saiba como habilitar ou desabilitar chamadores anônimos de ingressar em uma reunião no centro de administração do Teams. '
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641942"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams

Pode ser frustrante para os usuários que discam para uma reunião serem mantidos no lobby da reunião ouvindo música porque o organizador da reunião do Microsoft Teams não iniciou a reunião.
  
Se um organizador da reunião ligar para a reunião, por padrão, um PIN será necessário para iniciar uma reunião. Você pode configurá-lo para que qualquer pessoa possa discar para uma reunião e não ser solicitado que um PIN inicie a reunião. Você pode usar o centro de administração para habilitar ou desabilitar essa configuração para um único usuário.
  
Um PIN não será necessário para o organizador da reunião se alguém tiver iniciado a reunião no aplicativo Microsoft Teams. É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone. O PIN para reuniões é enviado ao usuário de áudio quando ele recebe a licença de **Audioconferência** e está habilitado para Audioconferência. Consulte [Enviar um email para um](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) usuário com suas informações de Audioconferência e Emails que são enviados automaticamente aos usuários quando suas [configurações de Audioconferência são alteradas](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar ou desabilitar chamadores anônimos para participar de uma reunião

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, clique em **Usuários**.

2. Selecione um usuário na lista e clique em **Editar** na parte superior da página.

3. Ao lado **de Audioconferência**, clique em **Editar**.

4. No painel **audioconferência** , habilitar ou desabilitar chamadas discadas pode ser **a primeira pessoa em uma reunião**.

5. Clique em **Aplicar**.

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell

Consulte a [referência do PowerShell do Microsoft Teams](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Se você quiser redefinir o PIN, consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin-in-teams.md).

- Se o acesso anônimo, ou não exigir um PIN para iniciar uma reunião, será desabilitado:

  - Se a reunião ainda não tiver sido iniciada (não há ninguém na reunião): um chamador será solicitado se ele for o organizador; se ele disser que sim, ele será solicitado a inserir o PIN e, depois de inserir o PIN, a reunião será iniciada e o usuário ingressará na reunião.

  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.

- Se o acesso anônimo, ou não exigir um PIN para iniciar uma reunião, estará habilitado:

  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador está definida como desativada, a reunião será iniciada e os chamadores anônimos ingressarão na reunião.

  - Se a reunião já tiver sido iniciada (outra pessoa já está na reunião): um chamador não será solicitado se ela for a organizadora e ela nunca será solicitada para o PIN; a reunião já foi iniciada e o chamador irá ingressá-la.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar o Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Microsoft 365 para Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
