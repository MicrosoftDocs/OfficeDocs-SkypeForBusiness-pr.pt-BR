---
title: Atribuir, alterar ou remover o número de telefone de um usuário
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Saiba como atribuir, alterar ou remover um número de telefone de trabalho para seus usuários Teams para que empresas e clientes externos possam chamar.
ms.openlocfilehash: 5e8041ce0a8cc95549a9dc75c0c8d74cd2438e1c
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579511"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Atribuir, alterar ou remover o número de telefone de um usuário

Ao configurar planos de chamadas ou Conexão operador, atribua números de telefone aos usuários. Em Microsoft Teams, o número de telefone atribuído é listado quando um usuário clica em **Chamadas**. 

Este artigo se aplica a Planos de Chamada e Conexão. Para obter informações sobre como atribuir, alterar ou remover um número de telefone de um usuário em um cenário de Roteamento Direto, consulte [Enable users for Direct Routing, voice, and voicemail](./direct-routing-enable-users.md).

Antes de atribuir um número para um usuário Conexão plano de chamada ou operador, você deve obter números para seus usuários. Para obter mais informações, [consulte Obter números para usuários do](getting-phone-numbers-for-your-users.md) Plano de Chamada ou Configurar números para [operadores Conexão usuários](operator-connect-configure.md#set-up-phone-numbers).

  
> [!NOTE]
> Uma maneira de ver se um usuário tem uma licença atribuída é indo para o Microsoft Teams de administração > **Usuários**. Se uma licença for atribuída, ela será indicada na página.  Você também pode usar o Centro de administração do Microsoft 365.

> [!NOTE]
> Esta observação se aplica aos clientes que têm uma implantação híbrida com um Active Directory local. Se você deseja atribuir um plano de chamada ou um número de telefone de operador Conexão a um usuário ou conta de recurso, certifique-se de que o número de telefone no Active Directory local foi removido e que a alteração foi sincronizada com Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Atribuir um número de telefone a um usuário

Ao atribuir um número de telefone a um usuário, certifique-se de que o número de telefone e o local de uso do usuário sejam do mesmo país.

Para atribuir um número usando o Teams de administração:
    
1. Na navegação à esquerda, clique **em Voz Telefone**  >  **números**.

2. Na página **Telefone números,** selecione um número não atribuído na lista e clique em **Editar**.  

3. No painel **Editar,** em **Atribuído** a , procure o usuário por nome de exibição ou nome de usuário e clique em **Atribuir**.

4. Para atribuir ou alterar o local de emergência associado, em **Local de** emergência, procure e selecione o local.

   > [!NOTE]
   > Se você estiver atribuindo números a usuários Conexão operadores, poderá ou não ser capaz de atribuir ou alterar o local de emergência associado. Essa funcionalidade dependerá do operador. Entre em contato com seu Operador para obter mais informações.

5. Dependendo se você deseja enviar um email para o usuário com suas informações de número de telefone, desativar ou ativar o usuário de email com informações **de número de telefone**. Por padrão, isso está em. 

6. Clique em **Salvar**.

Para atribuir números usando o PowerShell, use o cmdlet [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser) da seguinte forma:


''PowerShell Set-CsOnlineVoiceUser -Identity <user>   -TelephoneNumber <phone number> 
```

For example:

```PowerShell
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

> [!NOTE]
> Devido à latência entre Microsoft 365 e Teams, pode levar até 24 horas para que os usuários sejam habilitados. Se o número de telefone não for atribuído corretamente após 24 horas, [consulte Telefone Central de Serviços de Número.](https://pstnsd.powerappsportals.com/) 

  
## <a name="change-a-phone-number-for-a-user"></a>Alterar um número de telefone para um usuário

Para alterar um número de telefone para um usuário usando o Teams de administração:
    
1. Na navegação à esquerda, clique em **Usuários,** localize e clique duas vezes no usuário que você deseja, clique em Conta **e** em Informações **Gerais,** anote o número de telefone atribuído ao usuário.

2. Na navegação à esquerda, clique **em Voz Telefone**  >  **números**.

3. Na página **Telefone números,** selecione o número identificado na etapa 1 e clique em **Editar**.  

4. No painel **Editar,** em **Atribuído** a , clique no **X** para remover o usuário.

5. Clique em **Salvar**.

6. Na página **Telefone números,** selecione um número não atribuído na lista e clique em **Editar**.  

7. No painel **Editar,** em **Atribuído** a , procure o usuário por nome de exibição ou nome de usuário e clique em **Atribuir**.

8. Para atribuir ou alterar o local de emergência associado, em **Local de** emergência, procure e selecione o local.

      > [!NOTE]
      > Se você estiver alterando números para usuários Conexão operadores, poderá ou não ser capaz de atribuir ou alterar o local de emergência associado. Essa funcionalidade dependerá do operador. Entre em contato com seu Operador para obter mais informações.

9. Clique em **Salvar**.

Para um exemplo do PowerShell, consulte [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

## <a name="remove-a-phone-number-from-a-user"></a>Remover um número de telefone de um usuário

Para remover um número de telefone usando o Teams de administração:

1. Na navegação à esquerda, clique em **Usuários,** localize e clique duas vezes no usuário que você deseja, clique em Conta **e** em Informações **Gerais,** anote o número de telefone atribuído ao usuário.

2. Na navegação à esquerda, clique **em Voz Telefone**  >  **números**.

3. Na página **Telefone números,** selecione o número identificado na etapa 2 e clique em **Editar**.  

4. No painel **Editar,** em **Atribuído** a , clique no **X** para remover o usuário.

5. Clique em **Salvar**.

Para um exemplo do PowerShell, consulte [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

## <a name="related-topics"></a>Tópicos relacionados

[O que é validação de endereço?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

