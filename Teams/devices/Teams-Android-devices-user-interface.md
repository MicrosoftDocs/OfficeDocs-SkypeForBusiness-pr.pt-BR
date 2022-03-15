---
title: Definir Microsoft Teams de usuário de dispositivos Android
ms.author: czawideh
author: cazawideh
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
description: Saiba como definir a interface do usuário em Teams dispositivos Android.
ms.openlocfilehash: c1872fffef3f21c3fec6a9c693b02e218d5d8337
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503770"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Definir Microsoft Teams de usuário de dispositivos Android

Microsoft Teams dispositivos Android podem exibir uma interface de usuário específica com base no tipo de licença atribuída à conta de entrada. Você pode substituir esse comportamento e controlar qual interface é mostrada. Este artigo detalha como a interface de usuário padrão é escolhida e como você pode alterar a interface usando uma política do Powershell.

Há três tipos de interfaces de usuário em Teams dispositivos Android:

1. Usuário
2. Área Comum
3. Reunião

Se você atribuir uma licença de usuário a uma conta, como uma licença E3 ou E5, o dispositivo Teams exibirá [a](/microsoftteams/user-access) interface padrão do usuário final que é totalmente apresentada para a maioria dos cenários de usuário. No entanto, se um dispositivo estiver executando uma função específica, como um telefone de área comum ou uma sala de reunião, haverá interfaces de usuário específicas para esses usos.

As três imagens a seguir mostram como a interface do usuário muda com base na licença atribuída à conta de usuário. 

## <a name="end-user-interface"></a>Interface do usuário final 

A conta de usuário recebe uma licença E5. Esta é uma licença de usuário, portanto, o dispositivo mostra a interface padrão do usuário final:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interface do modo de usuário.":::

## <a name="common-area-interface"></a>Interface de área comum

Nesta imagem, a conta de usuário foi atribuída a uma [licença Telefone Área Comum](/microsoftteams/set-up-common-area-phones). Telefones de área comum são usados principalmente para fazer e receber chamadas telefônicas. Dessa forma, o bloco de discagem é mostrado no visor:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interface telefônica de área comum.":::

## <a name="meeting-interface"></a>Interface de reunião

Esta imagem mostra uma conta de usuário com uma [Salas do Microsoft Teams Padrão atribuída](/MicrosoftTeams/rooms/rooms-licensing). Salas do Teams licenças devem ser usadas em salas de reunião ou espaços compartilhados, portanto, a interface do usuário muda para facilitar a junção de uma reunião mostrando o modo de exibição do calendário:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interface de reunião.":::

> [!NOTE]
> Alterar a interface do usuário não afeta sua capacidade de usar outros recursos licenciados. Por exemplo, mesmo que o modo de exibição padrão da licença salas de equipe seja o modo de exibição de calendário, você ainda poderá fazer e receber chamadas telefônicas PSTN (Rede Telefônica pública com Opção) se a conta estiver corretamente licenciada e configurada.

> [!IMPORTANT]
> Há outros elementos da interface que mudam. Por exemplo, para impedir que os usuários finais saiam de um telefone de área comum ou dispositivo de sala de reunião, a opção "Sair" nesses dispositivos é movida para uma parte do menu de configurações que requer permissões de administrador para acessar.

## <a name="override-automatic-user-interface-detection"></a>Substituir a detecção automática de interface do usuário

Em alguns casos, você pode optar por atribuir uma licença a uma conta que não corresponder ao uso pretendido. Por exemplo, você pode atribuir uma licença de usuário a uma conta destinada a entrar Salas do Teams android. Por padrão, você verá a interface do usuário final em vez da interface da sala de reunião. Para substituir a interface padrão, crie uma nova política de [Teams IP Telefone e](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) aplique-a a ela a essa conta.

> [!NOTE]
> A licença atribuída à conta de usuário deve ter pelo menos os mesmos direitos de licença que a interface do usuário desejada. A licença área comum Telefone permite apenas a interface do usuário de telefone da Área Comum. A licença da sala de reunião permite a sala de reunião e interfaces de usuário de telefone de área comum. Uma licença E3 ou E5 dá suporte a todos os modos de login.

Veja a seguir um exemplo de como substituir a detecção automática de licença. Neste exemplo, suponha que uma conta de recurso de sala de reunião chamada conf-adams@contoso.com tenha sido atribuída uma licença E3. Quando essa conta estiver assinada, você deseja que os usuários vejam a interface do usuário da sala de reunião.

### <a name="create-a-new-policy-and-assign-to-user"></a>Criar uma nova política e atribuir ao usuário

1. Inicie uma sessão de Windows PowerShell remota e conecte-se Microsoft Teams usando o seguinte cmdlet:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Crie uma nova política Teams ip Telefone e de definir o modo de login como "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Agora você pode atribuir essa nova política à conta de recurso da sala de reunião:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Depois de conceder a política à conta de recurso da sala de reunião, você precisará aguardar que a atribuição de política seja replicada. Você também precisará sair do dispositivo e entrar novamente.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impacto no Microsoft Teams de administração

Microsoft Teams centro de administração permite que você gerencie Microsoft Teams dispositivos. Para obter mais informações sobre como gerenciar dispositivos Teams centro de administração, consulte [Manage your devices in Microsoft Teams](device-management.md).


Teams centro de administração oferece a capacidade de gerenciar Teams telefones. Os telefones são filtrados em uma das três guias com base em suas funções: telefones de usuário, telefones de área comum e telefone de conferência. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Header de telefones no Teams de administração.":::

Assim como na detecção da interface do usuário, Teams telefones são categorizados com base na licença atribuída à conta que está fazendo logo no telefone. Por exemplo, se uma conta atribuída a uma licença de telefone de área comum entrar em um telefone, esse telefone será mostrado na seção padrão Todos os telefones,  bem como na seção Telefones de **área comum.**

Se você quiser que um telefone apareça em uma seção diferente, você pode atribuir uma licença diferente ao telefone ou criar e atribuir uma política de Teams IP Telefone conforme descrito [acima](#override-automatic-user-interface-detection).
