---
title: Configurar a licença do Common Area Phone
ms.author: danismith
author: DaniEASmith
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
- admindeeplinkMAC
- admindeeplinkTEAMS
description: Saiba como configurar o Common Area Phones para lo lobbys, áreas de recepção e salas de conferência.
ms.openlocfilehash: 74809ffdf4f11b91584f770e7dc817543fccc98e
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475503"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Configurar telefones de área comuns para o Microsoft Teams

Um telefone de área comum normalmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada: uma área de recepção, lobby ou telefone de conferência. Telefones de área comuns são conectados com contas vinculadas a **uma licença do Common Area Phone** .

Este artigo fornece uma visão geral de como implantar e configurar dispositivos de telefone do Teams como telefones de área comuns para espaços compartilhados. Para obter uma experiência de sala de reunião mais completa, incluindo audioconferência, considere  comprar uma licença de Salas do Teams dedicada com um Salas do Teams dispositivo.

## <a name="overview"></a>Visão geral

A **licença do Common Area Phone** dá suporte a:

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

&sup1; Anteriormente conhecido como *Sistema de Telefonia*.
&sup2; Telefones de área comuns podem ingressar em conferências de áudio por meio de um número de discagem fornecido pelo organizador da reunião.
&sup3; Somente recursos de caixa postal baseados em nuvem.

> [!NOTE]
> Contas para objetos de telefones de área comuns criados Skype for Business Server não podem ser migradas para o Microsoft Teams. Siga as etapas neste artigo para recriar essas contas para o Teams e, se necessário, migre sua conectividade PSTN (Rede Telefônica Pública Comuada).

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

