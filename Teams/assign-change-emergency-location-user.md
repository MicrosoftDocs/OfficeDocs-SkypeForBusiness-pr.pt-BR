---
title: Atribuir ou alterar um local de emergência para um usuário
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
description: Neste artigo, você aprenderá a atribuir ou alterar um local de emergência para os usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a43ca031b8787d62639e141c3f733acdb402f85a
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551645"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Atribuir ou alterar um local de emergência para um usuário

Independentemente da opção de conectividade [PSTN](pstn-connectivity.md)&mdash;, você escolhe Planos de Chamada da Microsoft, Conexão de Operador, Telefone Móvel do Teams&mdash;ou Roteamento Direto, um local de emergência precisa ser atribuído a cada número de telefone ou usuário.

Dependendo da opção de conectividade PSTN, no entanto, a maneira como você gerencia e atribui locais de emergência para um usuário pode variar. Para obter mais informações, consulte [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md).

Este artigo descreve como atribuir ou alterar um local de emergência para um usuário. 

Este artigo se aplica aos Planos de Chamadas, ao Operator Connect e ao Teams Phone Mobile.
  
Você pode atribuir ou alterar um local de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, clique em **Números de Telefone** > **de Voz**.

2. Na página **Números de** telefone, clique **na guia Números** , selecione um número de usuário na lista e clique em **Editar**.

3. No painel **Editar** , em Local **de emergência**, siga um dos seguintes procedimentos:

   - Para atribuir um local de emergência, pesquise e selecione um local de emergência.

   - Para alterar o local de emergência já atribuído ao usuário, clique em **X** para remover o local existente e, em seguida, pesquise e selecione o local que você deseja atribuir.

4. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desative ou ative Email usuário com informações **de número de telefone**. Por padrão, isso está ativado.

5. Clique em **Aplicar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment). 

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um endereço de um local de emergência para um usuário](assign-change-emergency-place-user.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)
