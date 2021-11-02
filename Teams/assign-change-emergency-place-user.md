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
description: Neste artigo, você aprenderá a atribuir ou alterar o local para um local de emergência para usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9bd69356be22954ee1b1b44b2dcc1a52c1e72507
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634880"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Atribuir ou alterar o local para um local de emergência para um usuário

Independentemente da opção de conectividade [PSTN,](pstn-connectivity.md) você escolhe Planos de Chamadas da Microsoft, Operador Conexão ou Roteamento Direto um local de emergência precisa ser atribuído a cada número de telefone ou &mdash; &mdash; usuário.

No entanto, dependendo da sua opção de conectividade PSTN, a forma como você gerencia e atribui locais de emergência para um usuário pode variar. Para obter mais informações, consulte [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md).

Este artigo descreve como atribuir  ou alterar o local para um local de emergência para um usuário no centro de administração Microsoft Teams ou usando o PowerShell.

Este artigo se aplica a Planos de Chamada e Conexão.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Voz Telefone**  >  **números**.

2. Na página **Telefone números,** clique na guia **Números,** selecione um número de usuário na lista e clique em **Editar**.

3. No painel **Editar,** em **Local de emergência,** faça um dos seguintes procedimentos:

    - Para atribuir um local, pesquise o local ou o local e selecione o local nos resultados da pesquisa.

    - Para alterar o local já atribuído ao usuário, clique em **X** para remover o local e o local existentes, procure e selecione o local que você deseja atribuir.

4. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desativar ou ativar o usuário de email com informações **de número de telefone**. Por padrão, isso está em.

5. Clique em **Aplicar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Atribuir ou alterar um local de emergência para um usuário](assign-change-emergency-location-user.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)