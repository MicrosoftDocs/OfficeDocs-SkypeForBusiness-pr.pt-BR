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
ms.openlocfilehash: 905e0e66555f908e98368d592905e98b54db059a
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537282"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Atribuir ou alterar um local de emergência para um usuário

Um local de emergência precisa ser atribuído a cada número de telefone ou usuário. Para obter mais informações sobre endereços e locais de emergência, consulte [O que são locais de emergência, locais e roteamento de chamadas?](./what-are-emergency-locations-addresses-and-call-routing.md).

Para Planos de Chamadas da Microsoft, em países europeus, o local de emergência é associado ao número de telefone quando você o Microsoft 365 ou quando você transfere um número de telefone para Microsoft 365. Nos Estados Unidos, o local de emergência é associado ao número de telefone quando é atribuído ao usuário. O endereço de emergência pode ser alterado se o usuário atribuído a ele se mover para um novo local.
  
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

Consulte [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Atribuir ou alterar um endereço de um local de emergência para um usuário](assign-change-emergency-place-user.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)