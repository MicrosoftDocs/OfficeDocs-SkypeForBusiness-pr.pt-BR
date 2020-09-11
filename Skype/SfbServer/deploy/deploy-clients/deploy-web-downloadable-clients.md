---
title: Implantar clientes para download da Web no Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: implantar o Skype for Business Web App e o aplicativo de reuniões do Skype usado com o Skype for Business.'
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429417"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implantar clientes para download da Web no Skype for Business Server

**Resumo:** Implante o aplicativo Web do Skype for Business 2015 e o aplicativo de reuniões do Skype usado com o Skype for Business Server.

O Skype for Business Web App é um cliente da Web do IIS (serviços de informações da Internet) instalado no servidor que executa o Skype for Business Server e, por padrão, é implantado por demanda para atender aos usuários que ainda não têm o cliente Skype for Business. Esses usuários da reunião são mais frequentes do que não se conectar de fora da sua rede. Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente Skype for Business instalado, o usuário recebe a opção de participar da reunião usando a versão mais recente do Skype for Business Web App, o aplicativo de reuniões do Skype ou o Skype for Business para Mac.

Os recursos de voz, vídeo e compartilhamento no Skype for Business Web App requerem um controle ActiveX da Microsoft usado como um plug-in do navegador do usuário. Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, que ocorre na primeira vez em que usam o Skype for Business Web App ou na primeira vez que acessam um recurso que requer o controle ActiveX.

> [!NOTE]
> Nas implantações do servidor de borda do Skype for Business Server, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso do cliente do Skype for Business Web App. Também é necessário publicar URLs simples. Para obter detalhes, consulte [setting up Reverse proxy servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS Requirements for Simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar a autenticação multifator para o Skype for Business Web App
<a name="MFA"> </a>

O Skype for Business Web App, o aplicativo de reuniões do Skype e o Skype for Business para Mac oferecem suporte à autenticação multifator. Além de nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar os usuários que estão participando de redes externas ao entrarem em reuniões do Skype for Business. Você pode habilitar a autenticação multifator implantando o servidor de Federação do serviço de Federação do Active Directory (AD FS) e habilitando a autenticação passiva no Skype for Business Server. Após a configuração do AD FS, os usuários externos que tentarem participar de reuniões do Skype for Business são apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e a senha desafio, juntamente com quaisquer métodos de autenticação adicionais que você tenha configurado.

> [!IMPORTANT]
> As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:

- A autenticação do ADFS multifator funcionará se o participante da reunião e o organizador estiverem na mesma organização ou ambos de uma organização federada do AD FS. A autenticação ADFS multifator não funciona para usuários federados do Lync porque a infraestrutura da Web do Lync Server atualmente não oferece suporte a ele.

- Se você usar balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as solicitações do cliente de aplicativos Web App ou de reuniões do Skype for Business sejam tratadas pelo mesmo servidor de front-end.

- Ao estabelecer uma confiança de terceira parte confiável entre o Skype for Business Server e os servidores AD FS, atribua uma vida útil de token que seja longa o suficiente para abranger o tamanho máximo de suas reuniões do Skype for Business. Normalmente, uma vida de token de 240 minutos é suficiente.

- Essa configuração não se aplica aos clientes móveis do Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar a autenticação multifator

1. Instale uma função de servidor de federação do AD FS. Para obter detalhes, consulte o [Guia de implantação do serviços de Federação do Active Directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Criar certificados para o AD FS. Para obter mais informações, consulte a seção ["certificados do servidor de Federação"](https://go.microsoft.com/fwlink/p/?LinkId=285376) do tópico planejar e implantar o AD FS para uso com o logon único.

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

O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes Web do Skype for Business Web App. Para evitar problemas para usuários do Skype for Business Web App, verifique se o BranchCache não está habilitado.

Para obter detalhes sobre como desabilitar o BranchCache, consulte o [Guia de implantação do BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verificando a implantação do Skype for Business Web App
<a name="MFA"> </a>

Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API). Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) na documentação do Shell de gerenciamento do Skype for Business Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solucionando problemas de instalação de plug-in no Windows Server 2008 R2
<a name="MFA"> </a>

Se a instalação do plug-in falhar em um computador executando o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar a configuração de segurança no Internet Explorer

1. Abra o Internet Explorer.

2. Clique em **Ferramentas**, **Opções da Internet** e em **Avançado**.

3. Role até a seção **Segurança**.

4. Desmarque **Não salvar páginas criptografadas no disco** e clique em **OK**.

    > [!NOTE]
    > Se for selecionada, essa configuração também causará um erro ao tentar baixar um anexo do Skype for Business Web App.

5. Reingresse na reunião. O download do plug-in deve ocorrer sem erros.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar a configuração do registro DisableMSI

1. Clique em **Iniciar** e em **Executar**.

2. Para acessar o Editor de registro, digite **regedit**.

3. Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.

5. Reingresse na reunião.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar o aplicativo de reuniões do Skype para substituir o Skype for Business Web App (opcional, Skype for Business Server 2015 apenas)
<a name="SMA_Enable"> </a>

Este procedimento é opcional e se aplica ao Skype for Business Server 2015 CU5 e posterior. Se você não usá-lo, os usuários externos continuarão a participar de reuniões usando o Skype for Business Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar o ingresso em reunião simplificada e o aplicativo reuniões do Skype

1. Quando você habilita o acesso à rede de distribuição de conteúdo (CDN), os usuários terão a capacidade de se conectar à CDN online e obter o aplicativo de reuniões do Skype (no Windows) e o Skype for Business para Mac (no Mac) e usarão a experiência de junção de reunião simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir a telemetria de registro no cliente da página de ingresso na reunião ou do aplicativo de reuniões do Skype para ser enviado aos servidores da Microsoft (o comando padrão é false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    As informações enviadas à Microsoft estão em conformidade estrita com a [privacidade e o Microsoft Teams](../../../../Teams/teams-privacy.md).

3. Defina o tempo limite antes de voltar para a experiência do aplicativo Web do Skype for Business hospedado localmente, se a CDN não estiver disponível. O valor padrão é 6 segundos. Se esse valor for definido como 0, não haverá tempo limite.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Com o MeetingUxUseCdn na atualização cumulativa 5 do Skype for Business Server 2015, o valor padrão é definido como false. Isso causa um problema em que o cliente do Skype for Business para Mac não consegue ingressar em reuniões de parceiros não federados como convidados, mesmo que o administrador do Skype for Business tenha definido MeetingUxUseCdn como true. Para que isso funcione, o Skype for Business Server 2015 deve ter a atualização cumulativa 7, 6.0.9319.534 ou posterior. Consulte [habilitar o aplicativo de reuniões do Skype para substituir o Skype for Business Web App no Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Confira também
<a name="SMA_Enable"> </a>

[Plano para clientes de reuniões (aplicativo Web e aplicativos de reuniões)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar a página de ingresso na reunião no Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Declaração de Privacidade dos Serviços Online da Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Termos e documentação de licenciamento](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
