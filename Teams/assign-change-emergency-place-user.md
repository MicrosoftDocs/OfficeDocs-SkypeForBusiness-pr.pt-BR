---
title: Atribuir, alterar locais para locais de emergência para usuários
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
description: Neste artigo, você aprenderá a atribuir ou alterar o local para um local de emergência para usuários em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120823"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Atribuir ou alterar o local para um local de emergência para um usuário

Cada número de telefone ativo deve ter um local de emergência associado quando você atribui o número de telefone a um usuário. (Você associa o endereço quando você tem um número de telefone no Office 365 ou quando você transfere um número de telefone.) Ao associar o número a um local de emergência, você também pode adicionar um local para fornecer um local mais exato em um local físico. Um local pode ser o piso, a asa de construção ou o número do escritório onde o usuário está localizado. Você pode ter um número ilimitado de locais para um determinado local de emergência e pode alterar o local se o usuário mudar para um escritório ou edifício diferente. Por exemplo, se o usuário mudar do piso 34 para o 35º andar.
  
Para saber como obter Planos de Chamada e quanto eles custam, consulte [Licenciamento de complemento do Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
Você pode atribuir ou alterar o local para um local de emergência para um usuário no centro de administração do Microsoft Teams ou usando o PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, clique em **Números de Telefone** de  >  **Voz**.

2. Na página **Números de** telefone, clique na guia **Números,** selecione um número de usuário na lista e clique em **Editar**.

3. No painel **Editar,** em **Local de emergência,** faça um dos seguintes procedimentos:

    - Para atribuir um local, pesquise o local ou o local e selecione o local nos resultados da pesquisa.

    - Para alterar o local já atribuído ao usuário, clique em **X** para remover o local e o local existentes, procure e selecione o local que você deseja atribuir.

4. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desativar ou ativar o usuário de email com informações **de número de telefone**. Por padrão, isso está em.

5. Clique em **Aplicar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Atribuir ou alterar um local de emergência para um usuário](assign-change-emergency-location-user.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)