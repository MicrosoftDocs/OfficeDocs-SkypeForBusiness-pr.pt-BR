---
title: Desativar números gratuitos para usuários específicos do Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podme usar os números gratuitos para suas reuniões.
ms.openlocfilehash: 3334a9f4af261d9b4cacd988fcdff2f6a0a4eb19
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753936"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Desativar números gratuitos para usuários específicos do Teams

Se a sua organização tem números gratuitos na Ponte de Audioconferência da Microsoft, é possível permitir ou impedir o uso deles em reuniões de organizadores específicos.  

Por padrão, todos os usuários da sua organização estão habilitados para usar números gratuitos, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para participar de suas reuniões. Se esse não for o comportamento desejado para alguns usuários da sua organização, será possível restringir o uso desses números por usuários específicos em reuniões através de um controle de ativação de números gratuitos. 

Quando os números gratuitos são desativados para um determinado organizador: 
 - Seus convites de reunião não conterão mais um número gratuito. 
 - Os números gratuitos não serão mais listados na página “Encontrar um número local” que é mencionada em seus convites de reunião. 
 - Os participantes não conseguirão entrar na reunião desse organizador se discarem para algum número gratuito da organização. 
 - Todas as reuniões do organizador serão reagendadas automaticamente e o número gratuito será removido.  

    > [!IMPORTANT]
    > O convite do organizador será reenviado por e-mail para todos os participantes dessas reuniões. 

 - Os participantes podem continuar participando das reuniões do organizador usando números tarifados. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desativar números gratuitos para usuários específicos 

Partir do **Centro de administração de equipes da Microsoft**:

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Próximo a **Audioconferência**, clique em **Editar**.

3. Defina a **incluir números para ligações gratuitas nas solicitações deste usuário de reunião** para **Off**. 

4. Clique em **Salvar.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Usar o Windows PowerShell**  

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
