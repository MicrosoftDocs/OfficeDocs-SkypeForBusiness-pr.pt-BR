---
title: Atribuir ou alterar locais para locais de emergência para usuários
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
description: Neste artigo, você aprenderá a atribuir ou alterar o local para um local de emergência para os usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60bd471e42eb6e8c2404eef47636da2c9894268c
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551635"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Atribuir ou alterar o local de um local de emergência para um usuário

Independentemente da opção de conectividade [PSTN](pstn-connectivity.md)&mdash;, você escolhe Planos de Chamada da Microsoft, Conexão de Operador, Telefone Móvel do Teams&mdash;ou Roteamento Direto, um local de emergência precisa ser atribuído a cada número de telefone ou usuário.

Dependendo da opção de conectividade PSTN, no entanto, a maneira como você gerencia e atribui locais de emergência para um usuário pode variar. Para obter mais informações, consulte [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md).

Este artigo descreve como atribuir ou alterar o local de  um local de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.

Este artigo se aplica aos Planos de Chamadas, ao Operator Connect e ao Teams Phone Mobile.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, clique em **Números de Telefone** > **de Voz**.

2. Na página **Números de** telefone, clique **na guia Números** , selecione um número de usuário na lista e clique em **Editar**.

3. No painel **Editar** , em Local **de emergência**, siga um dos seguintes procedimentos:

    - Para atribuir um local, pesquise o local ou o local e selecione o local nos resultados da pesquisa.

    - Para alterar o local já atribuído ao usuário, clique em **X** para remover o local e o local existentes, pesquise e selecione o local que você deseja atribuir.

4. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desative ou ative Email usuário com informações **de número de telefone**. Por padrão, isso está ativado.

5. Clique em **Aplicar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Atribuir ou alterar um local de emergência para um usuário](assign-change-emergency-location-user.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)