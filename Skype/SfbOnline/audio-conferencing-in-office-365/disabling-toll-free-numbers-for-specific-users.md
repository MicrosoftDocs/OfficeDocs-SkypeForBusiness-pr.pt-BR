---
title: Desabilitando números para ligações gratuitas para Skype específico para usuários corporativos Online
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números para ligações gratuitas para suas reuniões.
ms.openlocfilehash: f553cc3abad8f4490d06099554c188881ef47e24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229277"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Desabilitando números para ligações gratuitas para Skype específico para usuários corporativos Online
 
> [!Note]
> Para obter informações sobre como desabilitar números livre de ferramenta para usuários de equipes, consulte [Desabilitando números para ligações gratuitas para usuários específicos de equipes](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Se sua organização tiver números para ligações gratuitas no seu Microsoft Audio Conferencing Bridge, você pode permitir ou impedir que o seu uso nas reuniões de organizadores específicos.  

Por padrão, todos os usuários em sua organização estão habilitados para o uso de números para ligações gratuitas, que significa que esses números, se estiver disponível, podem ser usados pelos participantes ingressem em suas reuniões. Se isso não for o comportamento desejado para alguns usuários em sua organização, você pode impedir usuários específicos usando esses números em suas reuniões por meio de um controle de habilitação de números gratuitos. 

Quando os números para ligações gratuitas estão desabilitados para um determinado organizador: 
 - Não é mais um número de chamada gratuito será incluído em seu ou convida sua reunião. 
 - Não há mais números para ligações gratuitas serão listados na página "Localizar um número local" que é referenciada no seu ou convida sua reunião. 
 - Os participantes não conseguirá ingressar na reunião do organizador determinado se eles discarem qualquer número de chamada gratuito da organização. 
 - Todas as reuniões do organizador serão reagendadas automaticamente e o número de chamada gratuito será removido do-los.  

    > [!IMPORTANT]
    > Isso irá Reenviar todos os convites de email do organizador para todos os participantes dessas reuniões. 

 - Os participantes podem continuar a ingressar em reuniões do organizador usando números tarifados. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desativar números gratuitos para usuários específicos 

Partir do **Centro de administração de equipes da Microsoft**:

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Ao lado de **Conferência de áudio**, clique em **Editar**.

3. Defina a **incluir números para ligações gratuitas nas solicitações deste usuário de reunião** para **Off**. 

4. Clique em **Salvar.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Usando o PowerShell**  

Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle. Por exemplo: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
