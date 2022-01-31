---
title: Configurar a licença de Telefone Área Comum
ms.author: czawideh
author: cazawideh
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Saiba como configurar Telefones de Área Comum para lobbies, áreas de recepção e salas de conferência '
ms.openlocfilehash: a4e4720fe7baf58d0da6f00800c61b706ec48516
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279259"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Implantar telefones de área comum para Microsoft Teams

Um telefone de área comum normalmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, lobby ou telefone de conferência. Telefones de área comum são assinados com contas vinculadas a uma licença Telefone Área Comum.

Este artigo fornece uma visão geral de como implantar e configurar telefones Teams como telefones de área comum para espaços compartilhados. Para obter uma experiência de sala de reunião mais completa, incluindo audioconferência, considere comprar a licença de Sala de Reunião dedicada com um dispositivo de sala de reunião.

## <a name="overview"></a>Visão Geral

A licença área comum Telefone suporta: 


| &nbsp;  |  Telefone de Área Comum  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema de Telefonia |    &#x2714; |
|Audioconferência |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilidade Mundial |       &#x2718; &sup2;  |
|Disponibilidade do Canal |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Os Telefones de Área Comum podem ingressar em conferências de áudio por meio do número de discagem fornecido pelo organizador da reunião

&sup2; Não disponível em nuvens soberanas  

>[!NOTE]
> Contas para telefones de área comum Skype for Business Server não podem ser migradas para Microsoft Teams. Siga as etapas deste artigo para recriar essas contas para Teams e, se necessário, migre sua conectividade PTSN.

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

