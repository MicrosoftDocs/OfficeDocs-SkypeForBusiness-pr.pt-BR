---
title: Adicionar, alterar, remover locais de emergência
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
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Saiba como adicionar, alterar ou remover um local de emergência para sua organização.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 99ab0821b8ccdb14664dc0a2aa37c959499ff8ac
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774736"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Adicionar, alterar ou remover um local de emergência para sua organização

Independentemente da [opção de conectividade PSTN](pstn-connectivity.md) , você escolhe&mdash;Planos de Chamada da Microsoft, Conexão do Operador, Teams Phone Mobile ou Locais de emergência de Roteamento&mdash;Direto podem ser associados a um número de telefone.

No entanto, dependendo da opção de conectividade PSTN, a forma como você gerencia locais de emergência e os requisitos de localização pode variar. Para obter mais informações, consulte [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md).

Este artigo descreve como adicionar, alterar ou remover um local de emergência para sua organização. 

Este artigo se aplica a Planos de Chamada da Microsoft, Conexão de Operador, Teams Phone Mobile e Roteamento Direto.

Você gerencia locais de emergência para sua organização no centro de administração do Microsoft Teams ou usando o PowerShell.

Para atribuir um local de emergência, usuários, números de telefone e locais de emergência precisam estar no mesmo país. Para obter mais informações, consulte [Atribuir ou alterar um local de emergência para um usuário](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Adicionar um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** > **de emergência** de locais.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para o local.
4. Selecione o país ou a região e insira o endereço.

   > [!NOTE]
   > Na Bélgica, França, Alemanha, Irlanda, Holanda e Espanha, é importante entender que para ativar com êxito um número de telefone no Microsoft 365, o endereço configurado no local de emergência, que é usado para adquirir o número, deve corresponder ao código de área do número de telefone.

5. Se o endereço não for encontrado e você quiser editar manualmente o endereço, ative **Editar o endereço manualmente**.
6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Alterar um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** > **de emergência** de locais.
2. Na lista, selecione o local que você deseja alterar e clique em **Editar**.
3. Faça as alterações desejadas.
4. Clique em **Salvar**.

> [!NOTE]
> Você só poderá alterar as informações de endereço de um local se o endereço não for validado. Se o endereço já estiver validado e você precisar alterar o endereço, exclua o local e crie um novo local com o endereço correto.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Remover um local de emergência

> [!NOTE]
> Você só poderá remover um local se nenhum usuário ou número de telefone for atribuído a ele. Se números ou usuários forem atribuídos ao local, você precisará removê-los primeiro.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Endereços** > **de emergência** de locais.
2. Na lista, selecione o local que você deseja remover e clique em **Excluir**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)
