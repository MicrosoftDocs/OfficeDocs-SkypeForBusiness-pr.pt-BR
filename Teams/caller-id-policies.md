---
title: Gerenciar políticas de identificação de chamadas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de identificação de chamadas no Microsoft Teams para alterar ou bloquear a identificação de chamadas de usuários do teams em sua organização.
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349775"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gerenciar políticas de identificação de chamadas no Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, você pode usar as políticas de identificação de chamada no Microsoft Teams para alterar ou bloquear a identificação de chamadas (também conhecida como identificação da linha de chamada). Por padrão, o número de telefone dos usuários do teams pode ser visto ao fazer uma chamada para um telefone PSTN, e o número de telefone PSTN pode ser visto quando ele chama um usuário do teams. Você pode usar as políticas de identificação de chamadas para exibir um número de telefone alternativo para usuários do teams em sua organização ou impedir que um número recebido seja exibido.

Por exemplo, quando os usuários fazem uma chamada, você pode alterar a identificação de chamadas para exibir o número de telefone principal da sua organização, em vez de números de telefone dos usuários.

Você gerencia as políticas de identificação de chamadas **Voice**indo para  >  **políticas de identificação de chamadas** de voz no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

Você pode editar a política global ou criar e atribuir uma política personalizada. Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário. Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário.

## <a name="create-a-custom-caller-id-policy"></a>Criar uma política de identificação de chamadas personalizada

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.
2. Clique em **Adicionar**. <br>
![Captura de tela da página nova política de identificação de chamadas no centro de administração](media/caller-id-policies-add-policy.png)
3. Insira um nome e uma descrição para a política.
4. Aqui, escolha as configurações desejadas:

    - **Bloquear a identificação**de chamadas de entrada: Ative essa configuração para impedir que a identificação de chamadas de chamadas de entrada seja exibida.
    - **Substituir a política de identificação de chamadas**: Ative essa configuração para permitir que os usuários substituam as configurações na política para exibir seu número para chamar ou não. Isso significa que os usuários podem escolher se desejam exibir a identificação de chamadas. Para obter mais informações, consulte [controle do usuário final da identificação de chamadas de saída](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).
    - **Substituir a identificação de chamadas**por: definir a identificação de chamadas a ser exibida para os usuários selecionando uma das seguintes opções:

        - **Número do usuário**: exibe o número do usuário. 
        - **Número do serviço**: permite que você defina um número de telefone de serviço para ser exibido como a identificação de chamadas.
        - **Anônimo**: EXIBE a identificação de chamadas como anônima.

    - **Substituir a identificação de chamadas por este número de serviço**: escolha um número de serviço para substituir a identificação de chamadas dos usuários. Essa opção estará disponível se você tiver selecionado **número de serviço** em **substituir a identificação de chamadas por**.

5. Clique em **Salvar**.

## <a name="edit-a-caller-id-policy"></a>Editar uma política de identificação de chamadas

Você pode editar a política global ou qualquer política personalizada criada. 

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Altere as configurações desejadas e clique em **salvar**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Atribuir uma política de identificação de chamadas personalizada a usuários

Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a um ou mais usuários ou ao módulo do PowerShell do Skype for Business para atribuir uma política personalizada a usuários em um grupo, como um grupo de segurança ou grupo de distribuição.

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a>Atribuir uma política de ID de linha de chamador personalizada aos usuários

Para atribuir uma política a um usuário:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.
3. Em **política de identificação de chamadas**, selecione a política que você deseja atribuir e, em seguida, escolha **salvar**.

Para atribuir uma política a vários usuários de uma só vez:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e procure os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique no &#x2713; (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **aplicar**.  

Ou, você também pode fazer o seguinte:

1. Vá para políticas de identificação de chamadas de voz **do centro de administração do Microsoft Teams**  >  **Voice**  >  **Caller ID policies**.
2. Escolha a política clicando à esquerda do nome da política.
3. Escolha **Gerenciar usuários**.
4. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, selecione **salvar**.

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>Atribuir uma política de identificação de chamadas personalizada a usuários em um grupo

Você pode querer atribuir uma política personalizada a vários usuários que você já tenha identificado. Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança. Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business. Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

Neste exemplo, atribuímos uma política de limite de chamadas personalizada chamada política de identificação de chamadas para todos os usuários no grupo de suporte da contoso.  

> [!NOTE]
> Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenha o GroupObjectId do grupo específico.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
Obter os membros do grupo especificado.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua todos os usuários do grupo a uma política específica de identificação de chamadas. Neste exemplo, ele é compatível com a política de identificação de chamadas.
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.

 ## <a name="related-topics"></a>Tópicos relacionados

- [New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [Atribuir políticas a seus usuários no Teams](assign-policies.md)
