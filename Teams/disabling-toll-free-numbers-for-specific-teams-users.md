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
ms.openlocfilehash: 158a4b31b0aaf65414af0d2119b3b6931a1f74ac
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014689"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Desativar números gratuitos para usuários específicos do Teams

Se a sua organização tem números gratuitos na Ponte de Audioconferência da Microsoft, é possível permitir ou impedir o uso deles em reuniões de organizadores específicos.  

Por padrão, todos os usuários em sua organização estão habilitados para o uso de números para ligações gratuitas, que significa que esses números, se estiver disponível, podem ser usados pelos participantes ingressem em suas reuniões. Se isso não for o comportamento desejado para alguns usuários em sua organização, você pode impedir usuários específicos usando esses números em suas reuniões por meio de um controle de habilitação de números gratuitos. 

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
