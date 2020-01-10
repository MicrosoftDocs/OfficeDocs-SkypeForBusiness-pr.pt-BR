---
title: Implantar clientes para download da Web no Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: implante o aplicativo Skype for Business Web App e reuniões do Skype usadas com o Skype for Business.'
ms.openlocfilehash: eb939ddf394ff62b9173939622a8ef3f20faaca9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003521"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implantar clientes para download da Web no Skype for Business Server

**Resumo:** Implante o aplicativo Web do Skype for Business 2015 e o aplicativo reuniões do Skype usado com o Skype for Business Server.

O Skype for Business Web App é um cliente Web do IIS (serviços de informações da Internet) instalado no servidor que está executando o Skype for Business Server e, por padrão, é implantado por demanda para os usuários da reunião que ainda não têm o cliente Skype for Business. Esses usuários da reunião são mais frequentes do que não se conectam de fora da sua rede. Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente Skype for Business instalado, o usuário recebe a opção de ingressar na reunião usando a versão mais recente do Skype for Business Web App, o aplicativo reuniões do Skype ou o Skype for Business para Mac.

Os recursos de voz, vídeo e compartilhamento do Skype for Business Web App exigem um controle ActiveX da Microsoft usado como um plugin pelo navegador do usuário. Você pode instalar o controle ActiveX antecipadamente ou permitir que os usuários o instalem quando solicitado, o que acontecerá na primeira vez em que usarem o Skype for Business Web App ou na primeira vez que acessar um recurso que exija o controle ActiveX.

> [!NOTE]
> Nas implantações do servidor de borda do Skype for Business Server, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso ao cliente do Skype for Business Web App. Você também deve publicar URLs simples. Para obter detalhes, consulte [Configurando servidores proxy reverso](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) e [requisitos de DNS para URLs simples no Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar a autenticação multifator para o Skype for Business Web App
<a name="MFA"> </a>

O Skype for Business Web App, o aplicativo reuniões do Skype e o Skype for Business para Mac dão suporte à autenticação de vários fatores. Além do nome de usuário e da senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar os usuários que estão participando de redes externas quando entrarem em reuniões do Skype for Business. Você pode habilitar a autenticação multifator implantando o servidor de Federação do AD FS (serviços de Federação do Active Directory) e habilitando a autenticação passiva no Skype for Business Server. Após a configuração do AD FS, os usuários externos que tentam participar de reuniões do Skype for Business são apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e o desafio de senha, juntamente com qualquer método de autenticação adicional que você configurou.

> [!IMPORTANT]
> As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:

- A autenticação multifator do ADFS funciona se o participante e o organizador da reunião estiverem na mesma organização ou forem de uma organização federada do AD FS. A autenticação do ADFS de vários fatores não funciona para usuários federados do Lync porque a infraestrutura da Web do servidor do Lync não dà suporte à ela atualmente.

- Se você usar balanceadores de carga de hardware, habilite a persistência de cookies nos balanceadores de carga para que todas as solicitações do aplicativo Skype for Business Web App ou de aplicativos de reuniões sejam manipuladas pelo mesmo servidor front-end.

- Quando você estabelece uma relação de confiança entre terceira parte confiável entre os servidores do Skype for Business e do AD FS, atribua uma vida de token longa o suficiente para abranger o tamanho máximo de suas reuniões do Skype for Business. Normalmente, uma vida de token de 240 minutos é suficiente.

- Esta configuração não se aplica aos clientes móveis do Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar a autenticação multifator

1. Instale uma função de servidor de federação AD FS. Para obter detalhes, consulte o [Guia de implantação do serviços de Federação do Active Directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Crie certificados para o AD FS. Para obter mais informações, consulte a seção ["certificados do servidor de Federação"](https://go.microsoft.com/fwlink/p/?LinkId=285376) do tópico planejar e implantar o AD FS para uso com o tópico logon único.

3. Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Estabeleça uma parceria executando o seguinte comando:

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Defina as seguintes regras de confiabilidade de parte:

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Desabilitar o BranchCache 
<a name="MFA"> </a>

O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes Web do Skype for Business Web App. Para impedir problemas para usuários do Skype for Business Web App, verifique se o BranchCache não está habilitado.

Para obter detalhes sobre como desabilitar o BranchCache, consulte o [Guia de implantação do BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verificando a implantação do Skype for Business Web App
<a name="MFA"> </a>

Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API). Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) na documentação do Shell de gerenciamento do Skype for Business Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solução de problemas de instalação do plug-in no Windows Server 2008 R2
<a name="MFA"> </a>

Se a instalação do plug-in falhar em um computador executando o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar a configuração de segurança no Internet Explorer

1. Abra o Internet Explorer.

2. Clique em **Ferramentas **, em **Opções da Internet ** e em **Avançado **.

3. Role para baixo até a seção **Segurança **.

4. Desmarque **Não salvar páginas criptografadas no disco ** e clique em **OK **.

    > [!NOTE]
    > Se selecionado, essa configuração também causará um erro ao tentar baixar um anexo do Skype for Business Web App.

5. Reingresse na reunião. O download do plug-in deve ocorrer sem erros.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar a configuração do Registro DisableMSI

1. Clique em  **Iniciar ** e em  **Executar **.

2. Para acessar o Editor do Registro, digite **regedit **.

3. Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.

5. Reingresse na reunião.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar o aplicativo reuniões do Skype para substituir o Skype for Business Web App (opcional, Skype for Business Server 2015 apenas)
<a name="SMA_Enable"> </a>

Esse procedimento é opcional e se aplica ao Skype for Business Server 2015 CU5 e posterior. Se você não usá-lo, os usuários externos continuarão a ingressar em reuniões usando o Skype for Business Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar ingresso em reunião simplificado e Aplicativo Reuniões do Skype

1. Quando você habilita o acesso à CDN (rede de distribuição de conteúdo), os usuários terão a capacidade de se conectar à CDN online e obter o aplicativo reuniões do Skype (no Windows) e o Skype for Business para Mac (no Mac) e usarão a experiência de junção de reunião simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir telemetria de log do cliente da página da Web ingressar na reunião ou do aplicativo reuniões do Skype para ser enviado para servidores da Microsoft (o comando usa como padrão false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    As informações enviadas à Microsoft estão em conformidade rigorosa com as [práticas de coleta de dados do Skype for Business](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Defina o tempo limite antes de retornar à experiência do Skype for Business Web App hospedada localmente se a CDN não estiver disponível. O valor padrão é de seis segundos. Se esse valor estiver definido como 0, não haverá tempo limite.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Com o MeetingUxUseCdn na atualização cumulativa 5 do Skype for Business Server 2015, o valor padrão é definido como false. Isso causa um problema em que o cliente do Skype for Business para Mac não consegue ingressar em reuniões de parceiros não federados como convidados, mesmo que o administrador do Skype for Business tenha definido o MeetingUxUseCdn como verdadeiro. Para que isso funcione, o Skype for Business Server 2015 deve ter a atualização cumulativa 7, 6.0.9319.534 ou posterior. Consulte [habilitar o aplicativo reuniões do Skype para substituir o Skype for Business Web App no Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Confira também
<a name="SMA_Enable"> </a>

[Plano para clientes de reuniões (aplicativo Web e aplicativo reuniões)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar a página ingressar na reunião no Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Política de privacidade do Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Termos e documentação de licenciamento](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