Primeiro, você precisa comprar uma licença de área comum Telefone (CAP) e garantir que você tenha um telefone certificado. Para pesquisar e saber mais sobre telefones certificados, acesse Microsoft Teams [dispositivos](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. No Centro de administração do Microsoft 365, vá para **Serviços BillingPurchase** > . 

2. Se a **seção Exibir por categoria** ainda não estiver exibida, vá para Comprar da **Microsoft** e selecione **Exibir produtos**. Em seguida, **selecione Colaboração e comunicação**.  

3. Na lista de produtos, encontre **Área Comum Telefone** e selecione **Detalhes**.

4. Insira o número de licenças de que você precisa e selecione **Comprar**.

>[!NOTE]
>Se você estiver usando o Intune em seu ambiente e tiver regras de acesso condicional que exigem conformidade do dispositivo, você precisará atribuir uma licença do Azure Active Directory Premium Plano 1 e do Intune à conta do dispositivo para o telefone de área comum.
>
>Telefones de área comum podem ser afetados por regras de acesso condicional e outras configurações de identidade, como Autenticação Multifacional. Consulte [Práticas recomendadas de autenticação para Teams dispositivos Android](devices/authentication-best-practices-for-android-devices.md) para saber mais.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Etapa 2 - Criar uma nova conta de usuário e atribuir licenças

### <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Se você estiver implantando mais de um telefone de área comum ao mesmo tempo, saiba como criar contas e atribuir licenças [usando o PowerShell](#using-powershell).

Se você estiver implantando um dispositivo:

1. Na Centro de administração do Microsoft 365, vá para **UsersActive** >  **UsersAdd** >  um usuário.

2. Insira um nome de usuário como "Main" para o primeiro nome e "Recepção" para o segundo nome.

3. Insira um nome de exibição se ele não gerar automaticamente um como "Recepção Principal".

4. Insira um nome de usuário como "MainReception" ou "Mainlobby".

5. De definir a senha do telefone de área comum manualmente para evitar. Para fazer isso, desmarque **Automaticamente criar** uma senha e exigir que esse usuário altere a senha ao **entrar pela primeira vez**.  

    >[!Important]
    > Definir uma senha manualmente para telefones de área comum é altamente recomendável para evitar problemas de login para seus usuários finais.

6. Selecione o local de uso do dispositivo e atribua a licença Telefone Área Comum à conta. Se quaisquer outras licenças são necessárias, como Planos de Chamada, atribua-as.

>[!NOTE]
> Você não precisa adicionar uma licença Sistema de Telefonia de terceiros. Ela está incluída na licença do Telefone da Área Comum.
>
>Se você não estiver usando Telefone Microsoft roteamento direto do sistema ou Conexão de operador, talvez queira adicionar licenças de Planos de Chamadas. Para obter mais informações sobre licenças, [consulte Microsoft Teams licenciamento de complemento](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell quando quiser criar e atribuir licenças para mais de uma conta de usuário de uma vez. Consulte [Create Microsoft 365 user accounts with PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) and [Assign Microsoft 365 licenses to user accounts with PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) for more information.

## <a name="step-3---set-policies-for-common-area-phones"></a>Etapa 3 - Definir políticas para telefones de área comum

Use políticas para controlar quais recursos estão disponíveis para os usuários em telefones de área comum.

>[!NOTE]
>Depois de atribuir uma política, saia do telefone e entre novamente. Pode levar até uma hora para que uma atribuição de política entre em vigor.

### <a name="ip-phone-policies"></a>Políticas de telefone IP

Telefones assinados com contas que foram atribuídas a uma licença de Telefone área comum exibirão a experiência do usuário de área comum.

Se você quiser substituir a interface padrão de um telefone, considere a criação de uma [política de telefone IP](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps). Por exemplo, se um telefone de área comum for usado em uma área pública, de definir uma política de telefone IP para restringir a pesquisa do Livro de Endereços Global da sua organização e bloquear o hot-desking. Consulte [Definir Teams de usuário de dispositivos Android](devices/Teams-Android-devices-user-interface.md) para saber mais.

### <a name="calling-policies"></a>Políticas de chamadas

Use políticas de chamada para habilitar chamadas privadas, usando encaminhamento de chamadas ou toque simultâneo em telefones de área comum. Consulte [Chamada e encaminhamento de chamada no Teams](teams-calling-policy.md) para saber mais.

Por padrão, o estacionamento de chamada não está habilitado para telefones de área comum. Você precisará criar uma política para habilita-la. Consulte [Estacionamento de chamada e recupere em Microsoft Teams](call-park-and-retrieve.md) para saber mais.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Etapa 4 - Adquirir e atribuir números de telefone

Consulte [Gerenciar números de telefone para sua](manage-phone-numbers-landing-page.md) organização para saber como adquirir e atribuir números de telefone com base em sua opção de conectividade PSTN.

## <a name="step-5---sign-in"></a>Etapa 5 - Entrar

Depois de criar e configurar uma conta de usuário, você pode entrar em um telefone. Dependendo de quantos telefones você estiver implantando, você tem três opções de login:

- [Login local](#local-sign-in)
- [Entrar de outro dispositivo](#sign-in-from-another-device)
- [Entre usando o centro de Teams de administração](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Login local

Para entrar localmente com um nome de usuário e senha: 

1. Ativar o telefone de área comum

2. Selecione **Entrar neste dispositivo**

3. Siga as instruções de entrada no dispositivo. Depois de entrar, o telefone exibirá a experiência de usuário de telefone de área comum.

### <a name="sign-in-from-another-device"></a>Entrar de outro dispositivo

Você também pode entrar em um telefone de área comum de outro dispositivo usando um código. Ao entrar dessa forma, você inserirá o nome de usuário e a senha em outro dispositivo, em vez de no próprio telefone.

1. Primeiro, em seu telefone de área comum, procure o código exibido na tela de login.

2. Em outro dispositivo, vá para https://www.microsoft.com/devicelogin.

3. Insira o código e seguindo as instruções para concluir a entrada.

### <a name="sign-in-using-the-teams-admin-center"></a>Entre usando o centro de Teams de administração

Como administrador, você pode provisioná-los remotamente e entrar em telefones de área comum Teams centro de administração. Esse é o método de login mais eficiente quando você está implantando um grande número de telefones ao mesmo tempo. Consulte [Provisionamento remoto e entre Teams dispositivos Android](devices/remote-provision-remote-login.md) para saber mais.

## <a name="next-steps"></a>Próximas etapas

Agora que você definiu e se inscreveu em telefones de área comum para sua organização, você pode gerenciá-los no centro de administração Teams local. Consulte [Microsoft Teams: Gerenciando seus dispositivos](devices/device-management.md) para saber mais.

## <a name="related-topics"></a>Tópicos relacionados

- [Atualizar Microsoft Teams dispositivos remotamente](devices/remote-update.md)
- [Gerenciar Microsoft Teams de dispositivo](devices/manage-device-tags.md)
- [Microsoft Teams monitoramento de saúde do dispositivo](alerts/device-health-status.md)
