---
title: Implantar clientes baixáveis da Web no Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: Implante o Aplicativo Web do Skype for Business e o Aplicativo de Reuniões do Skype usado com o Skype for Business.'
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122125"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implantar clientes baixáveis da Web no Skype for Business Server

**Resumo:** Implante o Aplicativo Web do Skype for Business 2015 e o Aplicativo de Reuniões do Skype usado com o Skype for Business Server.

O Skype for Business Web App é um cliente Web do Serviços de Informações da Internet (IIS) instalado no servidor que executa o Skype for Business Server e, por padrão, é implantado sob demanda para atender usuários que ainda não têm o cliente skype for Business. Esses usuários de reunião estão mais frequentemente do que não se conectando de fora da sua rede. Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente skype for Business instalado, o usuário é apresentado com a opção de ingressar na reunião usando a versão mais recente do Skype for Business Web App, Skype Meetings App ou Skype for Business para Mac.

Os recursos de voz, vídeo e compartilhamento no Skype for Business Web App exigem um controle microsoft ActiveX que é usado como um plug-in pelo navegador do usuário. Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, o que acontece na primeira vez que eles usam o Skype for Business Web App ou a primeira vez que acessam um recurso que exige o controle ActiveX.

> [!NOTE]
> Nas implantações do Servidor de Borda do Skype for Business Server, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso do cliente do Skype for Business Web App. Também é necessário publicar URLs simples. Para obter detalhes, consulte [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and DNS requirements for simple [URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar a autenticação multifabilitar para o Skype for Business Web App
<a name="MFA"> </a>

O Skype for Business Web App, o Aplicativo de Reuniões do Skype e o Skype for Business para Mac suportam a autenticação multifa factor. Além do nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários que estão inscritas em redes externas ao entrar em reuniões do Skype for Business. Você pode habilitar a autenticação multifabilitar implantando o servidor de federação do Serviço de Federação do Active Directory (AD FS) e habilitando a autenticação passiva no Skype for Business Server. Após a configuração do AD FS, os usuários externos que tentam ingressar em reuniões do Skype for Business são apresentados com uma página da Web de autenticação multifato do AD FS que contém o nome de usuário e o desafio de senha, juntamente com quaisquer métodos de autenticação adicionais que você configurou.

> [!IMPORTANT]
> As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:

- A autenticação ADFS multifato funciona se o participante e o organizador da reunião estão na mesma organização ou são ambos de uma organização federada do AD FS. A autenticação ADFS de vários fatores não funciona para usuários federados do Lync porque a infraestrutura web do servidor Lync atualmente não dá suporte a ela.

- Se você usar balanceadores de carga de hardware, habilita a persistência de cookie nos balanceadores de carga para que todas as solicitações dos clientes do Skype for Business Web App ou do Aplicativo de Reuniões sejam manipuladas pelo mesmo Servidor front-end.

- Ao estabelecer uma confiança de parte confiável entre o Skype for Business Server e os servidores do AD FS, atribua uma vida de token que seja longa o suficiente para abranger o comprimento máximo de suas reuniões do Skype for Business. Normalmente, uma vida de token de 240 minutos é suficiente.

- Essa configuração não se aplica aos clientes móveis do Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar a autenticação multifa factor

1. Instale uma função de servidor de federação do AD FS. Para obter detalhes, consulte o Guia de Implantação dos [Serviços de Federação do Active Directory 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. Criar certificados para o AD FS. Para obter mais informações, consulte a seção ["Certificados](/previous-versions/azure/azure-services/jj205462(v=azure.100)) do servidor de federação" do tópico Plan for and deploy AD FS for use with single sign-on topic.

3. Na interface Windows PowerShell linha de comando, execute o seguinte comando:

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

## <a name="disable-branchcache"></a>Desabilitar BranchCache
<a name="MFA"> </a>

O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes web do Skype for Business Web App. Para evitar problemas para usuários do Skype for Business Web App, certifique-se de que BranchCache não está habilitado.

Para obter detalhes sobre como desabilitar BranchCache, consulte o [Guia de Implantação branchCache.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verificando a implantação do Skype for Business Web App
<a name="MFA"> </a>

Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API). Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) na documentação do Shell de Gerenciamento do Skype for Business Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solução de problemas de instalação de plug-in no Windows Server 2008 R2
<a name="MFA"> </a>

Se a instalação do plug-in falhar em um computador que executa o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do Registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar a configuração de segurança no Internet Explorer

1. Abra o Internet Explorer.

2. Clique em **Ferramentas**, **Opções da Internet** e em **Avançado**.

3. Role até a seção **Segurança**.

4. Desmarque **Não salvar páginas criptografadas no disco** e clique em **OK**.

    > [!NOTE]
    > Se selecionada, essa configuração também causará um erro ao tentar baixar um anexo do Skype for Business Web App.

5. Reingresse na reunião. O download do plug-in deve ocorrer sem erros.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar a configuração DisableMSI Registry

1. Clique em **Iniciar** e em **Executar**.

2. Para acessar o Editor de registro, digite **regedit**.

3. Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.

5. Reingresse na reunião.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar o Aplicativo de Reuniões do Skype para substituir o Skype for Business Web App (Opcional, Somente Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Este procedimento é opcional e se aplica ao Skype for Business Server 2015 CU5 e posterior. Se você não usá-lo, os usuários externos continuarão a participar de reuniões usando o Skype for Business Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar a junção de reuniões simplificadas e o Aplicativo de Reuniões do Skype

1. Quando você habilita o acesso à Rede de Entrega de Conteúdo (CDN), os usuários terão a capacidade de se conectar à CDN online e obter o Skype Meetings App (no Windows) e o Skype for Business para Mac (no Mac) e usarão a experiência de junção de reunião simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir que a telemetria de registro em log do lado do cliente da página da Web de junção de reunião ou o Aplicativo de Reuniões do Skype seja enviada aos servidores microsoft (o comando padrão é false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    As informações enviadas à Microsoft estão em estrita conformidade com as práticas de coleta de dados [do Skype for Business.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Desembolse o tempo de tempo antes de voltar para a experiência do Skype for Business Web App hospedada localmente se a CDN não estiver disponível. O valor padrão é 6 segundos. Se esse valor for definido como 0, não haverá tempo de vida.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Com MeetingUxUseCdn no Skype for Business Server 2015 Cumulative Update 5, o valor padrão é definido como False. Isso causa um problema em que o cliente skype for Business para Mac não pode participar de reuniões de parceiros não federados como convidado, mesmo que o Administrador do Skype for Business tenha definido MeetingUxUseCdn como True. Para que isso funcione, o Skype for Business Server 2015 deve ter a Atualização Cumulativa 7, 6.0.9319.534 ou posterior. Consulte [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Confira também
<a name="SMA_Enable"> </a>

[Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar a página de junção de reunião no Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Declaração de Privacidade dos Serviços Online da Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Termos de licenciamento e documentação](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)