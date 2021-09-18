---
title: Consulte uma lista de números de telefone em sua organização
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
description: Aprenda a usar o Microsoft Teams de administração para ver uma lista de todos os números de telefone em sua organização e todos os números atribuídos aos usuários ou não atribuídos.
ms.openlocfilehash: 1473a87a190a671d537a958b34e839d53a668f3a
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432483"
---
# <a name="see-a-list-of-telephone-numbers"></a>Consulte uma lista de números de telefone 

Há diferentes tipos de números de telefone que você pode atribuir a usuários ou aplicativos de voz, como [Audioconferência](deploy-audio-conferencing-teams-landing-page.md) ou [Filas de Chamadas.](plan-auto-attendant-call-queue.md) Para obter mais informações, consulte [Manage telephone numbers for your organization](/microsoftteams/manage-phone-numbers-landing-page).

Este artigo se aplica a Planos de Chamada e Conexão. Para obter informações sobre Roteamento Direto, consulte [Configure the telephone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Para ver todos os números de telefone em sua organização

Para ver uma lista de todos os números de telefone em sua organização:

1. Vá para o Microsoft Teams **de administração**.

2. Na navegação à esquerda, vá para **Voz**  >  **Telefone números**.

3. Para exibir os números de telefone atribuídos, consulte a coluna **Status** da Atribuição, que também mostra a que tipo de serviço o número é atribuído.

4. Para filtrar sua exibição, clique no ícone de filtro. No painel **Filtro,** você pode usar a listada para filtrar sua exibição por:

   - **Intervalo de** números definido. Você pode pesquisar pelo número mais baixo ou o número mais alto.

   - Números que começam com um número especificado.

   - Estado **de ativação de número**.

   - Tipo **de número**.

   - Telefone status do **número**.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Para ver todos os números de telefone atribuídos aos usuários

Quando você estiver configurando usuários, talvez você queira apenas ver a lista de números de telefone que já estão atribuídos aos usuários e quais números de telefone estão disponíveis para serem atribuídos a eles.

1. Vá para o Microsoft Teams **de administração**.

2. Na navegação à esquerda, vá para **Voz**  >  **Telefone números**.

    > [!IMPORTANT]
    > Para que você veja **a** opção **Voz** na navegação à esquerda no centro de administração do Microsoft Teams, primeiro compre pelo menos uma licença **do Enterprise E5**, uma licença de complemento Sistema de Telefonia ou uma licença de complemento de **Audioconferência.**

3. Para classificar rapidamente os números para que você possa ver quais são atribuídos, clique no título da coluna Status da **Atribuição.** Ou, você pode clicar no ícone de filtro e filtrar seu ponto de exibição para ver números de telefone que já estão atribuídos a usuários ou números não atribuídos que você pode atribuir a um usuário. Você pode filtrar por:

   - **Atribuído ao usuário**
   - **Atribuído à ponte de conferência** 
   - **Atribuído ao aplicativo Voice (Atendedor Automático/Fila de Chamadas)**
   - **Não atribuído**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Para ver todos os números de telefone atribuídos aos usuários de voz

Quando você estiver configurando usuários em sua organização para fazer e receber chamadas telefônicas, primeiro você deve obter os números de telefone e atribuí-los aos seus usuários. Depois de ter obtido seus números de telefone, talvez você queira ver o status de ativação das atribuições de número.
  
1. Vá para o Microsoft Teams **de administração**.

2. Na navegação à esquerda, vá para **Voz**  >  **Telefone números**.

3. Clique no ícone de filtro para filtrar sua exibição pelo **estado de ativação.** Você pode filtrar por:

   - **Ativado**
   - **Atribuição pendente**
   - **Falha na atribuição**
   - **Atualização pendente**
   - **Falha na atualização**

## <a name="using-the-teams-powershell-module"></a>Usando o módulo Teams PowerShell

Você pode usar o módulo Teams PowerShell para obter as mesmas informações das seções anteriores, mas a versão 1.1.6 ou posterior é necessária, o que inclui a integração do conector Skype for Business Online. Para obter mais informações sobre o módulo, [consulte Microsoft Teams Visão Geral do PowerShell.](teams-powershell-overview.md)

Para ver uma lista de todos os números de telefone que você tem para sua organização, use o cmdlet [Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Por exemplo, para ver cada número de telefone e seu estado, execute o seguinte comando:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Para ver todos os números de telefone atribuídos aos usuários, use o cmdlet [Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Por exemplo, para ver todos os usuários com um número de telefone atribuído, execute o seguinte comando:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md)

[Termos e condições para chamadas de emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)