---
title: Adicionar, alterar, remover locais para locais de emergência
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: Saiba como adicionar, alterar ou remover um local para um local de emergência de sua organização no centro de administração do Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539428"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Adicionar, alterar ou remover um endereço de um local de emergência para sua organização

Dependendo do número de locais físicos da sua organização, você pode adicionar locais para prédios, andares e escritórios para criar um local de emergência mais específico. Consulte [gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md) para obter mais informações.
  
Para saber como obter um plano de chamadas e quanto eles custam, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Você gerencia locais de emergência para sua organização no centro de administração do Microsoft Teams ou usando o PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Adicionar um local a um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.
2. Na lista, clique no nome do local ao qual você deseja adicionar um local.
3. Na guia **locais** , clique em **Adicionar**.
4. Digite um nome para o local e clique em **aplicar**.

### <a name="using-powershell"></a>Usando o PowerShell

Veja [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Alterar um local para um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.
2. Na lista, clique no nome do local para o qual você deseja alterar um local.
3. Na guia **locais** , selecione o local que você deseja alterar e clique em **Editar**.
4. Atualize as informações do local e clique em **aplicar**.

### <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Remover um local de um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.
2. Na lista, clique no nome do local para o qual você deseja remover um local.
3. Na guia **locais** , selecione o local que você deseja remover e clique em **excluir**.

### <a name="using-powershell"></a>Usando o PowerShell

Consulte [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Tópicos relacionados

- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)
