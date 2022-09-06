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
description: Saiba como atribuir, alterar ou remover um número de telefone comercial para seus usuários do Teams para que empresas e clientes externos possam ligar.
ms.openlocfilehash: 1a959fd61200e7718cf1e14586d0060fb0e996ec
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606640"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Atribuir, alterar ou remover o número de telefone de um usuário

Quando você configura planos de chamadas, conexão de operador ou Operadora de Conexão Móvel (versão prévia pública), você atribui números de telefone aos usuários. No Microsoft Teams, o número de telefone que você atribui é listado quando um usuário clica em **Chamadas**.

Este artigo se aplica aos Planos de Chamada, ao Operator Connect e Operadora de Conexão Móvel (versão prévia pública). Para obter informações sobre como atribuir, alterar ou remover um número de telefone de um usuário em um cenário de Roteamento Direto, consulte Habilitar usuários para Roteamento Direto [, voz e](./direct-routing-enable-users.md) caixa postal.

Antes de atribuir um número para um Plano de Chamada, Conexão de Operador ou Operadora de Conexão Móvel usuário, você deve obter números para seus usuários. Para obter mais informações, consulte [Obter números](getting-phone-numbers-for-your-users.md) para usuários do Plano de Chamadas, configurar números para usuários do [Operator Connect](operator-connect-configure.md#set-up-phone-numbers) ou configurar números [para Operadora de Conexão Móvel usuários](operator-connect-mobile-configure.md).

> [!NOTE]
> Uma maneira de ver se um usuário tem uma licença atribuída é acessando o centro de administração do Microsoft Teams > **Usuários**. Se uma licença for atribuída, ela será indicada na página.  Você também pode usar o Centro de administração do Microsoft 365.

> [!NOTE]
> Essa observação se aplica aos clientes que têm uma implantação híbrida com um Active Directory local. Se você quiser atribuir um plano de chamada ou um número de telefone de conexão de operador a um usuário ou conta de recurso, verifique se qualquer número de telefone armazenado no atributo msRTCSIP-Line no objeto de conta de usuário ou recurso no Active Directory local foi removido e se a alteração foi sincronizada com o Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Atribuir um número de telefone a um usuário

Ao atribuir um número de telefone a um usuário, verifique se o número de telefone e o local de uso do usuário são do mesmo país.

Para atribuir um número usando o centro de administração do Teams:

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Para atribuir números usando o PowerShell, use o cmdlet [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) da seguinte maneira:

Para números do Plano de Chamadas:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Para números de Conexão do Operador:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Para Operadora de Conexão Móvel números:

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
> Devido à latência entre o Microsoft 365 e o Teams, pode levar até 24 horas para que os usuários sejam habilitados. Se o número de telefone não for atribuído corretamente após 24 horas, consulte [a Central de Serviços de Número de Telefone](https://pstnsd.powerappsportals.com/).

## <a name="change-a-phone-number-for-a-user"></a>Alterar um número de telefone para um usuário

Para alterar um número de telefone para um usuário usando o Centro de administração do Teams:

1. No painel de navegação esquerdo, clique em **Usuários,** localize e clique duas vezes no usuário desejado, clique em Conta **e, em** Informações **Gerais,** anote o número de telefone atribuído ao usuário.

2. No painel de navegação esquerdo, clique em **Números de Telefone** \> **de Voz**.

3. Na página **Números de** telefone, selecione o número identificado na etapa 1 e clique em **Editar**.

4. No painel **Editar** , em **Atribuído a**, clique no **X** para remover o usuário.

5. Clique em **Salvar**.

6. Na página **Números de** telefone, selecione um número não atribuído na lista e clique em **Editar**.

7. No painel **Editar** , em **Atribuído** a, pesquise o usuário por nome de exibição ou nome de usuário e clique em **Atribuir**.

8. Para atribuir ou alterar o local de emergência associado, em Local de **emergência,** pesquise e selecione o local.

      > [!NOTE]
      > Se você estiver alterando números para o Operator Connect ou Operadora de Conexão Móvel usuários, poderá ou não ser capaz de atribuir ou alterar o local de emergência associado. Essa funcionalidade dependerá do operador. Entre em contato com seu operador para obter mais informações.

9. Clique em **Salvar**.

Para obter um exemplo do PowerShell, [consulte Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Remover um número de telefone de um usuário

Para remover um número de telefone usando o centro de administração do Teams:

1. No painel de navegação esquerdo, clique em **Usuários,** localize e clique duas vezes no usuário desejado, clique em Conta **e, em** Informações **Gerais,** anote o número de telefone atribuído ao usuário.

2. No painel de navegação esquerdo, clique em **Números de Telefone** \> **de Voz**.

3. Na página **Números de** telefone, selecione o número identificado na etapa 2 e clique em **Editar**.

4. No painel **Editar** , em **Atribuído a**, clique no **X** para remover o usuário.

5. Clique em **Salvar**.

Para obter um exemplo do PowerShell, [consulte Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>Tópicos relacionados

[O que é validação de endereço?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
