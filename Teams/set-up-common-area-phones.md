---
title: Configurar a licença do Common Area Phone
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
description: 'Saiba como configurar o Common Area Phones para lo lobbys, áreas de recepção e salas de conferência '
ms.openlocfilehash: a4a0f5a0a0436a1ea8e81cac8c288de483c24896
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705860"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Implantar telefones de área comuns para o Microsoft Teams

Um telefone de área comum normalmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, lobby ou telefone de conferência. Telefones de área comuns são conectados com contas vinculadas a uma licença do Common Area Phone.

Este artigo fornece uma visão geral de como implantar e configurar telefones do Teams como telefones de área comuns para espaços compartilhados. Para obter uma experiência de sala de reunião mais completa, incluindo audioconferência, considere comprar a licença dedicada da Sala de Reunião com um dispositivo de sala de reunião.

## <a name="overview"></a>Visão geral

A licença do Common Area Phone dá suporte a:

|                                           | Telefone de Área Comum                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams Phone**  &sup1;                   | &#x2714;                                          |
| **Audioconferência**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premium Plano 1** | &#x2714;                                          |
| **Exchange Online Plano 2**                | &#x2714;  &sup3;                                  |
| **Disponibilidade mundial**                | &#x2714;                                          |
| **Disponibilidade de canal**                  | EA, EAS, EES, CSP, Web Direct, GCC, GCC-High, DoD |

&sup1; Anteriormente conhecido como Sistema de Telefonia.

&sup2; Os Telefones de Área Comuns podem ingressar em conferências de áudio por meio de um número de discagem fornecido pelo organizador da reunião.  

&sup3; Somente recursos de caixa postal baseados em nuvem.

>[!NOTE]
> Contas para objetos de telefones de área comuns criados Skype for Business Server não podem ser migradas para o Microsoft Teams. Siga as etapas neste artigo para recriar essas contas para o Teams e, se necessário, migre sua conectividade PTSN.

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

