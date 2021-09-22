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
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475901"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Implantando o aplicativo pais no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Habilenciar o aplicativo pais no Microsoft Teams é um processo simples para administradores, fornecendo um método seguro para os educadores se comunicarem com os alunos e seus contatos que permanecem no locatário e que será dimensionado em toda a sua organização de educadores.

## <a name="requirements"></a>Requisitos

- SDS (sincronização de dados escolares) - Você precisará carregar contatos relacionados associados aos seus alunos no SDS usando a opção CSV. Confira [Configure CSV for SDS](/schooldatasync/set-up-your-sds-flow) and [Update relatedContacts](/graph/api/relatedcontact-update) para obter mais informações.
- No Teams de administração, o Proprietário da Classe deve ter **o Chat** habilitado e o **chat federado** com Teams contas não gerenciadas por **uma organização.**

Se você precisar habilitar o chat federado por usuário, as etapas estão abaixo.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Habilitando o chat federado por usuário

1. Instale a versão Microsoft Teams versão mais recente do módulo do PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. Execute em uma janela de comando usando credenciais que tenham privilégios de administrador.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. Desativar e ativar na configuração global de nível de grupo/usuário ou no nível do locatário.

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > Ao executar este PowerShell, as alterações podem levar uma hora ou mais para ser concluída.
    
## <a name="more-information"></a>Mais informações

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Atribuir sua política a um usuário](/powershell/module/skype/grant-csexternalaccesspolicy)
