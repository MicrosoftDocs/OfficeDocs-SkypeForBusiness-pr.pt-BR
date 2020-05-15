---
title: Atribuir, alterar locais para locais de emergência para usuários
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
description: Neste artigo, você aprenderá a atribuir ou alterar o local de um local de emergência para os usuários da sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5b13cf5d4b4a0cf22077318e3c2c2196840f66e
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232462"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Atribuir ou alterar o local de um local de emergência de um usuário

Cada número de telefone ativo deve ter um local de emergência associado ao atribuir o número de telefone a um usuário. (Você associa o endereço quando recebe um número de telefone no Office 365 ou quando transfere um número de telefone.) Ao associar o número a um local de emergência, você também pode adicionar um local para fornecer um local mais exato em um local físico. Um local pode ser o andar, o asa do prédio ou o número do escritório onde o usuário está localizado. Você pode ter um número ilimitado de locais para um determinado local de emergência, e você pode alterar o local se o usuário se mover para um escritório ou prédio diferente. Por exemplo, se o usuário se move do andar 34 para o andar 35.
  
Para saber como obter planos de chamada e quanto eles custam, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
Você pode atribuir ou alterar o local de uma localização de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em números de telefone de **voz**  >  **Phone numbers**.

2. Na página **números de telefone** , selecione um número de usuário na lista e clique em **Editar**.

3. No painel **Editar** , em **local de emergência**, siga um destes procedimentos:

    - Para atribuir um local, procure o local ou o local e selecione o local nos resultados da pesquisa.

    - Para alterar o local que já está atribuído ao usuário, clique em **X** para remover o local e o local existentes, procure e selecione o local que você deseja atribuir.

4. Clique em **Salvar**.

## <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Atribuir ou alterar um local de emergência para um usuário](assign-change-emergency-location-user.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)
