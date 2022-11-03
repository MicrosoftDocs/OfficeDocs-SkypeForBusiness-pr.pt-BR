---
title: Configurar a licença de Telefone da Área Comum
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
description: Saiba como configurar telefones de área comum para lobbies, áreas de recepção e salas de conferência.
ms.openlocfilehash: 2a282526a0592c46c053e9c0319112a9238a6051
ms.sourcegitcommit: 92a0df6fc3aa62cec1bf72a40690fb8e16226965
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "68836745"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Configurar telefones de área comum para o Microsoft Teams

Um telefone de área comum normalmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas para fazer uma chamada: uma área de recepção, lobby ou telefone de conferência. Os telefones de área comum são conectados com contas vinculadas a uma licença **de Telefone da Área Comum** .

Este artigo fornece uma visão geral de como implantar e configurar dispositivos telefônicos do Teams como telefones de área comuns para espaços compartilhados. Para uma experiência mais completa da sala de reunião, incluindo a conferência de áudio, considere comprar uma licença de **Salas do Teams** dedicada com um dispositivo Salas do Teams. Para obter mais informações sobre Salas do Teams, consulte [Salas do Microsoft Teams](rooms/index.md).

## <a name="overview"></a>Visão geral

A licença **common area phone** dá suporte a:

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

&sup1; Anteriormente conhecido como *Sistema telefônico*.
&sup2; Os telefones de área comum podem participar de conferências de áudio por meio de um número discado fornecido pelo organizador da reunião.
&sup3; Somente recursos de caixa postal baseados em nuvem.

> [!NOTE]
> Contas de objetos de telefones de área comuns criados em Skype for Business Server não podem ser migradas para o Microsoft Teams. Siga as etapas deste artigo para recriar essas contas para o Teams e, se necessário, migre sua conectividade PSTN (Rede Telefônica Comutada Pública).

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

