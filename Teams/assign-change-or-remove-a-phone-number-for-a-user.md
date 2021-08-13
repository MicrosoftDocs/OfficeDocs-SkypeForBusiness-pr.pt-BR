---
title: Atribuir, alterar ou remover o número de telefone de um usuário
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Saiba como atribuir, alterar ou remover um número de telefone de trabalho para seus usuários Teams para que empresas e clientes externos possam chamar.
ms.openlocfilehash: 443fdb5833e657c3f45c0f53d1d4ce6744bd67b0b83247e72084e3d29f6c1bc7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320024"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Atribuir, alterar ou remover um número de telefone para um usuário (Planos de Chamadas)

Ao configurar Planos de Chamadas, atribua números de telefone aos usuários. Em Microsoft Teams, o número de telefone atribuído é listado quando um usuário clica em **Chamadas**. Para obter instruções sobre como atribuir, alterar ou remover um número de telefone de um usuário em um cenário de Roteamento Direto, consulte [Enable users for Direct Routing, voice, and voicemail](./direct-routing-enable-users.md).

![Número de telefone do usuário exibido em Teams.](media/teams-phone-number.png)

Quando você estiver configurando usuários para que eles possam fazer e receber chamadas telefônicas, primeiro você deve usar o centro de administração Microsoft Teams e atribuir um número de telefone. Você pode alterar ou remover o número de telefone se precisar.
  
Para saber como obter Planos de Chamada em Teams e quanto eles custam, consulte [Teams licenciamento de complemento.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
> [!NOTE]
> Uma maneira de ver se um usuário tem uma licença atribuída é indo para o Microsoft Teams de administração > **Usuários**. Se uma licença for atribuída, ela será indicada na página.  Você também pode usar o Centro de administração do Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Atribuir um número de telefone a um usuário
 
![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**
    
1. Na navegação à esquerda, clique **em Voz Telefone**  >  **números**.
2. Na página **Telefone números,** selecione um número não atribuído na lista e clique em **Editar**.  
3. No painel **Editar,** em **Atribuído** a , procure o usuário por nome de exibição ou nome de usuário e clique em **Atribuir**.
4. Para atribuir ou alterar o local de emergência associado, em **Local de** emergência, procure e selecione o local.
5. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desativar ou ativar o usuário de email com informações **de número de telefone**. Por padrão, isso está em. 
6. Clique em **Salvar**.

Para um exemplo do PowerShell, consulte [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Alterar um número de telefone para um usuário
 
![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**
    
1. Na navegação à esquerda, clique em **Usuários,** localize e clique duas vezes no usuário que você deseja, clique em Conta **e** em Informações **Gerais,** anote o número de telefone atribuído ao usuário.
2. Na navegação à esquerda, clique **em Voz Telefone**  >  **números**.
3. Na página **Telefone números,** selecione o número identificado na etapa 1 e clique em **Editar**.  
4. No painel **Editar,** em **Atribuído** a , clique no **X** para remover o usuário.
5. Clique em **Salvar**.
6. Na página **Telefone números,** selecione um número não atribuído na lista e clique em **Editar**.  
7. No painel **Editar,** em **Atribuído** a , procure o usuário por nome de exibição ou nome de usuário e clique em **Atribuir**.
8. Para atribuir ou alterar o local de emergência associado, em **Local de** emergência, procure e selecione o local.
9. Clique em **Salvar**.

Para um exemplo do PowerShell, consulte [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="remove-a-phone-number-from-a-user"></a>Remover um número de telefone de um usuário
 
![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários,** localize e clique duas vezes no usuário que você deseja, clique em Conta **e** em Informações **Gerais,** anote o número de telefone atribuído ao usuário.
2. Na navegação à esquerda, clique **em Voz Telefone**  >  **números**.
3. Na página **Telefone números,** selecione o número identificado na etapa 2 e clique em **Editar**.  
4. No painel **Editar,** em **Atribuído** a , clique no **X** para remover o usuário.
5. Clique em **Salvar**.

Para um exemplo do PowerShell, consulte [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="related-topics"></a>Tópicos relacionados

[O que é validação de endereço?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Planos de chamada para Microsoft 365](./calling-plans-for-office-365.md)