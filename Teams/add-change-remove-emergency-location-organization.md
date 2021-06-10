---
title: Adicionar, alterar, remover locais de emergência
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
description: 'Saiba como adicionar, alterar ou remover um local de emergência para sua organização no Microsoft Teams de administração. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b918cbcbebf8edb2cd54d08e0e4a3177867fa623
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121519"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Adicionar, alterar ou remover um local de emergência para sua organização

Um local de emergência deve ser associado a um número de telefone, mas quando isso acontece pode variar entre países e regiões. Por exemplo, nos Estados Unidos, você precisa associar um local de emergência ao atribuir o número de telefone ao usuário. No Reino Unido, você precisa associar um local de emergência ao número de telefone quando você obter os números de telefone de Microsoft 365 ou Office 365 ou transferir números de telefone do seu provedor de serviços atual.

Não importa em qual país ou região você está, você pode adicionar um local ou locais a um local de emergência e remover um local de emergência. Dependendo do número de locais físicos em sua organização, você pode criar locais para edifícios, pisos e escritórios. Consulte [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md).
  
Para saber como obter um Plano de Chamada e quanto eles custam, [consulte Teams licenciamento de complemento.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

Você gerencia locais de emergência para sua organização no centro de administração Microsoft Teams ou usando o PowerShell.
  
## <a name="add-an-emergency-location"></a>Adicionar um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para o local.
4. Selecione o país ou a região e insira o endereço.

   > [!NOTE]
   > Na Bélgica, França, Alemanha, Irlanda, Países Baixos e Espanha, é importante entender que, para ativar com êxito um número de telefone no Microsoft 365 ou no Office 365, o endereço definido no local de emergência, que é usado para adquirir o número, deve corresponder ao código de área do número de telefone.

5. Se o endereço não for encontrado e você quiser editar manualmente o endereço, a opção **Editar o endereço manualmente.**
6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Alterar um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.
2. Na lista, selecione o local que você deseja alterar e clique em **Editar**.
3. Faça as alterações que você deseja.
4. Clique em **Salvar**.

> [!NOTE]
> Você só poderá alterar as informações de endereço de um local se o endereço não for validado. Se o endereço já estiver validado e você precisar alterar o endereço, exclua o local e crie um novo local com o endereço correto.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Remover um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.
2. Na lista, selecione o local que você deseja remover e clique em **Excluir**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)