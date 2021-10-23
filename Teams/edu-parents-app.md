---
title: Configuração de administrador para o aplicativo Pais da Microsoft EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams para pré-requisitos de documento de artigo da EDU e configuração do PowerShell para o aplicativo Pais.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b79319da9f901fc4546c25d5165f4d2361521a7
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537002"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Implantando o aplicativo pais no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Habilenciar o aplicativo pais no Microsoft Teams é um processo simples para administradores, fornecendo um método seguro para os educadores se comunicarem com os alunos e seus contatos que permanecem no locatário, e que será dimensionado em toda a sua organização de educadores.

## <a name="requirements"></a>Requisitos

### <a name="school-data-sync"></a>School Data Sync

- Você precisa School Data Sync (SDS) para preencher as informações de contato relacionadas **de** cada aluno.
  - [Implantar SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Se você precisar de assistência na configuração do SDS e na habilitação de Contatos Pai em seu locatário, entre em contato com a equipe de Sucesso do Cliente EDU:
  - Concluindo o processo RFA em [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrir um tíquete em [Support](https://aka.ms/sdssupport).

### <a name="teams-admins-center---policies"></a>Teams Centro de Administração - Políticas

- Proprietário da classe deve ter Chat habilitado
- O Proprietário da Classe deve ter Acesso **Externo com Teams contas não gerenciadas por uma organização** habilitada. 
  - Essa configuração pode ser encontrada em Configurações em toda a organização > Acesso Externo para o nível do locatário ou se você quiser habilitar para um determinado conjunto de usuários, consulte o PowerShell abaixo.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Habilitando o chat federado por usuário

1. Instale a versão Microsoft Teams versão mais recente do módulo do PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Usando credenciais com privilégios de administrador, execute o seguinte comando em uma janela de comando:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

Por padrão, a configuração de nível de locatário que controla Teams acesso externo do consumidor para o locatário (AllowTeamsConsumer) está desabilitada. No entanto, a configuração de política que permite Teams acesso externo do consumidor no nível do usuário (EnableTeamsConsumerAccess) está habilitada por padrão para todas as políticas de acesso externo no nível do usuário. A configuração de nível de locatário e a configuração de política no nível do usuário precisam estar habilitadas para que um usuário tenha acesso Teams externo do consumidor. Se você não quiser que todos em seu locatário tenham o acesso externo do consumidor Teams habilitado, atualize as políticas de acesso externo no nível do usuário atribuídas aos usuários antes de habilitar a configuração no nível do locatário.

Se você precisar verificar quais políticas de acesso externo no nível do usuário existem e a quem elas são atribuídas, você pode usar as seguintes etapas:
    
3. Verifique quais políticas de acesso externo no nível do usuário existem.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Para cada política diferente da política "Global", verifique quais usuários têm a política atribuída. Observação: todos os usuários que não têm uma política específica atribuída retornarão à política "Global"

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq “<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>Outras opções do PowerShell

Como todas as políticas de acesso externo no nível do usuário têm EnableTeamsConsumerAccess definido como true por padrão, se você quiser atualizar qualquer uma dessas políticas para ajustar a configuração EnableTeamsConsumerAccess, você pode criar novas políticas de acesso externo com configurações ajustadas ou reatribuir usuários a políticas novas ou existentes, por meio do seguinte PowerShell:

- Criar uma nova política de acesso externo (isso cria uma nova política de acesso externo e define as configurações): [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar uma política de acesso externo existente (Modifica as configurações de uma política de acesso externo existente, incluindo a política Global)): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Os seguintes padrões de assinatura não podem ser modificados: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". Se você precisar alterar as configurações de política para usuários que têm essas políticas atribuídas, atribua políticas diferentes com as configurações corretas a esses usuários.

- Atribuir uma política de acesso externo a um único usuário: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Atribuir uma política a um conjunto de usuários: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Depois de ter certeza de que suas políticas de acesso externo no nível do usuário estão definidas corretamente para todos os usuários Teams, você poderá habilitar a configuração no nível de locatário que controla o acesso externo do consumidor para o locatário usando o seguinte cmdlet:

- Definir as configurações de federação para seu locatário (Definindo AllowTeamsConsumer como true): [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>Desabilitando o aplicativo Pais

O Aplicativo pais é habilitado por padrão, portanto, todos os proprietários de classe verão o aplicativo em sua equipe de classe. O aplicativo pode ser desabilitado no nível de locatário [usando Permitir e bloquear aplicativos](manage-apps.md#allow-and-block-apps) no Microsoft Teams de administração. Se estiver desabilitado no nível do locatário, ele será bloqueado para todos os usuários, mesmo que a permissão no nível do usuário seja habilitada.

Isso também pode ser desabilitado no nível do usuário usando [Gerenciar políticas de permissão do aplicativo em Microsoft Teams]. (teams-app-permission-policies.md).

## <a name="more-information"></a>Mais informações

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Atribuir sua política a um usuário](/powershell/module/skype/grant-csexternalaccesspolicy)
