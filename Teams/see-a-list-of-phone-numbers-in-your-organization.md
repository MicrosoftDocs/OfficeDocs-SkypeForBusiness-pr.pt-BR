---
title: Ver uma lista de números de telefone em sua organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
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
description: Aprenda a usar o Microsoft Teams de administração para ver uma lista de todos os números de telefone em sua organização e todos os números atribuídos aos usuários ou não atribuídos.
ms.openlocfilehash: d7de480508020dac24a63b5923af9cf2481c691b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733970"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Ver uma lista de números de telefone em sua organização

Há diferentes tipos de números de telefone que você pode atribuir a usuários ou outros serviços (números de serviço), como para Audioconferência em Microsoft 365 ou Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>Para ver uma lista de todos os números de telefone de sua organização

![Um ícone mostrando o logotipo Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Vá para o Microsoft Teams **de administração**.

2. Na navegação à esquerda, vá para **Voz**  >  **Telefone números**.

    > [!IMPORTANT]
    > Para que você veja **a** opção **Voz** na navegação à esquerda no centro de administração do Skype for Business, primeiro compre pelo menos uma licença **do Enterprise E5**, uma licença de complemento Sistema de Telefonia ou uma licença de complemento de **Audioconferência.**

3. Para exibir os números de telefone atribuídos, consulte a **coluna Status.**

4. Para filtrar sua exibição, clique no ícone de filtro. No painel **Filtro,** você pode usar a listada para filtrar sua exibição por:

   - **Intervalo de** números definido. Você pode pesquisar pelo número mais baixo ou o número mais alto.

   - Números que começam com um número especificado.

   - Estado **de ativação de número**.

   - Tipo **de número**.

   - Telefone status do **número**.

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>Para ver todos os números de telefone que estão atribuídos a usuários

Quando você estiver configurando usuários, talvez você queira apenas ver a lista de números de telefone que já estão atribuídos aos usuários e quais números de telefone estão disponíveis para serem atribuídos a eles.
  
![Um ícone mostrando o logotipo Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Vá para o Microsoft Teams **de administração**.

2. Na navegação à esquerda, vá para **Voz**  >  **Telefone números**.

    > [!IMPORTANT]
    > Para que você veja **a** opção **Voz** na navegação à esquerda no centro de administração do Microsoft Teams, primeiro compre pelo menos uma licença **do Enterprise E5**, uma licença de complemento Sistema de Telefonia ou uma licença de complemento de **Audioconferência.**

3. Para classificar rapidamente os números para que você possa ver quais são atribuídos, clique no **título da coluna Status.** Ou, você pode clicar no ícone de filtro e, em seguida, filtrar sua exibição para ver números de telefone que já estão atribuídos a usuários ou números não atribuídos que você pode atribuir a um usuário. Você pode filtrar por:

   - **Atribuído ao usuário**

   - **Atribuído à ponte de conferência** 

   - **Não atribuído**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>Para ver os números de telefone atribuídos a usuários de voz

Ao configurar usuários em sua organização para fazer e receber chamadas, primeiro você deve obter os números de telefone e, depois, atribuí-los aos usuários. Depois de ter obtido seus números de telefone, talvez você queira ver o status de ativação das atribuições de número.

![Um ícone mostrando o logotipo Teams.](media/teams-logo-30x30.png) **Usando o Microsoft Teams de administração!**
  
1. Vá para o Microsoft Teams **de administração**.

2. Na navegação à esquerda, vá para **Voz**  >  **Telefone números**.

    > [!IMPORTANT]
    > Para que você veja **a** opção **Voz** na navegação à esquerda no centro de administração do Microsoft Teams, primeiro compre pelo menos uma licença **do Enterprise E5**, uma licença de complemento Sistema de Telefonia ou uma licença de complemento de **Audioconferência.**

3. Clique no ícone de filtro para filtrar seu estado de exibição por **Estado** de ativação Você pode filtrar por:

   - **Ativado**

   - **Atribuição pendente**

   - **Falha na atribuição**

   - **Atualização pendente**

   - **Falha na atualização**

## <a name="using-the-teams-powershell-module"></a>Usando o módulo Teams PowerShell

Você pode usar o módulo Teams PowerShell para obter as mesmas informações das seções anteriores, mas a versão 1.1.6 ou posterior é necessária, o que inclui a integração do conector Skype for Business Online. Para obter mais informações sobre o módulo, [consulte Microsoft Teams Visão Geral do PowerShell.](teams-powershell-overview.md)

Você pode ver uma lista de todos os números de telefone que você tem para sua organização usando o cmdlet [Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Por exemplo, você pode executar o seguinte comando para ver cada número de telefone e seu estado:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Você pode ver todos os números de telefone atribuídos aos usuários usando o cmdlet [Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Por exemplo, você pode executar o seguinte comando para ver todos os usuários com um número de telefone atribuído:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)