Primeiro, você precisa comprar uma licença do CAP ( **Common Area Phone** ) e garantir que você tenha um telefone certificado. Para pesquisar e saber mais sobre telefones certificados, acesse [dispositivos do Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. No [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), acesse **Serviços de Compra de Cobrança** > .

2. Se a seção **Exibição por categoria** ainda não estiver exibida, acesse **Comprar da Microsoft** e selecione **Exibir produtos**. Em seguida, selecione **Colaboração e comunicação**.  

3. Na lista de produtos, localize **Common Area Phone** e selecione **Detalhes**.

4. Insira o número de licenças necessárias e selecione **Comprar**.

> [!NOTE]
> Se você estiver usando Intune em seu ambiente e tiver regras de acesso condicional que exigem a conformidade do dispositivo, precisará atribuir um **Azure Active Directory Premium Plano 1** e **Intune** licença à conta do dispositivo para o telefone de área comum.
>
> Os telefones de área comum podem ser afetados por regras de acesso condicional e outras configurações de identidade, como Autenticação Multifator. Confira [Práticas recomendadas de autenticação para dispositivos Android do Teams](devices/authentication-best-practices-for-android-devices.md) para saber mais.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Etapa 2 – Criar uma nova conta de usuário e atribuir licenças

### <a name="using-the-microsoft-365-admin-center"></a>Usando o Centro de administração do Microsoft 365

Se você estiver implantando mais de um telefone de área comum ao mesmo tempo, saiba como criar contas e atribuir licenças [usando o PowerShell](#using-powershell).

Se você estiver implantando um dispositivo:

1. No [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), acesse **Usuários Ativos Usuários** >  > **Adicionam um usuário**.

2. Insira um nome de usuário como `Main` para o primeiro nome e `Reception` para o segundo nome.

3. Insira um nome de exibição se ele não habilitar automaticamente um como `Main Reception`.

4. Insira um nome de usuário como `MainReception` ou `Mainlobby`.

5. Defina manualmente a senha para seu telefone de área comum. Para definir a senha, desmarque **Criar automaticamente uma senha** e **exigir que esse usuário altere sua senha quando entrar pela primeira vez**.  

    > [!IMPORTANT]
    > A configuração manual de uma senha para telefones de área comum é altamente recomendada para evitar problemas de entrada para seus usuários finais.

6. Selecione o local de uso do dispositivo e atribua a licença **common area phone** à conta. Se quaisquer outras licenças forem necessárias, como Planos de Chamadas, atribua-as.

> [!NOTE]
> Você não precisa adicionar uma licença com recursos do Sistema Telefônico. Ela está incluída na licença do **Telefone da Área Comum**.
>
> Se você não estiver usando o Microsoft Phone System com o Roteamento Direto ou o Operator Connect, talvez queira adicionar licenças **de Planos de Chamada** . Para obter mais informações sobre licenças, consulte [Licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use o PowerShell quando quiser criar e atribuir licenças para mais de uma conta de usuário ao mesmo tempo. Para obter mais informações, confira [Criar contas de usuário do Microsoft 365 com o PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) e [atribuir licenças do Microsoft 365 a contas de usuário com o PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>Etapa 3 – Definir políticas para telefones de área comum

Use políticas para controlar quais recursos estão disponíveis para usuários em telefones de área comum.

### <a name="ip-phone-policies"></a>Políticas de telefone IP

A política de telefone IP do Teams só poderá ser modificada se a conta que entra no telefone for licenciada com algo diferente de uma licença de Telefone da Área Comum.  Se licenciado com uma assinatura Microsoft 365 E3 ou E5, ou uma assinatura Office 365 Enterprise E1, E3 ou E5, você poderá modificar a política do IP Phone.  Se você estiver usando uma licença da Sala de Reunião em sua conta de telefone de área comum, ela só permitirá que você use o `MeetingRoomSignIn` modo. `MeetingRoomSignIn` O modo não está disponível na maioria dos telefones de área comuns. Para obter mais informações sobre substituições com suporte para a interface do telefone, consulte [Definir a interface do usuário de dispositivos Android do Microsoft Teams](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection). 

Usando a política de telefone IP do Teams, defina o [parâmetro SignInMode](/powershell/module/skype/new-csteamsipphonepolicy#parameters) para `CommonAreaPhoneSignIn` habilitar a experiência de telefone de área comum no dispositivo de telefone do Teams.

Para configurar outros parâmetros, considere criar uma [política de telefone IP](/powershell/module/skype/new-csteamsipphonepolicy). Por exemplo, se um telefone de área comum for usado em uma área pública, defina uma política de telefone IP para restringir a pesquisa no Catálogo de Endereços Global da sua organização e bloquear o hot-desking. Para saber mais, confira [Definir a interface do usuário de dispositivos Android do Teams](/microsoftteams/devices/Teams-Android-devices-user-interface).

### <a name="calling-policies"></a>Políticas de chamadas

Use políticas de chamada para habilitar chamadas privadas, usando encaminhamento de chamadas ou toque simultâneo em telefones de área comum. Para saber mais, confira [Chamada e encaminhamento de chamadas no Teams](teams-calling-policy.md).

Por padrão, o parque de chamadas não está habilitado para telefones de área comum. Você precisará criar uma política para habilitá-la. Para saber mais, confira [Chamar parque e recuperar no Microsoft Teams](call-park-and-retrieve.md).

> [!NOTE]
> Depois de atribuir uma política, saia do telefone e entre novamente. Pode levar até uma hora para que uma atribuição de política entre em vigor.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Etapa 4 – Adquirir e atribuir números de telefone

Consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md) para saber como adquirir e atribuir números de telefone com base na opção de conectividade PSTN.

## <a name="step-5---sign-in"></a>Etapa 5 – Entrar

Depois de criar e configurar uma conta de usuário, você poderá entrar em um telefone. Dependendo de quantos telefones você está implantando, você tem três opções de entrada:

- [Entrada local](#local-sign-in).
- [Entre em outro dispositivo](#sign-in-from-another-device).
- [Entre usando o centro de administração do Teams](#sign-in-using-the-teams-admin-center).

### <a name="local-sign-in"></a>Entrada local

Para entrar localmente com um nome de usuário e senha:

1. Ative o telefone da área comum.
2. Selecione **Entrar neste dispositivo**.
3. Siga as instruções de entrada no dispositivo. Depois de entrar, o telefone exibirá a experiência comum do usuário do telefone da área comum.

> [!NOTE]
> Se você estiver usando uma política de configuração personalizada que desaprova o aplicativo de chamada, o bloco de discagem não aparecerá no telefone da área comum. Para obter mais informações sobre políticas de instalação do Teams, consulte [Gerenciar políticas de configuração de aplicativo no Microsoft Teams](teams-app-setup-policies.md).

### <a name="sign-in-from-another-device"></a>Entrar de outro dispositivo

Você também pode entrar em um telefone de área comum de outro dispositivo usando um código. Ao entrar dessa forma, você inserirá o nome de usuário e a senha em outro dispositivo, em vez de no próprio telefone.

1. Em seu telefone de área comum, localize o código exibido na tela de entrada.
2. Em outro dispositivo, vá para [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin).
3. Insira o código e siga as instruções para concluir a entrada.

### <a name="sign-in-using-the-teams-admin-center"></a>Entrar usando o centro de administração do Teams

Como administrador, você pode provisionar e entrar remotamente em telefones comuns da área do [centro de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). Esse método é o método de entrada mais eficiente quando você está implantando um grande número de telefones ao mesmo tempo. Consulte [Provisionamento remoto e entrar em dispositivos Android do Teams](devices/remote-provision-remote-login.md) para saber mais.

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>Etapa 6 – Configurar chamada avançada em telefones de área comum (opcional)

Por padrão, a experiência básica de chamada estará na tela inicial do telefone da área comum, mas você pode ativar uma experiência avançada de chamada.

Os seguintes recursos avançados de chamada estão disponíveis para modelos de dispositivo de telefone do Teams com suporte com uma licença **do Common Area Phone** e as atualizações mais recentes do Teams (versão mínima: 1449/1.0.94.2022061702):

- [Chame park e recupere](call-park-and-retrieve.md).
- [Caixa postal baseada em nuvem por meio Exchange Online Plano 2](set-up-phone-system-voicemail.md).
  - Para desabilitar a caixa postal baseada em nuvem, consulte [Configurações de usuário do Voicemail usando o PowerShell](/powershell/module/skype/set-csonlinevoicemailusersettings).
- [Filas de chamadas](create-a-phone-system-call-queue.md).
- [Atendentes automáticos](create-a-phone-system-auto-attendant.md).
- [Pick-up de chamada em grupo](call-sharing-and-group-call-pickup.md).
- [Regras de encaminhamento](teams-calling-policy.md).

Para usar esses recursos avançados de chamada em modelos de dispositivo de telefone do Teams com suporte, você pode ativar o alternância **de chamada avançada** no [centro de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) ou no dispositivo de telefone do Teams que está conectado à sua conta do Common Area Phone.

Ativar recursos avançados de chamada exige que você compre modelos de hardware que possam dar suporte a todos os recursos necessários.

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Ativar chamada avançada no centro de administração do Teams

1. Entre no [centro de administração do Teams](https://admin.teams.microsoft.com/dashboard) com uma conta de administrador do Microsoft 365.
1. No menu esquerdo, navegue até **dispositivos do Teams Telefones** >  > e selecione a guia **Perfis de configuração**.
1. Na lista, selecione o perfil de configuração atribuído ao telefone de área comum.
1. Na seção **Configurações de chamada** , localize a alternância **de chamada avançada** .
1. Ative a alternância.
1. Na parte inferior da página, selecione o botão **Salvar** .

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Ativar chamadas avançadas de um dispositivo de telefone do Teams

1. Depois de entrar no dispositivo de telefone do Teams, navegue até **Configurações** > **configurações** >  do dispositivo **Administração apenas** > **Chamando**.
1. Localize a **alternância de chamada avançada** e ative-a.

## <a name="next-steps"></a>Próximas etapas

Agora que você configurou e inscreveu telefones de área comum para sua organização, você pode gerenciá-los no centro de administração do Teams. Confira [Microsoft Teams: gerenciando seus dispositivos](devices/device-management.md) para saber mais.

## <a name="related-articles"></a>Artigos relacionados

- [Atualize dispositivos do Microsoft Teams remotamente](devices/remote-update.md).
- [Gerenciar marcas de dispositivo do Microsoft Teams](devices/manage-device-tags.md).
- [Monitoramento de integridade do dispositivo do Microsoft Teams](alerts/device-health-status.md).
