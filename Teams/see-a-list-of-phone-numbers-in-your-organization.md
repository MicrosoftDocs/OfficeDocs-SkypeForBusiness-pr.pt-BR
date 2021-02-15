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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Saiba como usar o Centro de administração do Microsoft Teams para ver uma lista de todos os números de telefone em sua organização e todos os números atribuídos a usuários ou não atribuídos.
ms.openlocfilehash: 61e1fb59ba5b68aeb2ab2af51b2ef91202e43678
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918897"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Ver uma lista de números de telefone em sua organização

Há diferentes tipos de números de telefone que você pode atribuir a usuários ou outros serviços (números de serviço), como para Audioconferência no Microsoft 365 ou no Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>Para ver uma lista de todos os números de telefone de sua organização

![Um ícone mostrando o logotipo do Teams ](media/teams-logo-30x30.png) **usando o Centro de administração do Microsoft Teams**

1. Vá para o **Centro de administração do Microsoft Teams.**

2. No painel de navegação esquerdo, vá para **números de Telefone** De  >  **Voz.**

    > [!IMPORTANT]
    > Para ver a  opção Voz na navegação à esquerda no Centro de administração do Skype for  Business, primeiro você deve comprar pelo menos uma licença **Enterprise E5,** uma licença de complemento do Sistema de Telefonia ou uma licença de complemento de **AudioConferência.**

3. Para exibir os números de telefone atribuídos, consulte a **coluna Status.**

4. Para filtrar seu exibição, clique no ícone de filtro. No painel **Filtro,** você pode usar a listada para filtrar seu exibição por:

   - **Intervalo de números** que você definiu. Você pode pesquisar pelo número mais baixo ou pelo número mais alto.

   - Números que começam com um número especificado por você.

   - Estado **de ativação de número.**

   - Tipo **de número.**

   - Status do **número de telefone.**

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>Para ver todos os números de telefone que estão atribuídos a usuários

Ao configurar usuários, talvez você queira apenas ver a lista de números de telefone que já estão atribuídos aos usuários e quais números de telefone estão disponíveis para serem atribuídos a eles.
  
![Um ícone mostrando o logotipo do Teams ](media/teams-logo-30x30.png) **usando o Centro de administração do Microsoft Teams**

1. Vá para o **Centro de administração do Microsoft Teams.**

2. No painel de navegação esquerdo, vá para **números de Telefone** De  >  **Voz.**

    > [!IMPORTANT]
    > Para ver a  opção Voz na navegação à esquerda no Centro de administração do Microsoft Teams, primeiro você deve comprar pelo menos uma licença **Enterprise E5,** uma licença de complemento do Sistema de Telefonia ou uma licença de complemento de  **Audioconferência.**

3. Para classificar rapidamente os números para que você possa ver quais são atribuídos, clique no **título da** coluna Status. Ou você pode clicar no ícone de filtro e, em seguida, filtrar sua exibição para ver números de telefone que já estão atribuídos a usuários ou números não atribuídos que você pode atribuir a um usuário. Você pode filtrar por:

   - **Atribuído ao usuário**

   - **Atribuída à ponte de conferência** 

   - **Não atribuído**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>Para ver os números de telefone atribuídos a usuários de voz

Ao configurar usuários em sua organização para fazer e receber chamadas, primeiro você deve obter os números de telefone e, depois, atribuí-los aos usuários. Depois de ter obtido seus números de telefone, talvez você apenas queira ver o status de ativação das atribuições de número.

![Um ícone mostrando o logotipo do Teams ](media/teams-logo-30x30.png) **Usando o Centro de administração do Microsoft Teams!**
  
1. Vá para o **Centro de administração do Microsoft Teams.**

2. No painel de navegação esquerdo, vá para **números de Telefone** De  >  **Voz.**

    > [!IMPORTANT]
    > Para ver a  opção Voz na navegação à esquerda no Centro de administração do Microsoft Teams, primeiro você deve comprar pelo menos uma licença **Enterprise E5,** uma licença de complemento do Sistema de Telefonia ou uma licença de complemento de  **Audioconferência.**

3. Clique no ícone de filtro para filtrar o seu exibição por **Estado** de ativação, você pode filtrar por:

   - **Ativado**

   - **Tarefa pendente**

   - **Falha na atribuição**

   - **Atualização pendente**

   - **Falha na atualização**

## <a name="using-the-teams-powershell-module"></a>Usando o módulo do PowerShell do Teams

Você pode usar o módulo do Teams PowerShell para obter as mesmas informações das seções anteriores, mas a versão 1.1.6 ou posterior é necessária, o que inclui a integração do conector do Skype for Business Online. Para obter mais informações sobre o módulo, consulte [Visão geral do Microsoft Teams PowerShell.](teams-powershell-overview.md)

Você pode ver uma lista de todos os números de telefone que tem para sua organização usando o cmdlet [Get-CsOnlineTelephoneNumber.](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber) Por exemplo, você pode executar o seguinte comando para ver cada número de telefone e seu estado:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Você pode ver todos os números de telefone atribuídos aos usuários usando o cmdlet [Get-CsOnlineUser.](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser) Por exemplo, você pode executar o seguinte comando para ver todos os usuários com um número de telefone atribuído:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser)
