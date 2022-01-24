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
description: Neste artigo, você aprenderá sobre como atribuir ou alterar um local de emergência para usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004635be112bb8d38b88277e89c24d263b21ec37
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180894"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Atribuir ou alterar um local de emergência para um usuário

Independentemente da opção de conectividade [PSTN,](pstn-connectivity.md) você escolhe Planos de Chamadas da Microsoft, Operador Conexão ou Roteamento Direto um local de emergência precisa ser atribuído a cada número de telefone ou &mdash; &mdash; usuário.

No entanto, dependendo da sua opção de conectividade PSTN, a forma como você gerencia e atribui locais de emergência para um usuário pode variar. Para obter mais informações, consulte [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md).

Este artigo descreve como atribuir ou alterar um local de emergência para um usuário. 

Este artigo se aplica a Planos de Chamada e Conexão.
  
Você pode atribuir ou alterar um local de emergência para um usuário no centro de administração Microsoft Teams ou usando o PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Voz Telefone**  >  **números**.

2. Na página **Telefone números,** clique na guia **Números,** selecione um número de usuário na lista e clique em **Editar**.

3. No painel **Editar,** em **Local de emergência,** faça um dos seguintes procedimentos:

   - Para atribuir um local de emergência, pesquise e selecione um local de emergência.

   - Para alterar o local de emergência já atribuído ao usuário, clique em **X** para remover o local existente e, em seguida, procure e selecione o local que você deseja atribuir.

4. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desativar ou ativar o usuário de email com informações **de número de telefone**. Por padrão, isso está em.

5. Clique em **Aplicar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment). 

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um endereço de um local de emergência para um usuário](assign-change-emergency-place-user.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)
