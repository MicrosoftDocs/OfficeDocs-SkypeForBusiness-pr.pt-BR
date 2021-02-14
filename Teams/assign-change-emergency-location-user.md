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
localization_priority: Normal
f1.keywords:
- NOCSH
description: Neste artigo, você aprenderá sobre como atribuir ou alterar um local de emergência para os usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809561"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Atribuir ou alterar um local de emergência para um usuário

Ao configurar os Planos de Chamada, você precisa atribuir um local de emergência a cada número de telefone ou usuário. Em países europeus, o local de emergência está associado ao número de telefone quando você o consegue do Microsoft 365 ou do Office 365 ou quando você transfere um número de telefone para o Microsoft 365 ou o Office 365. Nos Estados Unidos, o local de emergência está associado ao número de telefone quando ele é atribuído ao usuário. O endereço de emergência pode ser alterado se o usuário ao que ele foi atribuído se mover para um novo local. Para saber mais sobre endereços e locais de emergência, confira [O que são locais,](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)locais e encaminhamento de chamadas de emergência? .
  
Para saber como obter um Plano de Chamada e quanto eles custam, consulte o licenciamento [de complementos do Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
Você pode atribuir ou alterar um local de emergência para um usuário no Centro de administração do Microsoft Teams ou usando o PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, clique em **Números de Telefone** De  >  **Voz.**

2. Na página **Números de telefone,** clique na **guia Números,** selecione um número de usuário na lista e clique em **Editar.**

3. No painel **Editar,** em Local **de emergência,** faça o seguinte:

   - Para atribuir um local de emergência, pesquise e selecione um local de emergência.

   - Para alterar o local de emergência que já está atribuído ao usuário, clique em **X** para remover o local existente e, em seguida, pesquise e selecione o local que você deseja atribuir.

4. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desligue ou a ligue o usuário de email com informações de número **de telefone.** Por padrão, isso está em.

5. Clique em **Aplicar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Atribuir ou alterar um endereço de um local de emergência para um usuário](assign-change-emergency-place-user.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
