---
title: Autenticação baseada em aplicativo no Módulo do Teams PowerShell
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba mais sobre a autenticação baseada em aplicativo no Módulo do Teams PowerShell, usado para administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60d9bf64233db3f5e615c0904c6eb376f187266c
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812838"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Autenticação baseada em aplicativo no Módulo do Teams PowerShell

A autenticação baseada em aplicativo agora tem suporte no Módulo do Teams PowerShell com versões 4.7.1-preview ou posteriores. Atualmente, esse modo de autenticação só tem suporte em ambientes comerciais.


## <a name="cmdlets-supported"></a>Cmdlets com suporte

Todos os cmdlets têm suporte agora, exceto para os cmdlets mencionados abaixo. 

  - New-Team
  - [Get| Definir| Novo| Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>Exemplos

Os exemplos a seguir mostram como usar o Módulo do Teams PowerShell com o Azure AD autenticação baseada em aplicativo: 

- Conecte-se usando uma impressão digital de certificado:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Quando você usa o parâmetro CertificateThumbprint, o certificado precisa ser instalado no computador em que você está executando o comando. O certificado deve ser instalado no repositório de certificados do usuário.
  
- Conecte-se usando um objeto de certificado:

  ```powershell
  Connect-MicrosoftTeams -Certificate <%X509Certificate2 object%> -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Quando você usa o parâmetro Certificado, o certificado não precisa ser instalado no computador em que você está executando o comando. O certificado pode ser armazenado remotamente & buscado quando o script é executado. O parâmetro Certificado está disponível no Módulo do Teams PowerShell versão 4.9.2-preview ou posterior.
  
- Conecte-se usando Tokens de Acesso:
  
  Os Tokens de Acesso podem ser recuperados por meio do ponto de extremidade login.microsoftonline.com. Ele requer dois Tokens de Acesso – recursos "MS Graph" e "API Administração do Locatário do Skype e do Teams".

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>Como funciona?

O Módulo do Teams PowerShell busca o token baseado em aplicativo usando a ID do aplicativo, a ID do locatário e a impressão digital do certificado. O objeto de aplicativo provisionado dentro do Azure AD tem uma Função de Diretório atribuída a ele, que é retornada no token de acesso. O RBAC (controle de acesso baseado em função) da sessão é configurado usando as informações de função de diretório disponíveis no token.


## <a name="setup-application-based-authentication"></a>Configurar autenticação baseada em aplicativo

Uma integração inicial é necessária para autenticação usando objetos de aplicativo. O aplicativo e a entidade de serviço são usados de forma intercambiável, mas um aplicativo é como um objeto de classe, enquanto uma entidade de serviço é como uma instância da classe. Você pode saber mais sobre esses objetos em [objetos de entidade de aplicativo e serviço no Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

As etapas de exemplo para criar aplicativos no Azure Ad são mencionadas abaixo, para obter etapas detalhadas, consulte este [artigo](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Registrar o aplicativo no Azure AD
2. Atribuir permissões de API ao aplicativo
   - Para \*cmdlets -Cs - a permissão de API do Graph da Microsoft necessária é `Organization.Read.All`.
   - Para cmdlets não \*-Cs - as permissões do Microsoft API do Graph necessárias são `Organization.Read.All`, `User.Read.All`, `Group.ReadWrite.All`, , `AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All`, `ChannelSettings.ReadWrite.All`, `ChannelMember.ReadWrite.All`.  
3. Gerar um certificado autoassinado
4. Anexar o certificado ao aplicativo Azure AD
5. Atribuir [Azure AD funções](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) ao aplicativo

O aplicativo precisa ter as funções RBAC apropriadas atribuídas. Como os aplicativos são provisionados em Azure AD, você pode usar qualquer uma das funções internas com suporte.
 
