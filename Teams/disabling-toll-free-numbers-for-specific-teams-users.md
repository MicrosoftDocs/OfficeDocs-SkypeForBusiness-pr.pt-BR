---
title: Desativar números gratuitos para usuários específicos do Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: Os administradores podem controlar como os organizadores podme usar os números gratuitos para suas reuniões.
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887376"
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

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Próximo a **Audioconferência**, clique em **Editar**.

4. Desative **Incluir números gratuitos em solicitações de reunião deste usuário**. 

5. Clique em **Salvar.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Usar o Windows PowerShell**  

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
