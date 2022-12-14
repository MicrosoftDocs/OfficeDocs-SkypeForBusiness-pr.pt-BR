---
title: Definir Microsoft interface do usuário de dispositivos Android do Teams
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
ms.openlocfilehash: 0efabef522a791a56ac187da9a63fab10e4ab3e9
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392430"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Definir Microsoft interface do usuário de dispositivos Android do Teams

Microsoft dispositivos Android do Teams podem exibir uma interface de usuário específica com base no tipo de licença atribuída à conta de entrada. Você pode substituir esse comportamento e controlar qual interface é mostrada. Este artigo detalha como a interface do usuário padrão é escolhida e como você pode alterar a interface usando uma política do Powershell.

Há três tipos de interfaces de usuário em dispositivos Android do Teams:

1. Usuário
2. Área Comum
3. Reunião

Se você [atribuir uma licença de usuário](/microsoftteams/user-access) a uma conta, como uma licença E3 ou E5, o dispositivo teams exibirá a interface padrão do usuário final que está totalmente em destaque para a maioria dos cenários de usuário. No entanto, se um dispositivo estiver executando uma função específica, como um telefone de área comum ou uma sala de reunião, haverá interfaces de usuário específicas para esses usos.

As três imagens a seguir mostram como a interface do usuário muda com base na licença atribuída à conta de usuário.

## <a name="end-user-interface"></a>Interface do usuário final

A conta de usuário recebe uma licença E5. Essa é uma licença de usuário, portanto, o dispositivo mostra a interface padrão do usuário final:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interface do modo de usuário.":::

## <a name="common-area-interface"></a>Interface de área comum

Nesta imagem, a conta de usuário recebeu uma [licença Microsoft Dispositivos Compartilhados do Teams](/microsoftteams/teams-add-on-licensing/teams-shared-device-license). Os telefones de área comum são usados principalmente para fazer e receber chamadas telefônicas. Como tal, o bloco de discagem é mostrado na exibição:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interface de telefone de área comum.":::

## <a name="meeting-interface"></a>Interface de reunião

Esta imagem mostra uma conta de usuário com uma [licença de Salas do Microsoft Teams](/MicrosoftTeams/rooms/rooms-licensing) atribuída. Salas do Teams licenças devem ser usadas em salas de reunião ou espaços compartilhados, portanto, a interface do usuário muda para facilitar a participação em uma reunião mostrando a exibição do calendário:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interface de reunião.":::

> [!NOTE]
> A alteração da interface do usuário não afeta sua capacidade de usar outros recursos licenciados. Por exemplo, embora a exibição padrão da licença de Salas de Equipe seja a exibição de calendário, você ainda pode fazer e receber chamadas telefônicas PSTN (Rede Telefônica pública) se a conta estiver corretamente licenciada e configurada.

> [!IMPORTANT]
> Há outros elementos da interface que mudam. Por exemplo, para impedir que os usuários finais saiam de um telefone de área comum ou dispositivo de sala de reunião, a opção "Sair" nesses dispositivos é movida para uma parte do menu de configurações que exige permissões de administrador para acessar.

## <a name="override-automatic-user-interface-detection"></a>Substituir a detecção automática de interface do usuário

Em alguns casos, você pode optar por atribuir uma licença a uma conta que não corresponda ao uso pretendido. Por exemplo, você pode atribuir uma licença de usuário a uma conta destinada a entrar no Salas do Teams no Android. Por padrão, você veria a interface do usuário final em vez da interface da sala de reunião. Para substituir a interface padrão, crie uma nova [Política de Telefone IP do Teams](/powershell/module/skype/new-csteamsipphonepolicy) e aplique a ela a essa conta.

> [!NOTE]
> A licença atribuída à conta de usuário deve ter pelo menos os mesmos direitos de licença que a interface de usuário desejada. A licença **Microsoft Dispositivos Compartilhados do Teams** permite apenas a interface do usuário de telefone de área comum. A **licença Salas do Teams** permite a sala de reunião e as interfaces comuns do usuário do telefone da área comum. Uma licença E3 ou E5 dá suporte a todos os modos de entrada.

Veja a seguir um exemplo de como substituir a detecção automática de licenças. Neste exemplo, suponha que uma conta de recurso da sala de reunião chamada conf-adams@contoso.com tenha sido atribuída uma licença E3. Quando essa conta estiver inserida, você deseja que os usuários vejam a interface do usuário da sala de reunião.

### <a name="create-a-new-policy-and-assign-to-user"></a>Criar uma nova política e atribuir ao usuário

1. Inicie uma sessão de Windows PowerShell remota e conecte-se ao Microsoft Teams usando o seguinte cmdlet:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Crie uma nova política de telefone IP do Teams e defina o modo de entrada como "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Agora você pode atribuir essa nova política à conta de recursos da sala de reunião:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Depois de conceder a política à conta de recursos da sala de reunião, você precisará aguardar a replicação da atribuição da política. Você também precisará sair do dispositivo e entrar novamente.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impacto no centro de administração do Microsoft Teams

Microsoft centro de administração do Teams permite que você gerencie Microsoft dispositivos do Teams. Para obter mais informações sobre como gerenciar dispositivos usando o centro de administração do Teams, consulte [Gerenciar seus dispositivos no Microsoft Teams](device-management.md).

O centro de administração do Teams fornece a capacidade de gerenciar telefones do Teams. Os telefones são filtrados em uma das três guias com base em sua função: telefones de usuário, telefones de área comum e telefone de conferência.

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Cabeçalho de telefones no centro de administração do Teams.":::

Assim como acontece com a detecção da interface do usuário, os telefones do Teams são categorizados com base na licença atribuída à entrada da conta no telefone. Por exemplo, se uma conta atribuída a um Microsoft a licença **dispositivos compartilhados do Teams** entrar em um telefone, esse telefone será mostrado na seção **Todos os telefones** padrão, bem como na seção **Telefones da área comum**.

Se você quiser que um telefone apareça em uma seção diferente, você pode atribuir uma licença diferente ao telefone ou criar e atribuir uma política de telefone IP do Teams, conforme [descrito acima](#override-automatic-user-interface-detection).
