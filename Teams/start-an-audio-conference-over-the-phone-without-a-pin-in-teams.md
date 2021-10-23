---
title: Iniciar a Conferência de Áudio pelo telefone sem um PIN Teams
ms.author: tonysmit
author: tonysmit
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
description: 'Saiba como habilitar ou desabilitar os chamadores anônimos de ingressar em uma reunião do Teams de administração. '
ms.openlocfilehash: da31c734275113eab3e96b67230a578d0609c1bb
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537302"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams

Pode ser frustrante para os usuários que discam para uma reunião ser realizada no lobby da reunião ouvindo música porque o organizador Microsoft Teams de reunião ainda não iniciou a reunião. 
  
Se um organizador da reunião chamar a reunião, por padrão, um PIN será necessário para iniciar uma reunião. Você pode defini-lo para que qualquer pessoa possa discar para uma reunião e não ser solicitado que um PIN inicie a reunião. Você pode usar o centro de administração para habilitar ou desabilitar essa configuração para um único usuário.
  
Um PIN não será necessário para o organizador da reunião se alguém tiver iniciado a reunião a partir do aplicativo Microsoft Teams. É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone. O PIN para reuniões é enviado ao usuário de áudio quando ele recebe a licença de **Audioconferência** e está habilitado para Audioconferência. Consulte Enviar um email para um usuário com suas informações de [Audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) e Emails que são enviados automaticamente aos usuários quando suas configurações de [Audioconferência mudarem.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar ou desabilitar chamadores anônimos para participar de uma reunião

 **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários**. 

2. Selecione um usuário na lista e clique em **Editar** na parte superior da página. 

3. Ao lado **de Audioconferência,** clique em **Editar**.

4. No painel **Audioconferência,** habilitar ou desabilitar os chamadores de discagem podem ser a primeira **pessoa em uma reunião.**
    
4. Clique em **Aplicar**. 

**Usando Windows PowerShell**
  
Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Se você deseja redefinir o PIN, consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião, será desabilitado:
    
  - Se a reunião ainda não tiver começado (ainda não há ninguém na reunião): um chamador será solicitado se ele for o organizador; se ele disser que sim, ele será solicitado a solicitar seu PIN e, depois de inserir o PIN, a reunião será iniciar e o usuário ingressará na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião, será habilitado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador está definida como off, a reunião será inicial e os chamadores anônimos ingressarão na reunião.
    
  - Se a reunião já tiver sido iniciada (outra pessoa já está na reunião): um chamador não será solicitado se ela for a organizadora e ela nunca será solicitado a solicitar o PIN; a reunião já foi iniciada e o chamador ingressará nele.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)