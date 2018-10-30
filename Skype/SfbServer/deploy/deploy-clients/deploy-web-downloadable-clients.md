---
title: Implantar clientes para download da Web no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: Implante o Skype para negócios Web App e Skype App de reuniões usado com Skype para negócios.'
ms.openlocfilehash: 13facacfc2e42ec45e29aae1c1006c792ef6ac1e
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839223"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implantar clientes para download da Web no Skype para Business Server

**Resumo:** Implante o Skype para negócios 2015 Web App e Skype reuniões App usado com Skype para Business Server 2015.

Skype para negócios Web App é um cliente de web do Internet Information Services (IIS) que está instalado no servidor que executa o Skype para Business Server 2015 e por padrão, ele é implantado por demanda aos usuários de reunião que ainda não tiver o Skype para o cliente de negócios. Esses usuários de reunião são mais frequência que não se conectando de fora da rede. Sempre que um usuário clica em uma URL de reunião, mas não tem o Skype para o cliente de negócios instalado, o usuário é apresentado com a opção para ingressar na reunião usando a versão mais recente do Skype para negócios Web App ou aplicativo de reuniões do Skype.

Recursos de voz, vídeo e compartilhamento em Skype para negócios Web App requerem um controle Microsoft ActiveX que é usado como um plug-in pelo navegador do usuário. Você pode instalar o controle ActiveX antecipadamente ou permitir que os usuários instalem-quando solicitado, o que acontece na primeira vez que eles usam Skype para negócios Web App ou na primeira vez que eles acessem um recurso que requer que o controle ActiveX.

> [!NOTE]
> Skype para implantações de servidor de borda de 2015 Business Server, um proxy reverso de HTTPS na rede de perímetro será necessário para Skype para acesso de cliente de negócios Web App. Você também deve publicar URLs simples. Para obter detalhes, consulte [Configuração Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) e [requisitos de DNS para URLs simples no Skype para Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar a autenticação multifator para Skype para negócios Web App
<a name="MFA"> </a>

O Skype para negócios Web App e Skype reuniões App oferecem suporte a autenticação multifator. Além do nome de usuário e senha, você pode exigir que os métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar os usuários que estão ingressando a partir de redes externas quando entrarem no Skype para reuniões de negócios. Você pode habilitar a autenticação multifator Implantando o servidor de Federação do serviço de Federação do Active Directory (AD FS) e habilitando autenticação passiva no Skype para Business Server. Depois que o AD FS estiver configurado, os usuários externos que tentarem ingressar Skype para reuniões de negócios são apresentados com uma AD FS a autenticação multifator página da Web que contém o nome de usuário e senha desafiar junto com quaisquer métodos de autenticação adicional que você configurou.

> [!IMPORTANT]
> As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:

- A autenticação multifator do ADFS funciona se o participante e o organizador da reunião estiverem na mesma organização ou forem de uma organização federada do AD FS. A autenticação do ADFS de vários fatores não funciona para usuários federados do Lync porque a infraestrutura da Web do servidor do Lync não dà suporte à ela atualmente.

- Se você usar os balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as requisições do Skype para clientes corporativos Web App ou aplicativo de reuniões são manipuladas pelo mesmo servidor Front-End.

- Quando se estabelece uma terceira parte confiável entre Skype para servidores Business Server e o AD FS, atribua uma token vida que é grande o suficiente para abranger o comprimento máximo do seu Skype para reuniões de negócios. Normalmente, uma vida de token de 240 minutos é suficiente.

- Esta configuração não se aplica aos clientes móveis do Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar a autenticação multifator

1. Instale uma função de servidor de federação AD FS. Para obter detalhes, consulte o [Guia de implantação do Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Crie certificados para o AD FS. Para obter mais informações, consulte a seção ["Certificados de servidor de federação"](https://go.microsoft.com/fwlink/p/?LinkId=285376) do plano para e implantar o AD FS para uso com o tópico de logon único.

3. Da interface de linha de comando do Windows PowerShell, execute o seguinte comando:

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Estabeleça uma parceria executando o seguinte comando:

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Defina as seguintes regras de confiabilidade de parte:

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Desabilitar o BranchCache 
<a name="MFA"> </a>

O recurso BranchCache no Windows 7 e Windows Server 2008 R2 pode interferir Skype de componentes da web de negócios Web App. Para evitar problemas de Skype para usuários corporativos Web App, certifique-se de que o BranchCache não está habilitado.

Para obter detalhes sobre como desabilitar o BranchCache, consulte o [Guia de implantação do BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verificando Skype para implantação de aplicativo Web de negócios
<a name="MFA"> </a>

Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API). Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) no Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solucionando problemas de instalação de plug-in no Windows Server 2008 R2
<a name="MFA"> </a>

Se a instalação do plug-in falhar em um computador executando o Windows Server 2008 R2, você pode precisar modificar a configuração de segurança do Internet Explorer ou a configuração da chave do registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar a configuração de segurança no Internet Explorer

1. Abra o Internet Explorer.

2. Clique em **Ferramentas **, em **Opções da Internet ** e em **Avançado **.

3. Role para baixo até a seção **Segurança **.

4. Desmarque **Não salvar páginas criptografadas no disco ** e clique em **OK **.

    > [!NOTE]
    > Se selecionado, esta configuração também causará um erro ao tentar baixar um anexo do Skype para negócios Web App.

5. Reingresse na reunião. O download do plug-in deve ocorrer sem erros.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar a configuração do Registro DisableMSI

1. Clique em  **Iniciar ** e em  **Executar **.

2. Para acessar o Editor do Registro, digite **regedit **.

3. Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.

5. Reingresse na reunião.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar o aplicativo de reuniões do Skype substituir Skype para negócios Web App (opcional, Skype para negócios 2015 de servidor somente)
<a name="SMA_Enable"> </a>

Esse procedimento é opcional e se aplica a Skype para Business Server 2015 CU5 e posterior. Se você não usá-lo, os usuários externos continuarão participar de reuniões usando Skype para negócios Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar ingresso em reunião simplificado e Aplicativo Reuniões do Skype

1. Quando você habilita o acesso à rede conteúdo de entrega (CDN), os usuários terão a capacidade de conectar ao CDN online e obtenha Skype reuniões App e usará o simplificado experiência de participação da reunião.

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir que o cliente telemetria de registro em log do lado da reunião ingressar em página da web ou o aplicativo de reuniões do Skype sejam enviadas aos servidores da Microsoft (os padrões de comando como false).

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    As informações enviadas à Microsoft estão em estrita conformidade com as [práticas de coleta de dados do Skype for Business](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Defina o tempo limite antes de queda de volta para o Skype hospedado localmente para a experiência de negócios Web App se CDN não estiver disponível. O valor padrão é de seis segundos. Se esse valor estiver definido como 0, não haverá tempo limite.

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Ver também
<a name="SMA_Enable"> </a>

[Planejar para clientes de reuniões (Web App e reuniões App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar a reunião página de ingresso em Skype para Business Server](../../manage/conferencing/meeting-join-page.md)

[Declaração de privacidade do Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Termos de licenciamento e documentação](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)