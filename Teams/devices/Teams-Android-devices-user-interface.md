---
title: Definir a interface do usuário de dispositivos Android do Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
description: Saiba como definir a interface do usuário em dispositivos Android do Teams.
ms.openlocfilehash: 859c1d9d0f7a946f37b53ad81dc2a0637bb26621
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269316"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Definir a interface do usuário de dispositivos Android do Microsoft Teams

Os dispositivos Android do Microsoft Teams podem exibir uma interface do usuário específica com base no tipo de licença atribuída à conta conectada. Você pode substituir esse comportamento e controlar qual interface é mostrada. Este artigo detalha como a interface do usuário padrão é escolhida e como você pode alterar a interface usando uma política do Powershell.

Há três tipos de interfaces do usuário em dispositivos Android do Teams:

1. Usuário
2. Área comum
3. Reunião

Se você atribuir uma licença de usuário a uma conta, como uma licença E3 ou E5, o dispositivo teams exibirá [a](/microsoftteams/user-access) interface do usuário final padrão que é totalmente em destaque para a maioria dos cenários de usuário. No entanto, se um dispositivo estiver executando uma função específica, como um telefone de área comum ou uma sala de reunião, haverá interfaces de usuário específicas para esses usos.

As três imagens a seguir mostram como a interface do usuário muda com base na licença atribuída à conta de usuário. 

## <a name="end-user-interface"></a>Interface do usuário final 

A conta de usuário recebe uma licença E5. Essa é uma licença de usuário, portanto, o dispositivo mostra a interface padrão do usuário final:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interface do modo de usuário.":::

## <a name="common-area-interface"></a>Interface de área comum

Nesta imagem, a conta de usuário foi atribuída a uma [licença do Common Area Phone](/microsoftteams/set-up-common-area-phones). Telefones de área comuns são usados principalmente para fazer e receber chamadas telefônicas. Dessa forma, o teclado de discagem é mostrado no visor:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interface de telefone de área comum.":::

## <a name="meeting-interface"></a>Interface de reunião

Esta imagem mostra uma conta de usuário com [uma Salas do Microsoft Teams Padrão atribuída](/MicrosoftTeams/rooms/rooms-licensing). Salas do Teams licenças devem ser usadas em salas de reunião ou espaços compartilhados, portanto, a interface do usuário muda para facilitar o ingresso em uma reunião mostrando o modo de exibição de calendário:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interface de reunião.":::

> [!NOTE]
> Alterar a interface do usuário não afeta sua capacidade de usar outros recursos licenciados. Por exemplo, mesmo que o modo de exibição padrão da licença de Salas de Equipe seja o modo de exibição de calendário, você ainda poderá fazer e receber chamadas telefônicas PSTN (Rede Telefônica com Opção Pública) se a conta estiver corretamente licenciada e configurada.

> [!IMPORTANT]
> Há outros elementos da interface que mudam. Por exemplo, para impedir que os usuários finais saiam de um telefone de área comum ou dispositivo de sala de reunião, a opção "Sair" nesses dispositivos é movida para uma parte do menu de configurações que requer permissões de administrador para acessar.

## <a name="override-automatic-user-interface-detection"></a>Substituir a detecção automática de interface do usuário

Em alguns casos, você pode optar por atribuir uma licença a uma conta que não corresponda ao uso pretendido. Por exemplo, você pode atribuir uma licença de usuário a uma conta destinada a entrar Salas do Teams no Android. Por padrão, você verá a interface do usuário final em vez da interface da sala de reunião. Para substituir a interface padrão, crie uma nova Política [de Telefone IP do Teams](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) e aplique-a a essa conta.

> [!NOTE]
> A licença atribuída à conta de usuário deve ter pelo menos os mesmos direitos de licença que a interface do usuário desejada. A licença do Common Area Phone só permite a interface do usuário do telefone da Área Comum. A licença da sala de reunião permite a sala de reunião e as interfaces de usuário do telefone de área comum. Uma licença E3 ou E5 dá suporte a todos os modos de entrada.

Veja a seguir um exemplo de como substituir a detecção automática de licenças. Neste exemplo, suponha que uma conta de recurso da sala de reunião chamada conf-adams@contoso.com tenha sido atribuída uma licença E3. Quando essa conta estiver conectada, você desejará que os usuários vejam a interface do usuário da sala de reunião.

### <a name="create-a-new-policy-and-assign-to-user"></a>Criar uma nova política e atribuir ao usuário

1. Inicie uma sessão Windows PowerShell remota e conecte-se ao Microsoft Teams usando o seguinte cmdlet:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Crie uma nova política de Telefone IP do Teams e defina o modo de entrada como "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Agora você pode atribuir essa nova política à conta de recurso da sala de reunião:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Depois de conceder a política à conta de recurso da sala de reunião, você precisará aguardar a atribuição de política ser replicada. Você também precisará sair do dispositivo e entrar novamente.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impacto no centro de administração do Microsoft Teams

O Centro de administração do Microsoft Teams permite que você gerencie dispositivos do Microsoft Teams. Para obter mais informações sobre como gerenciar dispositivos usando o Centro de administração do Teams, consulte [Gerenciar seus dispositivos no Microsoft Teams](device-management.md).


O Centro de administração do Teams fornece a capacidade de gerenciar telefones do Teams. Os telefones são filtrados em uma das três guias com base em suas funções: telefones de usuário, telefones de área comum e telefone de conferência. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Cabeçalho de telefones no centro de administração do Teams.":::

Assim como na detecção da interface do usuário, os telefones do Teams são categorizados com base na licença atribuída à conta que está entrando no telefone. Por exemplo, se uma conta que recebe uma licença de telefone de área comum entrar em um telefone, esse telefone será mostrado na seção Padrão Todos os telefones,  bem como na seção Telefones de área comum.

Se você quiser que um telefone apareça em uma seção diferente, atribua uma licença diferente ao telefone ou crie e atribua uma política de Telefone IP do Teams, conforme descrito [acima](#override-automatic-user-interface-detection).
