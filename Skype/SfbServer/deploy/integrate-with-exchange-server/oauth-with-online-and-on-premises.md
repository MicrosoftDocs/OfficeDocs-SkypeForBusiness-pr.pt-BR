---
title: Configurar OAuth entre o Skype for Business Online e o Exchange no local
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configurando o OAuth a autenticação entre o Exchange no local e Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos no suporte ao recurso.
ms.openlocfilehash: 6fbf6944ec1b7518311d8d7a0bd75ef3249a0142
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876574"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>Configurar OAuth entre o Skype for Business Online e o Exchange no local

Configurando o OAuth a autenticação entre o Exchange no local e Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos em [suporte de recurso](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tópico se aplica ao Exchange Server 2016 e Exchange Server 2013.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para concluir esta tarefa: 15 minutos

-  Você precisa receber permissões antes de realizar esse procedimento ou procedimentos. Para ver quais permissões você precisa, consulte o tópico [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Para obter informações sobre atalhos de teclado que possam se aplicar aos procedimentos neste tópico, consulte [atalhos de teclado no Centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>Configure a autenticação de OAuth entre seu Exchange local e as empresas com Skype for Business

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>Etapa 1: crie um objeto do servidor de autorização para sua organização do Skype for Business Online

Especifique um domínio verificado para seu Skype para a organização Business Online. Esse domínio deve ser o mesmo que o domínio SIP primário utilizado para o modelo de contas baseadas em nuvem. Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir.

Execute o seguinte comando no Shell de gerenciamento do Exchange (o Exchange PowerShell) no seu local de organização do Exchange.

```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1"
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>Etapa 2: habilite o aplicativo parceiro para sua organização do Skype for Business Online

Execute o seguinte comando no Exchange PowerShell em seu local de organização do Exchange.

```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Etapa 3: crie uma nova conta de Usuário de Email para o aplicativo parceiro do Skype for Business Online 

Esta etapa é realizada no local. Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento. Essa conta será então usada na próxima etapa.

Especifique um domínio verificado para sua organização do Exchange. Esse domínio deve ser o mesmo usado como o domínio SMTP primário usado para as contas do Exchange local. Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir. Além disso, o \<DomainControllerFQDN\> deve ser o FQDN de um controlador de domínio.

```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Esse comando ocultará o novo usuário da caixa de correio das listas de endereços.

```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Esses dois próximos comandos atribuirão a função de gerenciamento de UserApplication e ArchiveApplication a esta nova conta.

```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Etapa 4: crie e habilite um aplicativo parceiro para o Skype for Business Online

Crie um novo aplicativo parceiro e use a conta que você acabou de criar. Execute o seguinte comando no Exchange PowerShell em seu local de organização do Exchange.

```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>Etapa 5: Exportar o certificado de autorização local

Execute um script do PowerShell para exportar o certificado de autorização local, que você importará para seu Skype para a organização Business Online na próxima etapa.

Salve o seguinte texto em um arquivo de script do PowerShell denominado, por exemplo, ExportAuthCert.ps1.

```
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

No Exchange PowerShell em sua organização do Exchange local, execute o script do PowerShell que você acabou de criar. Por exemplo:.\ExportAuthCert.ps1

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Etapa 6: carregar o certificado de autorização local para o Azure Active Directory ACS

Em seguida, utilize o Windows PowerShell para carregar o certificado de autorização local que você exportou na etapa anterior no Serviço de Controle de Acesso do Azure Active Directory (ACS). Para fazer isso, o Módulo Azure Active Directory para cmdlets do Windows PowerShell já deve estar instalado. Se não estiver instalado, vá para [https://aka.ms/aadposh](https://aka.ms/aadposh) para instalar o Windows Azure Active Directory módulo para Windows PowerShell. Conclua as etapas a seguir após a instalação do módulo Azure Active Directory para Windows PowerShell.

1. Clique no atalho do **Módulo Azure Active Directory para Windows PowerShell** para abrir um espaço de trabalho do Windows PowerShell que possui os cmdlets do Azure AD instalado. Todos os comandos nesta etapa serão executados utilizando-se o Windows PowerShell para console do Azure Active Directory.

2. Salve o seguinte texto em um arquivo de script do PowerShell chamado, por exemplo, `UploadAuthCert.ps1`.

   ```
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Execute o script do PowerShell criado na etapa anterior. Por exemplo:`.\UploadAuthCert.ps1`

4. Depois de iniciar o script, uma caixa de diálogo de credenciais será exibida. Insira as credenciais para a conta do administrador do locatário de sua empresa Microsoft Online Azure AD. Depois de executar o script, deixe a sessão Windows PowerShell para Azure AD aberta. Você a utilizará para executar um script do PowerShell na próxima etapa.

### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a>Passo 7: registrar as autoridades do nome do host para o domínio SMTP

Especifique um domínio verificado para sua organização do Exchange. Esse domínio deve ser o mesmo usado como o domínio SMTP primário usado para as contas do Exchange local. Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir.

> [!NOTE]
> A execução bem sucedida do script a seguir requer que o Windows PowerShell para Azure Active Directory esteja conectado ao seu locatário do Microsoft Online Azure AD, conforme explicado na etapa 4 na seção anterior.

1. Salve o texto a seguir em um arquivo de script do PowerShell denominado, por exemplo, RegisterEndpoints.ps1. Este exemplo usa um curinga para registrar todos os pontos de extremidade para contoso.com. Substituir <your Verified Domain> com um FQDN para seu servidor do Exchange local.

   ```
   $externalAuthority="*.<your Verified Domain>"
   $ServiceName = "00000002-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName;
   $spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority);
   $p.ServicePrincipalNames.Add($spn);
   Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames;
   ```

2. No Windows PowerShell para Azure Active Directory, execute o script do Windows PowerShell que você criou na etapa anterior. Por exemplo:`.\RegisterEndpoints.ps1`

### <a name="verify-your-success"></a>Verifique se a operação foi realizada com sucesso

Verifique se a configuração do OAuth está correta verificando se alguns recursos estão funcionando com êxito, como obtenção do histórico de conversa para clientes móveis visíveis na pasta Histórico de Conversas do Outlook.

1. Inicie o Skype para aplicativos móveis de negócios no seu Windows Phone ou dispositivo iOS e entrar como um Skype para usuário Business Online com um Exchange 2016 ou caixa de correio do Exchange 2013 local.

2. Ter uma conversa de mensagem instantânea com outro Skype para usuário Business Online.

3. Fechar a janela de Conversa IM.

4. Inicie o Outlook para este usuário e verifique se a conversa está visível na pasta Histórico de Conversas do Outlook.

Como alternativa, examine o tráfego. O tráfego em um handshake OAuth é realmente característica (e não se parece com a autenticação básica), especialmente ao redor territórios, onde você vai começar a ver o tráfego de emissor parecida com esta: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes com uma / antes o sinal @), em que estão sendo passados tokens. Você não verá um nome de usuário ou senha, que é o ponto do OAuth. Mas você verá o emissor 'Temporária' – nesse caso, '4' é Skype para negócios – e o território de sua assinatura.

Se você quiser ter certeza de que você estiver usando o OAuth com êxito, certifique-se de que você sabe o que esperar e quando já souber o que o tráfego deve se parecer com. Caso [aqui está o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um bem standard [exemplo de tráfego de OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente úteis para mensagens lidas, embora não use Refresh tokens) e existem extensões Fiddler que permitirá que você procure em seu OAuth JWT (JSON Token de Web).

Aqui está um [exemplo de configuração de um](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mas você pode usar qualquer ferramenta de rastreamento de rede que você deseja realizar esse processo.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a autenticação OAuth entre organizações do Exchange e o Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
