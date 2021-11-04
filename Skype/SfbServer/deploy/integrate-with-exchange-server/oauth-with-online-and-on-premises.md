---
title: Integração entre Skype for Business Online e Exchange servidor
ms.reviewer: cbland
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configurar a autenticação OAuth entre o Exchange local e o Skype for Business Online habilita os recursos Skype for Business e Exchange integração descritos em Suporte a recursos.
ms.openlocfilehash: 0e811a7feb713e2c356acdeba5461a212bfff17e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764769"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurar Integração e OAuth entre Skype for Business Online e Exchange Server 

Configurar a integração entre o Exchange e o Skype for Business Online habilita os recursos Skype for Business e Exchange integração descritos em [Suporte a recursos.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)

Este tópico se aplica à integração com o Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para a conclusão da tarefa: 15 minutos

-  Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o tópico Exchange e permissões de infraestrutura [do Shell.](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)

- Para informações sobre atalhos de teclado que possam se aplicar aos procedimentos neste tópico, confira [Atalhos de teclado no Centro de Administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Para obter informações sobre compatibilidade, [consulte Skype for Business compatibilidade com Office aplicativos](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar a integração entre Exchange Server e O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Etapa 1: Configurar a autenticação OAuth entre Exchange Server e O365

Execute as etapas no seguinte artigo:

[Configurar a autenticação OAuth entre organizações do Exchange e do Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Etapa 2: Criar uma nova conta de usuário de email para o aplicativo de parceiro Skype for Business Online

Esta etapa é feita no servidor Exchange servidor. Ele criará um usuário de email e atribuirá a ele os direitos de função de gerenciamento apropriados. Essa conta será usada na próxima etapa.

Especifique um domínio verificado para sua Exchange organização. Esse domínio deve ser o mesmo domínio usado como o domínio SMTP principal usado para as contas Exchange locais. Esse domínio é conhecido \<your Verified Domain\> como no procedimento a seguir. Além disso, \<DomainControllerFQDN\> o deve ser o FQDN de um controlador de domínio.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Este comando ocultará o novo usuário de email das listas de endereços.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Esses dois comandos a seguir atribuirão a função de gerenciamento UserApplication e ArchiveApplication a essa nova conta.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Etapa 3: criar e habilitar um aplicativo de parceiro para Skype for Business Online 

Crie um novo aplicativo parceiro e usará a conta que você acabou de criar. Execute o seguinte comando no Exchange PowerShell em sua organização local do Exchange.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Etapa 4: Exportar o certificado de autorização local

Execute um script do PowerShell para exportar o certificado de autorização local, que será importado para sua organização Skype for Business Online na próxima etapa.

Salve o seguinte texto em um script do PowerShell chamado, por exemplo, de ExportAuthCert.ps1.

```powershell
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

No Exchange PowerShell em sua organização Exchange local, execute o script do PowerShell que você acabou de criar. Por exemplo: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Etapa 5: Upload certificado de autorização local para Azure Active Directory ACS

Em seguida, use Windows PowerShell para carregar o certificado de autorização local que você exportou na etapa anterior para Azure Active Directory Serviços de Controle de Acesso (ACS). Para fazer isso, o módulo Azure Active Directory para Windows PowerShell cmdlets já deve estar instalado. Se não estiver instalado, vá para instalar o módulo [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) Azure Active Directory para Windows PowerShell. Conclua as etapas a seguir após Azure Active Directory módulo Windows PowerShell for instalado.

1. Clique no **Azure Active Directory módulo Windows PowerShell** atalho para abrir um espaço de trabalho Windows PowerShell que tenha os cmdlets do Azure AD instalados. Todos os comandos nesta etapa serão executados usando o Windows PowerShell para Azure Active Directory console.

2. Salve o texto a seguir em um arquivo de script do PowerShell chamado, por exemplo,  `UploadAuthCert.ps1` .

   ```powershell
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

3. Execute o script do PowerShell criado na etapa anterior. Por exemplo:  `.\UploadAuthCert.ps1`

4. Depois de iniciar o script, uma caixa de diálogo de credenciais é exibida. Insira as credenciais da conta de administrador de locatários da sua organização do Microsoft Online Azure AD. Depois de executar o script, deixe o Windows PowerShell para a sessão do Azure AD aberta. Você usará isso para executar um script do PowerShell na próxima etapa.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Etapa 6: Verificar se o certificado foi carregado na entidade Skype for Business Service Principal
1. No PowerShell aberto e autenticado para Azure Active Directory, execute o seguinte
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Pressione Enter quando solicitado para ReturnKeyValues
3. Confirme se você vê uma chave listada com data de início e dados de término que corresponde às datas de início e término do certificado Exchange Oauth

### <a name="verify-your-success"></a>Verificar seu sucesso

Verifique se a configuração está correta verificando se alguns dos recursos estão funcionando com êxito. 

1. Confirme se Skype for Business usuários com o serviço Caixa postal na Nuvem, em uma organização com uma configuração Híbrida Exchange Server, podem alterar com êxito suas saudações de caixa postal.

2. Confirme se o histórico da conversa para clientes móveis está visível na pasta Histórico Outlook Conversa.

3. Confirme se as mensagens de chat arquivadas são depositadas na caixa de correio local do usuário na pasta Limpezas usando [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).

Como alternativa, veja seu tráfego. O tráfego em um handshake OAuth é realmente distinto (e não se parece com a autenticação Básica), particularmente ao redor de realms, onde você começará a ver o tráfego do emissor com esta aparência: 000000004-0000-0ff1-ce00-0000000000000@ (às vezes com um / antes do sinal @), nos tokens que estão sendo passados. Você não verá um nome de usuário ou senha, que é o ponto de OAuth. Mas você verá o emissor "Office" – nesse caso ,4" é Skype for Business – e o domínio da sua assinatura.

Se você quiser ter certeza de que está usando o OAuth com êxito, certifique-se de saber o que esperar e saber como o tráfego deve ser. Portanto, veja o que esperar [,](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)aqui está um exemplo bastante padrão do tráfego [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  em um aplicativo da Microsoft (realmente útil para ler, embora ele não use tokens refresh) e há extensões fiddler que permitirão que você procure seu OAuth JWT (Token Web JSON).

Aqui está um exemplo [de configuração de](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)um , mas você pode usar qualquer ferramenta de rastreamento de rede que você gosta para realizar esse processo.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a autenticação OAuth entre organizações do Exchange e do Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)