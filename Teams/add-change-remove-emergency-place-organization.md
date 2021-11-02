---
title: Adicionar, alterar, remover locais para locais de emergência
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Saiba como adicionar, alterar ou remover um local de emergência para sua organização.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fec188634377b04cb4149d3680acc07eef797149
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634870"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Adicionar, alterar ou remover um endereço de um local de emergência para sua organização

Dependendo do número de locais físicos em  sua organização, você pode adicionar locais para edifícios, pisos e escritórios para criar um local de emergência mais específico.

No entanto, dependendo da sua opção de conectividade PSTN, a forma como você gerencia os locais de emergência e os requisitos de local podem variar. Para obter mais informações, consulte [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md).

Este artigo descreve como adicionar, alterar ou remover um *local* de emergência para sua organização.

Este artigo se aplica aos Planos de Chamadas da Microsoft, Conexão operador e Roteamento Direto.

Você gerencia locais de emergência para sua organização no centro de administração Microsoft Teams ou usando o PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Adicionar um local a um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.
2. Na lista, clique no nome do local para o qual você deseja adicionar um lugar.
3. Na guia **Locais,** clique em **Adicionar**.
4. Insira um nome de local e clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Alterar um local para um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.
2. Na lista, clique no nome do local para o qual você deseja alterar um local.
3. Na guia **Locais,** selecione o local que você deseja alterar e clique em **Editar**.
4. Atualize as informações do local e clique em **Aplicar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Remover um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.
2. Na lista, clique no nome do local para o qual você deseja remover um local.
3. Na guia **Locais,** selecione o local que você deseja remover e clique em **Excluir**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)