---
title: Atribuir ou alterar um local de emergência para um usuário
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
description: Neste artigo, você aprenderá a atribuir ou alterar um local de emergência para os usuários da sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 450fe848052af1e331964da3d7b695daf0f1567a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610990"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Atribuir ou alterar um local de emergência para um usuário

Quando você estiver configurando planos de chamada, será necessário atribuir um local de emergência para cada número de telefone ou usuário. Em países europeus, o local de emergência está associado ao número de telefone quando você o recebe do Microsoft 365 ou do Office 365 ou quando transfere um número de telefone para o Microsoft 365 ou o Office 365. Nos Estados Unidos, o local de emergência está associado ao número de telefone quando ele é atribuído ao usuário. O endereço de emergência pode ser alterado se o usuário ao qual ele está atribuído for movido para um novo local. Para obter mais informações sobre endereços e locais de emergência, consulte [o que são locais de emergência, locais e encaminhamento de chamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).
  
Para saber como obter um plano de chamadas e quanto eles custam, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
Você pode atribuir ou alterar um local de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em números de telefone de **voz**  >  **Phone numbers**.

2. Na página **números de telefone** , clique na guia **números** , selecione um número de usuário na lista e, em seguida, clique em **Editar**.

3. No painel **Editar** , em **local de emergência**, siga um destes procedimentos:

   - Para atribuir um local de emergência, procure e selecione um local de emergência.

   - Para alterar o local de emergência que já está atribuído ao usuário, clique em **X** para remover o local existente e, em seguida, procure e selecione o local que você deseja atribuir.

4. Dependendo se você deseja enviar um email para o usuário com as informações do número de telefone, desative ou ative o **usuário de email com informações de número de telefone**. Por padrão, ele está ativado.

5. Clique em **Aplicar**.

## <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Atribuir ou alterar um endereço de um local de emergência para um usuário](assign-change-emergency-place-user.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
