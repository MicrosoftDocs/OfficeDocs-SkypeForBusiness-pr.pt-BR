---
title: Ver uma lista de números de telefone em sua organização
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Saiba como usar o Centro de administração do Microsoft Teams para ver uma lista de todos os números de telefone em sua organização e todos os números atribuídos a usuários ou não atribuídos.
ms.openlocfilehash: ac7c63515b34b8c199f8050933b6c3ccbc6f8d33
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606070"
---
# <a name="see-a-list-of-telephone-numbers"></a>Ver uma lista de números de telefone 

Há diferentes tipos de números de telefone que você pode atribuir a usuários ou aplicativos de voz, como [Audioconferência](deploy-audio-conferencing-teams-landing-page.md) ou [Filas de Chamadas](plan-auto-attendant-call-queue.md). Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-landing-page).

Este artigo se aplica aos Planos de Chamada, ao Operator Connect e Operadora de Conexão Móvel (versão prévia pública). Para obter informações sobre Roteamento Direto, [consulte Configurar o número de telefone e habilitar o Enterprise Voice](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Para ver todos os números de telefone em sua organização

Para ver uma lista de todos os números de telefone em sua organização:

1. Vá para o **centro de administração do Microsoft Teams**.

2. No painel de navegação esquerdo, vá para **números de telefone** > **de voz**.

3. Para exibir os números de telefone atribuídos, consulte a coluna **Status** da Atribuição, que também mostra a que tipo de serviço o número é atribuído.

4. Para filtrar o modo de exibição, clique no ícone de filtro. No painel **Filtro** , você pode usar a lista suspensa para filtrar sua exibição por:

   - **Intervalo de números** definido. Você pode pesquisar pelo número mais baixo ou maior.

   - Números que começam com um número especificado.

   - Estado de **ativação de número**.

   - Tipo **de número**.

   - Status do **número de telefone**.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Para ver todos os números de telefone atribuídos aos usuários

Quando você estiver configurando usuários, talvez queira apenas ver a lista de números de telefone que já estão atribuídos aos usuários e quais números de telefone estão disponíveis para serem atribuídos a eles.

1. Vá para o **centro de administração do Microsoft Teams**.

2. No painel de navegação esquerdo, vá para **números de telefone** > **de voz**.

    > [!IMPORTANT]
    > Para ver a opção Voz  no painel de navegação à esquerda no Centro de administração do Microsoft Teams, primeiro você deve comprar pelo menos uma licença **Enterprise E5**,  uma licença de complemento do Sistema de Telefonia ou uma licença de complemento de **Audioconferência**.

3. Para classificar rapidamente os números para que você possa ver quais são atribuídos, clique no título da coluna **Status da Atribuição** . Ou você pode clicar no ícone de filtro e, em seguida, filtrar o modo de exibição para ver os números de telefone que já estão atribuídos a usuários ou números não atribuídos que você pode atribuir a um usuário. Você pode filtrar por:

   - **Atribuído ao usuário**
   - **Atribuído à ponte de conferência** 
   - **Atribuído ao aplicativo de voz (Atendedor Automático/Fila de Chamadas)**
   - **Não atribuído**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Para ver todos os números de telefone atribuídos aos usuários de voz

Ao configurar usuários em sua organização para fazer e receber chamadas telefônicas, primeiro você deve obter os números de telefone e, em seguida, atribuí-los aos usuários. Depois de obter seus números de telefone, talvez você queira ver o status de ativação das atribuições de número.
  
1. Vá para o **centro de administração do Microsoft Teams**.

2. No painel de navegação esquerdo, vá para **números de telefone** > **de voz**.

3. Clique no ícone de filtro para filtrar sua exibição pelo estado **de Ativação**. Você pode filtrar por:

   - **Ativado**
   - **Atribuição pendente**
   - **Falha na atribuição**
   - **Atualização pendente**
   - **Falha na atualização**

## <a name="using-the-teams-powershell-module"></a>Usando o módulo powershell do Teams

Você pode usar o módulo do Teams PowerShell para obter as mesmas informações das seções anteriores, mas a versão 1.1.6 ou posterior é necessária, o que inclui a integração do conector do Skype for Business Online. Para obter mais informações sobre o módulo, consulte [Visão geral do PowerShell do Microsoft Teams](teams-powershell-overview.md).

Para ver uma lista de todos os números de telefone que você tem para sua organização, use o cmdlet [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) . Por exemplo, para ver cada número de telefone, seu tipo e seu estado, execute o seguinte comando:

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

Para ver todos os números de telefone atribuídos aos usuários, use o cmdlet [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) . Por exemplo, para ver todos os usuários com um número de telefone atribuído, execute o seguinte comando:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md)

[Termos e condições para chamadas de emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