Primeiro, você precisa comprar uma licença **CAP (Telefone** de Área Comum) e certificar-se de ter um telefone certificado. Para pesquisar e saber mais sobre telefones certificados, acesse os [dispositivos do Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. No [Centro de administração do Microsoft 365,](https://go.microsoft.com/fwlink/p/?linkid=2024339) vá para os **serviços de** > **Compra de Cobrança**.

2. Se a **seção Exibir por** categoria ainda não estiver exibida, vá para Comprar da **Microsoft** e selecione **Exibir produtos**. Em seguida, **selecione Colaboração e comunicação**.  

3. Na lista de produtos, **localize o Telefone de Área Comum** e selecione **Detalhes**.

4. Insira o número de licenças necessárias e selecione **Comprar**.

> [!NOTE]
> Se você estiver usando o Intune em seu ambiente e tiver regras de acesso condicional que exigem conformidade do dispositivo, será necessário atribuir uma licença do **Azure Active Directory Premium Plano 1** e uma licença **do Intune** à conta do dispositivo para o telefone de área comum.
>
> Telefones de área comuns podem ser afetados por regras de acesso condicional e outras configurações de identidade, como a Autenticação Multifator. Confira [as práticas recomendadas de autenticação para dispositivos Android do Teams](devices/authentication-best-practices-for-android-devices.md) para saber mais.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Etapa 2 – Criar uma nova conta de usuário e atribuir licenças

### <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Se você estiver implantando mais de um telefone de área comum ao mesmo tempo, saiba como criar contas e atribuir licenças [usando o PowerShell](#using-powershell).

Se você estiver implantando um dispositivo:

1. No [Centro de administração do Microsoft 365,](https://go.microsoft.com/fwlink/p/?linkid=2024339) vá para **Usuários** > **Ativos Adicionar** > **um usuário**.

2. Insira um nome de usuário `Main` como o nome e `Reception` o segundo nome.

3. Insira um nome de exibição se ele não gerar automaticamente um como `Main Reception`.

4. Insira um nome de usuário como `MainReception` ou `Mainlobby`.

5. Defina manualmente a senha para seu telefone de área comum. Para definir a senha, desmarque Automaticamente **criar** uma senha e exija que esse usuário altere a **senha ao entrar pela primeira vez**.  

    > [!IMPORTANT]
    > Configurar manualmente uma senha para telefones de área comum é altamente recomendável para evitar problemas de entrada para seus usuários finais.

6. Selecione o local de uso do dispositivo e atribua a **licença do Common Area Phone** à conta. Se outras licenças forem necessárias, como Planos de Chamadas, atribua-as.

> [!NOTE]
> Você não precisa adicionar uma licença com recursos do Sistema de Telefonia. Ela está incluída na licença do **Telefone da Área Comum**.
>
> Se você não estiver usando o Sistema de Telefonia da Microsoft com Roteamento Direto ou Conexão de Operador, convém adicionar licenças de **Planos** de Chamadas. Para obter mais informações sobre licenças, consulte [licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell quando quiser criar e atribuir licenças para mais de uma conta de usuário de uma vez. Para obter mais informações, consulte Criar contas de usuário do [Microsoft 365 com o PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) e atribuir [licenças do Microsoft 365 a contas de usuário com o PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>Etapa 3 – Definir políticas para telefones de área comum

Use políticas para controlar quais recursos estão disponíveis para os usuários em telefones de área comum.

### <a name="ip-phone-policies"></a>Políticas de telefone IP

Usando a política de Telefone IP do Teams, defina o parâmetro [SignInMode](/powershell/module/skype/new-csteamsipphonepolicy#parameters) `CommonAreaPhoneSignIn` para habilitar a experiência de telefone de área comum no dispositivo de telefone do Teams.

Para configurar outros parâmetros, considere criar uma [política de telefone IP](/powershell/module/skype/new-csteamsipphonepolicy). Por exemplo, se um telefone de área comum for usado em uma área pública, defina uma política de telefone IP para restringir a pesquisa no Catálogo de Endereços Global da sua organização e bloquear o hot-desking. Para saber mais, confira [Definir a interface do usuário de dispositivos Android do Teams](/microsoftteams/devices/Teams-Android-devices-user-interface).

### <a name="calling-policies"></a>Políticas de chamadas

Use políticas de chamada para habilitar chamadas privadas, usando encaminhamento de chamadas ou toque simultâneo em telefones de área comum. Para saber mais, confira [Chamadas e encaminhamento de chamadas no Teams](teams-calling-policy.md).

Por padrão, o estacionamento de chamadas não está habilitado para telefones de área comum. Você precisará criar uma política para habilita-la. Para saber mais, consulte [Estacionamento de chamada e recuperar no Microsoft Teams](call-park-and-retrieve.md).

> [!NOTE]
> Depois de atribuir uma política, saia do telefone e entre novamente. Pode levar até uma hora para que uma atribuição de política entre em vigor.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Etapa 4 – Adquirir e atribuir números de telefone

Consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md) para saber como adquirir e atribuir números de telefone com base em sua opção de conectividade PSTN.

## <a name="step-5---sign-in"></a>Etapa 5 – Entrar

Depois de criar e configurar uma conta de usuário, você pode entrar em um telefone. Dependendo de quantos telefones você estiver implantando, você terá três opções de entrada:

- [Entrada local](#local-sign-in).
- [Entre de outro dispositivo](#sign-in-from-another-device).
- [Entre usando o centro de administração do Teams](#sign-in-using-the-teams-admin-center).

### <a name="local-sign-in"></a>Entrada local

Para entrar localmente com um nome de usuário e senha:

1. Ligue o telefone de área comum.
2. Selecione **Entrar neste dispositivo**.
3. Siga as instruções de entrada no dispositivo. Depois de conectado, o telefone exibirá a experiência de usuário de telefone de área comum.

> [!NOTE]
> Se você estiver usando uma política de configuração personalizada que desafixa o aplicativo de chamada, o teclado de discagem não aparecerá no telefone de área comum. Para obter mais informações sobre as políticas de configuração do Teams, consulte [Gerenciar políticas de configuração de aplicativo no Microsoft Teams](teams-app-setup-policies.md).

### <a name="sign-in-from-another-device"></a>Entrar de outro dispositivo

Você também pode entrar em um telefone de área comum de outro dispositivo usando um código. Ao entrar dessa forma, você inserirá o nome de usuário e a senha em outro dispositivo, em vez de no próprio telefone.

1. Em seu telefone de área comum, localize o código exibido na tela de entrada.
2. Em outro dispositivo, vá para [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin).
3. Insira o código e siga as instruções para concluir a entrada.

### <a name="sign-in-using-the-teams-admin-center"></a>Entrar usando o centro de administração do Teams

Como administrador, você pode provisionar e entrar remotamente em telefones de área comum do centro [de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). Esse método é o método de entrada mais eficiente quando você está implantando um grande número de telefones ao mesmo tempo. Confira [o provisionamento remoto e entre em dispositivos Android do Teams](devices/remote-provision-remote-login.md) para saber mais.

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>Etapa 6 – Configurar chamadas avançadas em telefones de área comum (opcional)

Por padrão, a experiência básica de chamada estará na tela inicial do telefone de área comum, mas você pode ativar uma experiência de chamada avançada.

Os seguintes recursos avançados de chamada estão disponíveis para modelos de dispositivos de telefone do Teams com suporte com uma licença do **Common Area Phone** e as atualizações mais recentes do Teams (versão mínima: 1449/1.0.94.2022061702):

- [Ligue para o parque e recupere](call-park-and-retrieve.md).
- [Caixa postal baseada em nuvem Exchange Online Plano 2](set-up-phone-system-voicemail.md).
  - Para desabilitar a caixa postal baseada em nuvem, confira as configurações do usuário [da Caixa Postal usando o PowerShell](/powershell/module/skype/set-csonlinevoicemailusersettings).
- [Chamar filas](create-a-phone-system-call-queue.md).
- [Atendedores automáticos](create-a-phone-system-auto-attendant.md).
- [Pick-up de chamada em grupo](call-sharing-and-group-call-pickup.md).
- [Regras de encaminhamento](teams-calling-policy.md).

Para usar esses recursos avançados de chamada em modelos de dispositivos de telefone do Teams com suporte,  você pode ativar a alternância chamadas avançadas no centro de administração do [Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) ou em seu dispositivo de telefone do Teams que está conectado à sua conta do Telefone de Área Comum.

Ativar recursos avançados de chamada exige que você compre modelos de hardware que possam dar suporte a todos os recursos necessários.

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Ativar chamadas avançadas no centro de administração do Teams

1. Entre no centro [de administração do Teams](https://admin.teams.microsoft.com/dashboard) com uma conta de administrador do Microsoft 365.
1. No menu do lado esquerdo, navegue até telefones de dispositivos **do Teams** > **> e** selecione a **guia Perfis de configuração** .
1. Na lista, selecione o perfil de configuração atribuído ao telefone de área comum.
1. Na seção **Configurações de chamada** , localize a **alternância Chamada** Avançada.
1. Ative o botão de alternância.
1. Na parte inferior da página, selecione o **botão** Salvar.

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Ativar chamadas avançadas de um dispositivo de telefone do Teams

1. Depois de entrar em seu dispositivo de telefone do Teams, navegue até **Configurações** >  >  do dispositivo **Administração somente Chamada** > .
1. Localize **o botão de alternância** Chamada Avançada e ative-o.

## <a name="next-steps"></a>Próximas etapas

Agora que você configurou e entrou em telefones de área comuns para sua organização, você pode gerenciá-los no Centro de administração do Teams. Consulte [o Microsoft Teams: Gerenciando seus dispositivos](devices/device-management.md) para saber mais.

## <a name="related-articles"></a>Artigos relacionados

- [Atualize os dispositivos do Microsoft Teams remotamente](devices/remote-update.md).
- [Gerenciar marcas de dispositivo do Microsoft Teams](devices/manage-device-tags.md).
- [Monitoramento de integridade de dispositivos do Microsoft Teams](alerts/device-health-status.md).
