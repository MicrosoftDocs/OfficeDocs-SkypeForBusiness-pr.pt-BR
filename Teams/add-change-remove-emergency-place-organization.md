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
localization_priority: Normal
f1.keywords:
- NOCSH
description: Saiba como adicionar, alterar ou remover um local de emergência para sua organização no centro de administração do Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806271"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Adicionar, alterar ou remover um endereço de um local de emergência para sua organização

Dependendo do número de locais físicos em sua organização, você pode adicionar locais para edifícios, andares e escritórios para criar um local de emergência mais específico. Consulte [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md) para obter mais informações.
  
Para saber como obter um Plano de Chamada e quanto eles custam, consulte o licenciamento [de complementos do Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

Você gerencia locais de emergência para sua organização no centro de administração do Microsoft Teams ou usando o PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Adicionar um local a um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** de Emergência de  >  **Locais.**
2. Na lista, clique no nome do local para o qual você deseja adicionar um local.
3. Na guia **Casas,** clique em **Adicionar**.
4. Insira um nome de local e clique em **Aplicar.**

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Alterar um local para um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** de Emergência de  >  **Locais.**
2. Na lista, clique no nome do local para o qual você deseja alterar um local.
3. Na guia **Casas,** selecione o local que você deseja alterar e clique em **Editar**.
4. Atualize as informações de local e clique em **Aplicar.**

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Remover um local de um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** de Emergência de  >  **Locais.**
2. Na lista, clique no nome do local para o qual você deseja remover um local.
3. Na guia **Casas,** selecione o local que deseja remover e clique em **Excluir**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Tópicos relacionados

- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)
