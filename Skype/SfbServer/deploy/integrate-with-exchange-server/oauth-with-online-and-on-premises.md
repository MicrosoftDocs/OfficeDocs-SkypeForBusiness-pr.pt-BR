---
title: Integração entre o Skype for Business Online e o Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: A configuração da autenticação OAuth entre o Exchange local e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em suporte a recursos.
ms.openlocfilehash: 35dc8777ddf5c7102e99d726f916f9b8f8bb4aae
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002891"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server 

A configuração da integração entre o Exchange Server e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em [suporte a recursos](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tópico se aplica à integração com o Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para concluir esta tarefa: 15 minutos

-  Você precisa receber permissões antes de realizar esse procedimento ou procedimentos. Para ver quais permissões você precisa, consulte o tópico [permissões de infraestrutura do Shell e do Exchange](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Para obter informações sobre os atalhos de teclado que podem ser aplicáveis aos procedimentos deste tópico, consulte [atalhos de teclado no centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Para obter informações sobre compatibilidade, confira [compatibilidade do Skype for Business com os aplicativos do Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar a integração entre o Exchange Server e o O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Etapa 1: configurar a autenticação OAuth entre o Exchange Server e o O365

Execute as etapas do seguinte artigo:

[Configurar a autenticação OAuth entre organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Etapa 2: criar uma nova conta de usuário de email para o aplicativo para parceiros do Skype for Business Online

Esta etapa é feita no Exchange Server. Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento. Essa conta será então usada na próxima etapa.

Especifique um domínio verificado para sua organização do Exchange. Esse domínio deve ser o mesmo usado como o domínio SMTP principal usado para as contas do Exchange no local. Esse domínio é chamado \<de domínio\> verificado no procedimento a seguir. Além disso, \<o\> DOMAINCONTROLLERFQDN deve ser o FQDN de um controlador de domínio.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Esse comando ocultará o novo usuário da caixa de correio das listas de endereços.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Esses dois próximos comandos atribuirão a função de gerenciamento de UserApplication e ArchiveApplication a esta nova conta.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Etapa 3: criar e habilitar um aplicativo parceiro para o Skype for Business Online 

Crie um novo aplicativo parceiro e use a conta que você acabou de criar. Execute o seguinte comando no PowerShell do Exchange em sua organização do Exchange local.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Etapa 4: exportar o certificado de autorização local

Execute um script do PowerShell para exportar o certificado de autorização local, que você vai importar para sua organização do Skype for Business online na próxima etapa.

Salve o seguinte texto em um arquivo de script do PowerShell denominado, por exemplo, ExportAuthCert.ps1.

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

No Exchange PowerShell em sua organização do Exchange local, execute o script do PowerShell que você acabou de criar. Por exemplo: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Etapa 5: carregar o certificado de autorização local para o ACS do Azure Active Directory

Em seguida, utilize o Windows PowerShell para carregar o certificado de autorização local que você exportou na etapa anterior no Serviço de Controle de Acesso do Azure Active Directory (ACS). Para fazer isso, o Módulo Azure Active Directory para cmdlets do Windows PowerShell já deve estar instalado. Se não estiver instalado, vá para [https://aka.ms/aadposh](https://aka.ms/aadposh) instalar o módulo Azure Active Directory para Windows PowerShell. Conclua as etapas a seguir após a instalação do módulo Azure Active Directory para Windows PowerShell.

1. Clique no atalho do **Módulo Azure Active Directory para Windows PowerShell** para abrir um espaço de trabalho do Windows PowerShell que possui os cmdlets do Azure AD instalado. Todos os comandos nesta etapa serão executados utilizando-se o Windows PowerShell para console do Azure Active Directory.

2. Salve o seguinte texto em um arquivo de script do PowerShell chamado, por `UploadAuthCert.ps1`exemplo,.

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

3. Execute o script do PowerShell criado na etapa anterior. Por exemplo:`.\UploadAuthCert.ps1`

4. Depois de iniciar o script, uma caixa de diálogo de credenciais será exibida. Insira as credenciais para a conta do administrador do locatário de sua empresa Microsoft Online Azure AD. Depois de executar o script, deixe a sessão Windows PowerShell para Azure AD aberta. Você a utilizará para executar um script do PowerShell na próxima etapa.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Etapa 6: Verifique se o certificado foi carregado na entidade de serviço do Skype for Business
1. No PowerShell aberto e autenticado para o Azure Active Directory, execute o seguinte
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Pressione Enter quando solicitado para ReturnKeyValues
3. Confirme que você vê uma chave listada com data de início e dados finais que correspondem às datas de início e término do certificado OAuth do Exchange

### <a name="verify-your-success"></a>Verifique se a operação foi realizada com sucesso

Verifique se a configuração está correta verificando se alguns dos recursos estão funcionando com êxito. 

1. Confirme se os usuários do Skype for Business com serviço de correio de voz na nuvem, em uma organização com uma configuração híbrida do Exchange Server, podem alterar suas saudações de correio de voz com êxito.

2. Confirme se o histórico de conversas para clientes móveis está visível na pasta Histórico de conversas do Outlook.

3. Confirme se as mensagens de chat arquivadas são depositadas na caixa de correio local do usuário na pasta Purges usando o [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).

Como alternativa, examine seu tráfego. O tráfego em um handshake OAuth é realmente distintivo (e não se parece com autenticação básica), especialmente em relação a territórios, onde você começará a ver o tráfego do emissor parecido com este: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes, com/antes do símbolo @), nos símbolos que estão sendo passados. Você não verá um nome de usuário ou senha, que é o ponto de OAuth. Mas você verá o emissor "Office" – neste caso, ' 4 ' é o Skype for Business – e o território da sua assinatura.

Se você quiser ter certeza de que está usando o OAuth com êxito, verifique se sabe o que esperar e saiba para que tal tráfego deve ser exibido. Portanto, [Veja o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um exemplo bem padrão [de tráfego OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (muito útil para ler, embora não use os tokens de atualização), e existem extensões Fiddler que permitem que você examine seu JWT OAuth (JSON Web token).

Veja um [exemplo de](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)como configurar um, mas você pode usar qualquer ferramenta de rastreamento de rede que você queira para empreender esse processo.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a autenticação OAuth entre organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
