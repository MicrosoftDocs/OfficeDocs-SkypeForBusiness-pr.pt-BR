---
title: Integração entre o Skype for Business Online e o Exchange Server
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configurar a autenticação OAuth entre o Exchange local e o Skype for Business Online habilita os recursos de Integração do Skype for Business e do Exchange descritos no suporte a recursos.
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886638"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server 

Configurar a integração entre o Exchange Server e o Skype for Business Online habilita os recursos de Integração do Skype for Business e do Exchange descritos no [suporte a recursos](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tópico se aplica à integração com o Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para a conclusão da tarefa: 15 minutos

-  Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver quais permissões você precisa, consulte o tópico de permissões de [infraestrutura do Exchange e do Shell](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) .

- Para informações sobre atalhos de teclado que possam se aplicar aos procedimentos neste tópico, confira [Atalhos de teclado no Centro de Administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Para obter informações sobre compatibilidade, consulte [a compatibilidade do Skype for Business com aplicativos do Office](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar a integração entre o Exchange Server e o O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Etapa 1: Configurar a autenticação OAuth entre o Exchange Server e o O365

Execute as etapas no seguinte artigo:

[Configurar a autenticação OAuth entre organizações do Exchange e do Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Etapa 2: Criar uma nova conta de Usuário de Email para o Aplicativo de Parceiros do Skype for Business Online

Esta etapa é feita no servidor Exchange. Ele criará um usuário de email e atribuirá a ele os direitos de função de gerenciamento apropriados. Essa conta será usada na próxima etapa.

Especifique um domínio verificado para sua organização do Exchange. Esse domínio deve ser o mesmo domínio usado como o domínio SMTP primário usado para as contas locais do Exchange. Esse domínio é conhecido como \<your Verified Domain\> no procedimento a seguir. Além disso, ele \<DomainControllerFQDN\> deve ser o FQDN de um controlador de domínio.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Esse comando ocultará o novo usuário de email das listas de endereços.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Etapa 3: Criar e habilitar um aplicativo de parceiro para o Skype for Business Online 

Crie um novo aplicativo de parceiro e usará a conta que você acabou de criar. Execute o seguinte comando no Exchange PowerShell em sua organização local do Exchange.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Etapa 4: Exportar o certificado de autorização local

Execute um script do PowerShell para exportar o certificado de autorização local, que você importará para sua organização do Skype for Business Online na próxima etapa.

Salve o seguinte texto em um script do PowerShell chamado, por exemplo, de ExportAuthCert.ps1.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

No Exchange PowerShell em sua organização local do Exchange, execute o script do PowerShell que você acabou de criar. Por exemplo: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Etapa 5: Carregar o certificado de autorização local para o ACS do Azure Active Directory

Em seguida, use o Windows PowerShell para carregar o certificado de autorização local que você exportou na etapa anterior para o ACS (Serviços de Controle de Acesso) do Azure Active Directory. Para fazer isso, os cmdlets do Módulo do Azure Active Directory para Windows PowerShell já devem estar instalados. Se ele não estiver instalado, vá para [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) instalar o Módulo do Azure Active Directory para Windows PowerShell. Conclua as etapas a seguir após a instalação do Módulo do Azure Active Directory para Windows PowerShell.

1. Clique no **atalho módulo do Azure Active Directory para Windows PowerShell** para abrir um workspace do Windows PowerShell que tenha os cmdlets do Azure AD instalados. Todos os comandos nesta etapa serão executados usando o Console do Windows PowerShell para Azure Active Directory.

2. Salve o texto a seguir em um arquivo de script do PowerShell chamado, por exemplo,  `UploadAuthCert.ps1`.

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Execute o script do PowerShell criado na etapa anterior. Por exemplo:  `.\UploadAuthCert.ps1`

4. Depois de iniciar o script, uma caixa de diálogo de credenciais é exibida. Insira as credenciais para a conta de administrador de locatários da sua organização do Microsoft Online Azure AD. Depois de executar o script, deixe a sessão do Windows PowerShell para Azure AD aberta. Você usará isso para executar um script do PowerShell na próxima etapa.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Etapa 6: Verificar se o certificado foi carregado na entidade de serviço do Skype for Business
1. No PowerShell aberto e autenticado no Azure Active Directory, execute o seguinte

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. Pressione Enter quando solicitado para ReturnKeyValues
3. Confirme se você vê uma chave listada com os dados de data de início e de término que correspondem às datas de início e término do certificado Oauth do Exchange

### <a name="verify-your-success"></a>Verificar seu sucesso

Verifique se a configuração está correta verificando se alguns dos recursos estão funcionando com êxito. 

1. Confirme se os usuários do Skype for Business com o serviço caixa postal na nuvem, em uma organização com uma configuração híbrida do Exchange Server, podem alterar com êxito suas saudações de caixa postal.

2. Confirme se o histórico de conversas para clientes móveis está visível na pasta Histórico da Conversa do Outlook.

3. Confirme se as mensagens de chat arquivadas são depositadas na caixa de correio local do usuário na pasta Limpezas usando [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).

Como alternativa, examine o tráfego. O tráfego em um handshake do OAuth é realmente distinto (e não se parece com a autenticação Básica), especialmente em torno de realms, onde você começará a ver o tráfego do emissor com esta aparência: 000000004-0000-0ff1-ce00-000000000000@ (às vezes com um /antes do sinal @), nos tokens que estão sendo passados. Você não verá um nome de usuário ou senha, que é o ponto do OAuth. Mas você verá o emissor do 'Office' – neste caso, '4' é o Skype for Business – e o realm da sua assinatura.

Se você quiser ter certeza de que está usando o OAuth com êxito, certifique-se de saber o que esperar e saber qual deve ser a aparência do tráfego. Portanto, aqui está o que [esperar, aqui](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34) está um exemplo bastante padrão de tráfego [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  em um aplicativo da Microsoft (realmente útil para ler, embora ele não use tokens de atualização) e há extensões fiddler que permitirão que você examine o JWT do OAuth (Token Web JSON).

Aqui está um exemplo [de configuração](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), mas você pode usar qualquer ferramenta de rastreamento de rede que desejar para realizar esse processo.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a autenticação OAuth entre organizações do Exchange e do Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
