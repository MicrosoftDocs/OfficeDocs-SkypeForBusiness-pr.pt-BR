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
description: Saiba como atribuir, alterar ou remover um número de telefone de trabalho para seus usuários do Teams para que empresas e clientes externos possam chamar.
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414679"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Atribuir, alterar ou remover o número de telefone de um usuário

Ao configurar Planos de Chamada, Conexão de Operador ou Teams Phone Mobile, você atribui números de telefone aos seus usuários. No Microsoft Teams, o número de telefone atribuído é listado quando um usuário clica em **Chamadas**.

Este artigo se aplica a Planos de Chamada, Conexão de Operador e Teams Phone Mobile. Para obter informações sobre como atribuir, alterar ou remover um número de telefone de um usuário em um cenário de Roteamento Direto, consulte [Habilitar usuários para Roteamento Direto, voz e caixa postal](./direct-routing-enable-users.md).

Antes de atribuir um número para um usuário do Plano de Chamada, do Operador Connect ou do Teams Phone Mobile, você deve obter números para seus usuários. Para obter mais informações, confira [Obter números para usuários do Plano de Chamada](getting-phone-numbers-for-your-users.md), [Configurar números para usuários do Operator Connect](operator-connect-configure.md#set-up-phone-numbers) ou [Configurar números para usuários do Teams Phone Mobile](operator-connect-mobile-configure.md).

> [!NOTE]
> Uma maneira de ver se um usuário tem uma licença atribuída é acessando o centro de administração do Microsoft Teams > **Usuários**. Se uma licença for atribuída, ela será indicada na página.  Você também pode usar o Centro de administração do Microsoft 365.

> [!NOTE]
> Esta nota se aplica aos clientes que têm uma implantação híbrida com um Active Directory local. Se você quiser atribuir um número de telefone plano de chamada ou conexão de operador a um usuário ou conta de recurso, você deve garantir que qualquer número de telefone armazenado no atributo msRTCSIP-Line no objeto da conta de recurso ou usuário no Active Directory local tenha sido removido e que a alteração tenha sido sincronizada para Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Atribuir um número de telefone a um usuário

Ao atribuir um número de telefone a um usuário, verifique se o número de telefone e o local de uso do usuário são do mesmo país.

Para atribuir um número usando o centro de administração do Teams:

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Para atribuir números usando o PowerShell, use o cmdlet [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) da seguinte maneira:

Para números do Plano de Chamada:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Para números do Operator Connect:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Para números do Teams Phone Mobile:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

Por exemplo:

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```

> [!NOTE]
> Devido à latência entre Microsoft 365 e o Teams, pode levar até 24 horas para que os usuários sejam habilitados. Se o número de telefone não for atribuído corretamente após 24 horas, consulte [Central de Serviço de Número de Telefone](https://pstnsd.powerappsportals.com/).

> [!NOTE]
> Quando você atribui um número de telefone, o sinalizador EnterpriseVoiceEnabled é automaticamente definido como True.

## <a name="change-a-phone-number-for-a-user"></a>Alterar um número de telefone para um usuário

Para alterar um número de telefone para um usuário usando o centro de administração do Teams:

1. Na navegação à esquerda, clique em **Usuários**, localize e clique duas vezes no usuário desejado, clique em **Conta** e, em **informações gerais**, anote o número de telefone atribuído ao usuário.

2. Na navegação à esquerda, clique em **Números de Telefone de** **Voz**\>.

3. Na página **Números de telefone** , selecione o número que você identificou na etapa 1 e clique em **Editar**.

4. No painel **Editar** , em **Atribuído a**, clique no **X** para remover o usuário.

5. Clique em **Salvar**.

6. Na página **Números de telefone** , selecione um número não atribuído na lista e clique em **Editar**.

7. No painel **Editar** , em **Atribuído,** pesquise o usuário pelo nome de exibição ou nome de usuário e clique em **Atribuir**.

8. Para atribuir ou alterar o local de emergência associado, em **Local de emergência**, pesquise e selecione o local.

      > [!NOTE]
      > Se você estiver alterando números para usuários do Operator Connect ou do Teams Phone Mobile, poderá ou não ser capaz de atribuir ou alterar o local de emergência associado. Essa funcionalidade dependerá do operador. Entre em contato com o operador para obter mais informações.

9. Clique em **Salvar**.

Para obter um exemplo do PowerShell, consulte [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Remover um número de telefone de um usuário

Para remover um número de telefone usando o centro de administração do Teams:

1. Na navegação à esquerda, clique em **Usuários**, localize e clique duas vezes no usuário desejado, clique em **Conta** e, em **informações gerais**, anote o número de telefone atribuído ao usuário.

2. Na navegação à esquerda, clique em **Números de Telefone de** **Voz**\>.

3. Na página **Números de telefone** , selecione o número que você identificou na etapa 2 e clique em **Editar**.

4. No painel **Editar** , em **Atribuído a**, clique no **X** para remover o usuário.

5. Clique em **Salvar**.

Para obter um exemplo do PowerShell, consulte [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>Tópicos relacionados

[O que é validação de endereço?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de isenção de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