Primeiro, você precisa comprar uma licença CAP (Telefone de Área Comum) e certificar-se de ter um telefone certificado. Para pesquisar e saber mais sobre telefones certificados, acesse os [dispositivos do Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. No Centro de administração do Microsoft 365, vá para os **serviços de****Compra de** >  Cobrança. 

2. Se a **seção Exibir por** categoria ainda não estiver exibida, vá para Comprar da **Microsoft** e selecione **Exibir produtos**. Em seguida, **selecione Colaboração e comunicação**.  

3. Na lista de produtos, **localize o Telefone de Área Comum** e selecione **Detalhes**.

4. Insira o número de licenças necessárias e selecione **Comprar**.

>[!NOTE]
>Se você estiver usando o Intune em seu ambiente e tiver regras de acesso condicional que exigem conformidade do dispositivo, será necessário atribuir uma licença do Azure Active Directory Premium Plano 1 e uma licença Intune à conta do dispositivo para o telefone de área comum.
>
>Telefones de área comuns podem ser afetados por regras de acesso condicional e outras configurações de identidade, como a Autenticação Multifator. Confira [as práticas recomendadas de autenticação para dispositivos Android do Teams](devices/authentication-best-practices-for-android-devices.md) para saber mais.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Etapa 2 – Criar uma nova conta de usuário e atribuir licenças

### <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Se você estiver implantando mais de um telefone de área comum ao mesmo tempo, saiba como criar contas e atribuir licenças [usando o PowerShell](#using-powershell).

Se você estiver implantando um dispositivo:

1. No Centro de administração do Microsoft 365, vá para **Usuários** > **Ativos Adicionar** > **um usuário**.

2. Insira um nome de usuário como "Main" para o nome e "Recepção" para o segundo nome.

3. Insira um nome de exibição se ele não gerar automaticamente um como "Recepção Principal".

4. Insira um nome de usuário como "MainReception" ou "Mainlobby".

5. Defina a senha para o telefone de área comum manualmente. Para fazer isso, desmarque Automaticamente **criar uma senha** e exigir que esse usuário altere sua **senha ao entrar pela primeira vez**.  

    >[!Important]
    > Definir uma senha manualmente para telefones de área comum é altamente recomendável para evitar problemas de entrada para seus usuários finais.

6. Selecione o local de uso do dispositivo e atribua a licença do Common Area Phone à conta. Se outras licenças forem necessárias, como Planos de Chamadas, atribua-as.

>[!NOTE]
> Você não precisa adicionar uma licença do Sistema de Telefonia. Ela está incluída na licença do Telefone da Área Comum.
>
>Se você não estiver usando o Roteamento Direto do Sistema de Telefonia da Microsoft ou a Conexão de Operador, convém adicionar licenças de Planos de Chamadas. Para obter mais informações sobre licenças, consulte [licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell quando quiser criar e atribuir licenças para mais de uma conta de usuário de uma vez. Consulte [Criar contas de usuário do Microsoft 365 com o PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) e atribuir [licenças do Microsoft 365](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) a contas de usuário com o PowerShell para obter mais informações.

## <a name="step-3---set-policies-for-common-area-phones"></a>Etapa 3 – Definir políticas para telefones de área comum

Use políticas para controlar quais recursos estão disponíveis para os usuários em telefones de área comum.

>[!NOTE]
>Depois de atribuir uma política, saia do telefone e entre novamente. Pode levar até uma hora para que uma atribuição de política entre em vigor.

### <a name="ip-phone-policies"></a>Políticas de telefone IP

Os telefones conectados com contas que foram atribuídas a uma licença do Common Area Phone exibirão a experiência do usuário de área comum.

Se você quiser substituir a interface padrão de um telefone, considere criar uma [política de telefone IP](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps&preserve-view=true). Por exemplo, se um telefone de área comum for usado em uma área pública, defina uma política de telefone IP para restringir a pesquisa no Catálogo de Endereços Global da sua organização e bloquear o hot-desking. Confira [Definir a interface do usuário de dispositivos Android do Teams](devices/Teams-Android-devices-user-interface.md) para saber mais.

### <a name="calling-policies"></a>Políticas de chamadas

Use políticas de chamada para habilitar chamadas privadas, usando encaminhamento de chamadas ou toque simultâneo em telefones de área comum. Consulte [Chamadas e encaminhamento de chamadas no Teams](teams-calling-policy.md) para saber mais.

Por padrão, o estacionamento de chamadas não está habilitado para telefones de área comum. Você precisará criar uma política para habilita-la. Consulte [Estacionamento de chamada e recuperar no Microsoft Teams](call-park-and-retrieve.md) para saber mais.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Etapa 4 – Adquirir e atribuir números de telefone

Consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md) para saber como adquirir e atribuir números de telefone com base em sua opção de conectividade PSTN.

## <a name="step-5---sign-in"></a>Etapa 5 – Entrar

Depois de criar e configurar uma conta de usuário, você pode entrar em um telefone. Dependendo de quantos telefones você estiver implantando, você terá três opções de entrada:

- [Entrada local](#local-sign-in)
- [Entrar de outro dispositivo](#sign-in-from-another-device)
- [Entrar usando o centro de administração do Teams](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Entrada local

Para entrar localmente com um nome de usuário e senha: 

1. Ativar o telefone de área comum

2. Selecione **Entrar neste dispositivo**

3. Siga as instruções de entrada no dispositivo. Depois de conectado, o telefone exibirá a experiência de usuário de telefone de área comum.

> [!NOTE]
> Se você estiver usando uma política de configuração personalizada que desafixa o aplicativo de chamada, o teclado de discagem não aparecerá no Telefone de Área Comum. Para obter mais informações sobre as políticas de configuração do Teams, consulte [Gerenciar políticas de configuração de aplicativo no Microsoft Teams](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>Entrar de outro dispositivo

Você também pode entrar em um telefone de área comum de outro dispositivo usando um código. Ao entrar dessa forma, você inserirá o nome de usuário e a senha em outro dispositivo, em vez de no próprio telefone.

1. Primeiro, em seu telefone de área comum, procure o código exibido na tela de entrada.

2. Em outro dispositivo, vá para https://www.microsoft.com/devicelogin.

3. Insira o código e siga as instruções para concluir a entrada.

### <a name="sign-in-using-the-teams-admin-center"></a>Entrar usando o centro de administração do Teams

Como administrador, você pode provisionar e entrar remotamente em telefones de área comum do centro de administração do Teams. Esse é o método de entrada mais eficiente quando você está implantando um grande número de telefones ao mesmo tempo. Confira [o provisionamento remoto e entre em dispositivos Android do Teams](devices/remote-provision-remote-login.md) para saber mais.

## <a name="next-steps"></a>Próximas etapas

Agora que você configurou e entrou em telefones de área comuns para sua organização, você pode gerenciá-los no Centro de administração do Teams. Consulte [o Microsoft Teams: Gerenciando seus dispositivos](devices/device-management.md) para saber mais.

## <a name="related-topics"></a>Tópicos relacionados

- [Atualizar dispositivos do Microsoft Teams remotamente](devices/remote-update.md)
- [Gerenciar marcas de dispositivo do Microsoft Teams](devices/manage-device-tags.md)
- [Monitoramento de integridade de dispositivos do Microsoft Teams](alerts/device-health-status.md)
