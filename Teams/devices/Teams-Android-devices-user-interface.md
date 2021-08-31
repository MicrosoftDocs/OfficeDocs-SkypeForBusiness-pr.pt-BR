---
title: Definir Microsoft Teams de usuário de dispositivos Android
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Saiba como definir a interface do usuário em Teams Dispositivos Android.
ms.openlocfilehash: 4d17158a6d76dd0d735392c8a441ca184968897a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732450"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Definir Microsoft Teams de usuário de dispositivos Android

Microsoft Teams Dispositivos Android podem exibir uma interface de usuário específica com base no tipo de licença atribuída à conta de entrada. Você pode substituir esse comportamento e controlar qual interface é mostrada. Este artigo detalha como a interface de usuário padrão é escolhida e como você pode alterar a interface usando uma política do Powershell.

Há três tipos de interfaces de usuário em Teams dispositivos Android:

1. Usuário
2. Área Comum
3. Reunião

Se você atribuir uma licença de usuário a uma conta, como uma licença E3 ou E5, o dispositivo Teams exibirá [a](/microsoftteams/user-access) interface padrão do usuário final, que é totalmente apresentada para a maioria dos cenários do usuário. No entanto, se um dispositivo estiver executando uma função específica, como um telefone de área comum ou uma sala de reunião, haverá interfaces de usuário específicas para esses usos.

As três imagens a seguir mostram como a interface do usuário muda com base na licença atribuída à conta de usuário. Na primeira imagem, a conta de usuário recebe uma licença E5. Esta é uma licença de usuário, portanto, o dispositivo mostra a interface padrão do usuário final:

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="Interface do modo de usuário.":::

Nesta imagem, a conta de usuário recebeu uma licença de telefone de área [comum.](/microsoftteams/set-up-common-area-phones) Telefones de área comum são usados principalmente para fazer e receber chamadas telefônicas. Dessa forma, o bloco de discagem é mostrado no visor:

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="Interface telefônica de área comum.":::

Por fim, essa imagem mostra uma conta de usuário com [uma Salas do Microsoft Teams Standard](/MicrosoftTeams/rooms/rooms-licensing) atribuída. Salas do Teams licenças devem ser usadas em salas de reunião ou espaços compartilhados, portanto, a interface do usuário muda para facilitar a junção de uma reunião mostrando o modo de exibição do calendário:

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="Interface de reunião.":::

> [!NOTE]
> Alterar a interface do usuário não afeta sua capacidade de usar outros recursos licenciados. Por exemplo, mesmo que o modo de exibição padrão da licença salas de equipe seja o modo de exibição de calendário, você ainda poderá fazer e receber chamadas telefônicas PSTN (Rede Telefônica pública com Opção) se a conta estiver corretamente licenciada e configurada.

> [!IMPORTANT]
> Há outros elementos da interface que mudam. Por exemplo, para impedir que os usuários finais saiam de um telefone de área comum ou dispositivo de sala de reunião, a opção "Sair" nesses dispositivos é movida para uma parte do menu de configurações que requer permissões de administrador para acessar.

## <a name="override-automatic-user-interface-detection"></a>Substituir a detecção automática de interface do usuário

Em alguns casos, você pode optar por atribuir uma licença a uma conta que não corresponder ao uso pretendido. Por exemplo, você pode atribuir uma licença de usuário a uma conta destinada a entrar Salas do Teams no Android. Por padrão, você verá a interface do usuário final em vez da interface da sala de reunião. Para substituir a interface padrão, crie uma nova política de [Teams IP Telefone e](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) aplique-a a ela a essa conta.

> [!NOTE]
> A licença atribuída à conta de usuário deve ter pelo menos os mesmos direitos de licença que a interface do usuário desejada. A licença área comum Telefone permite apenas a interface do usuário de telefone da Área Comum. A licença da sala de reunião permite a sala de reunião e interfaces de usuário de telefone de área comum. Uma licença E3 ou E5 dá suporte a todos os modos de login.

Veja a seguir um exemplo de como substituir a detecção automática de licença. Neste exemplo, suponha que uma conta de recurso de sala de reunião chamada conf-adams@contoso.com tenha sido atribuída uma licença E3. Quando essa conta estiver assinada, você deseja que os usuários vejam a interface do usuário da sala de reunião.

### <a name="create-a-new-policy-and-assign-to-user"></a>Criar uma nova política e atribuir ao usuário

1. Inicie uma sessão Windows PowerShell remota e conecte-se Microsoft Teams usando o seguinte cmdlet:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Crie uma nova política de Teams IP Telefone e de definir o modo de login como "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Agora você pode atribuir essa nova política à conta de recurso da sala de reunião:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Depois de conceder a política à conta de recurso da sala de reunião, você precisará aguardar que a atribuição de política seja replicada. Você também precisará sair do dispositivo e entrar novamente.
