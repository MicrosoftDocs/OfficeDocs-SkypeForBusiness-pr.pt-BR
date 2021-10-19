---
title: Adicionar, alterar, remover locais para locais de emergência
author: cichur
ms.author: v-cichur
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
description: Saiba como adicionar, alterar ou remover um local de emergência para sua organização no Microsoft Teams de administração.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2bf3e2fad1ee0f0182e2b3a25f2be78f5ef68823
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465961"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Adicionar, alterar ou remover um endereço de um local de emergência para sua organização

Dependendo do número de locais físicos em sua organização, você pode adicionar locais para edifícios, pisos e escritórios para criar um local de emergência mais específico. Consulte [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md) para obter mais informações.

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

- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)