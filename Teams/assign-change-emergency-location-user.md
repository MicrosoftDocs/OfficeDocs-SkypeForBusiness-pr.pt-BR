---
title: Atribuir ou alterar um local de emergência para um usuário
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
description: Neste artigo, você aprenderá sobre como atribuir ou alterar um local de emergência para usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36be65ef14cfe0fc97ce49dfa9227fe50daa18f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588373"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Atribuir ou alterar um local de emergência para um usuário

Ao configurar Planos de Chamadas, você precisa atribuir um local de emergência a cada número de telefone ou usuário. Em países europeus, o local de emergência é associado ao número de telefone quando você o consegue do Microsoft 365 ou Office 365 ou quando você transfere um número de telefone para Microsoft 365 ou Office 365. Nos Estados Unidos, o local de emergência é associado ao número de telefone quando é atribuído ao usuário. O endereço de emergência pode ser alterado se o usuário atribuído a ele se mover para um novo local. Para obter mais informações sobre endereços e locais de emergência, consulte [O que são locais de emergência, locais e roteamento de chamadas?](./what-are-emergency-locations-addresses-and-call-routing.md).
  
Para saber como obter um Plano de Chamada e quanto eles custam, [consulte Teams licenciamento de complemento.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
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