---
title: "Desabilitando números para ligações gratuitas para usuários específicos"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Os administradores podem controlar como os organizadores podem usar números para ligações gratuitas para suas reuniões."
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>Desabilitando números para ligações gratuitas para usuários específicos

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

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a>Desabilitando números para ligações gratuitas para usuários específicos usando o Skype para o Centro de administração de negócios 
 1. Vá para o **Centro de administração do Office 365** > **Skype for Business**. 
 2. No Skype para o Centro de administração de negócios, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis. 
 3. No Painel de Ações, clique em **Editar**. 
 4. Marque ou desmarque **Permitir usando números de discagem gratuita para participar de reuniões deste usuário**. 
 5. Clique em **Salvar**. 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a>Desabilitando números para ligações gratuitas para usuários específicos usando o PowerShell  

Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle. Por exemplo: 

 - Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
