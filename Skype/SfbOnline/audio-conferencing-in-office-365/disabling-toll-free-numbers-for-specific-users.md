---
title: Desabilitando números para ligações gratuitas para usuários específicos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números para ligações gratuitas para suas reuniões.
ms.openlocfilehash: c144f807a20088f8e2330b541ba18b1da4b40e10
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703794"
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

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desabilitando números para ligações gratuitas para usuários específicos 

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Clique no menu ao lado de **Pontes de conferência**e clique em **Editar** na lista suspensa.

4. No painel de tarefas do **provedor de ponte de conferência** , desative **Permitir usando números para ligações gratuitas na ponte de conferência da sua organização para participar de reuniões deste usuário**. 

5. Clique em **se aplicam.** 

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis. 

2. No Painel de Ações, clique em **Editar**. 

3. Desmarque **Permitir usando números de discagem gratuita para participar de reuniões deste usuário**. 
 
4. Clique em **Salvar**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Usando o PowerShell**  

Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle. Por exemplo: 

 - Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
