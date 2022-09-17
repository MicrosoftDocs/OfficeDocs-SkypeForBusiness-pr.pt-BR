---
title: Autenticação baseada em aplicativo no Módulo powershell do Teams
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba mais sobre a autenticação baseada em aplicativo no Módulo do PowerShell do Teams, usado para administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 479dd64d6eece46335545e79e8f618b797e85f77
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795060"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Autenticação baseada em aplicativo no Módulo powershell do Teams

A autenticação baseada em aplicativo agora tem suporte no Módulo do PowerShell do Teams para um conjunto limitado de cmdlets em versão prévia com versões 4.7.1 ou posteriores. Atualmente, esse modo de autenticação só tem suporte em ambientes comerciais. Não há suporte para clientes que estão ou foram habilitados anteriormente para Reuniões Hospedadas Regionalmente no Skype for Business Online.


## <a name="cmdlets-supported"></a>Cmdlets com suporte

Todos os \*cmdlets não -Cs (por exemplo, Get-Team), Get-CsTenant e Get-CsOnlineUser & Get-CsOnlineVoiceUser já têm suporte. Outros cmdlets serão distribuídos gradualmente. 


## <a name="examples"></a>Exemplos

Os exemplos a seguir mostram como usar o Módulo do PowerShell do Teams com a autenticação Azure AD baseada em aplicativo: 

- Conecte-se usando uma impressão digital do certificado:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Quando você usa o parâmetro CertificateThumbprint, o certificado precisa ser instalado no computador em que você está executando o comando. O certificado deve ser instalado no repositório de certificados do usuário.
  
- Conecte-se usando tokens de acesso:
  
  Os Tokens de Acesso podem ser recuperados por meio login.microsoftonline.com ponto de extremidade. Ele requer dois tokens de acesso – recursos de "MS Graph" e "API de locatário do Skype e do Teams Administração".

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

O Módulo do PowerShell do Teams busca o token baseado em aplicativo usando a ID do aplicativo, a ID do locatário e a impressão digital do certificado. O objeto de aplicativo provisionado Azure AD tem uma Função de Diretório atribuída a ele, que é retornada no token de acesso. O RBAC (controle de acesso baseado em função) da sessão é configurado usando as informações de função de diretório disponíveis no token.


## <a name="setup-application-based-authentication"></a>Configurar a autenticação baseada em aplicativo

Uma integração inicial é necessária para autenticação usando objetos de aplicativo. O aplicativo e a entidade de serviço são usados de forma intercambiável, mas um aplicativo é como um objeto de classe enquanto uma entidade de serviço é como uma instância da classe. Você pode saber mais sobre esses objetos em [objetos de aplicativo e entidade de serviço no Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

As etapas de alto nível para criar aplicativos no Azure Ad são mencionadas abaixo. Para obter etapas detalhadas, consulte este [artigo](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Registrar o aplicativo no Azure AD
2. Atribuir permissões de API ao aplicativo
   - Para \*cmdlets -Cs– nenhuma permissão de API é necessária.
   - \*Para cmdlets não -Cs, as `User.Read.All`permissões API do Graph Microsoft necessárias são , `Group.ReadWrite.All`, `AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All`, `ChannelSettings.ReadWrite.All`, . `ChannelMember.ReadWrite.All`  
3. Gerar um certificado autoassinado
4. Anexar o certificado ao Azure AD aplicativo
5. Atribuir Azure AD funções ao aplicativo

O aplicativo precisa ter as funções RBAC apropriadas atribuídas. Como os aplicativos são provisionados Azure AD, você pode usar qualquer uma das funções internas com suporte.
 
