---
title: Implantar clientes baixáveis da Web em Skype for Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: Implante o Skype for Business Web App e Skype de reuniões usados com Skype for Business.'
ms.openlocfilehash: 1592a5634257867fc5acb904c474cab5a36520ef
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403555"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implantar clientes baixáveis da Web em Skype for Business Server

**Resumo:** Implante o Skype for Business Web App 2015 e o Skype reuniões usados com Skype for Business Server.

Skype for Business Web App é um cliente web Serviços de Informações da Internet (IIS) instalado no servidor que executa o Skype for Business Server e, por padrão, ele é implantado sob demanda para atender usuários que ainda não têm o Skype for Business cliente. Esses usuários de reunião estão mais frequentemente do que não se conectando de fora da sua rede. Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente Skype for Business instalado, o usuário é apresentado com a opção de ingressar na reunião usando a versão mais recente do Skype for Business Web App, Skype Meetings App ou Skype for Business para Mac.

Os recursos de voz, vídeo e compartilhamento no Skype for Business Web App exigem um controle microsoft ActiveX que é usado como um plug-in pelo navegador do usuário. Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, o que acontece na primeira vez que eles usam Skype for Business Web App ou na primeira vez que acessam um recurso que requer o controle ActiveX.

> [!NOTE]
> Em Skype for Business Server implantações do Servidor de Borda, um proxy reverso HTTPS na rede de perímetro é necessário para Skype for Business Web App cliente. Também é necessário publicar URLs simples. Para obter detalhes, consulte [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar a autenticação multifa factor para Skype for Business Web App
<a name="MFA"> </a>

Skype for Business Web App, Skype De reuniões e Skype for Business para Mac suportam autenticação multifa factor. Além do nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários que estão inscritas em redes externas quando eles entrarem em reuniões Skype for Business. Você pode habilitar a autenticação multifabilitar implantando o servidor de federação do Serviço de Federação do Active Directory (AD FS) e habilitando a autenticação passiva no Skype for Business Server. Após a configuração do AD FS, os usuários externos que tentam ingressar em reuniões Skype for Business são apresentados com uma página da Web de autenticação multifato do AD FS que contém o nome de usuário e o desafio de senha, juntamente com quaisquer métodos de autenticação adicionais que você configurou.

> [!IMPORTANT]
> As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:

- A autenticação ADFS multifato funciona se o participante e o organizador da reunião estão na mesma organização ou são ambos de uma organização federada do AD FS. A autenticação ADFS de vários fatores não funciona para usuários federados do Lync porque a infraestrutura web do servidor Lync atualmente não dá suporte a ela.

- Se você usar balanceadores de carga de hardware, habilita a persistência de cookie nos balanceadores de carga para que todas as solicitações dos clientes do aplicativo Skype for Business Web App reuniões sejam manipuladas pelo mesmo Servidor front-end.

- Ao estabelecer uma confiança de parte confiável entre Skype for Business Server e servidores do AD FS, atribua uma vida de token que seja longa o suficiente para abranger o comprimento máximo de suas reuniões Skype for Business de segurança. Normalmente, uma vida de token de 240 minutos é suficiente.

- Essa configuração não se aplica aos clientes móveis do Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar a autenticação multifa factor

1. Instale uma função de servidor de federação do AD FS. Para obter detalhes, consulte o Guia de Implantação dos [Serviços de Federação do Active Directory 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. Criar certificados para o AD FS. Para obter mais informações, consulte [a seção "Certificados](/previous-versions/azure/azure-services/jj205462(v=azure.100)) do servidor de federação" do tópico Plan for and deploy AD FS for use with single sign-on topic.

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

O recurso BranchCache no Windows 7 e Windows Server 2008 R2 pode interferir com Skype for Business Web App web. Para evitar problemas para Skype for Business Web App usuários, certifique-se de que BranchCache não está habilitado.

Para obter detalhes sobre como desabilitar BranchCache, consulte o [Guia de Implantação branchCache](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verificando a Skype for Business Web App implantação
<a name="MFA"> </a>

Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API). Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) na documentação Skype for Business Server Shell de Gerenciamento.

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

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar Skype Aplicativo de Reuniões para substituir Skype for Business Web App (Opcional, Skype for Business Server 2015 somente)
<a name="SMA_Enable"> </a>

Este procedimento é opcional e se aplica Skype for Business Server 2015 CU5 e posterior. Se você não usá-lo, os usuários externos continuarão a participar de reuniões usando Skype for Business Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar o aplicativo de Skype reuniões simplificadas

1. Quando você habilita o acesso ao Rede de Distribuição de Conteúdo (CDN), os usuários terão a capacidade de se conectar ao CDN online e obter o Skype Meetings App (no Windows) e Skype for Business para Mac  (no Mac) e usará a experiência de junção de reunião simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir que a telemetria de registro em log do lado do cliente da página da Web de junção de reunião ou o aplicativo de reuniões do Skype seja enviado para servidores Microsoft (o comando padrão é false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    As informações enviadas à Microsoft estão em estrita conformidade [com Skype for Business de coleta de dados](/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Desempacotar o tempo Skype for Business Web App experiência hospedada localmente se CDN não estiver disponível. O valor padrão é 6 segundos. Se esse valor for definido como 0, não haverá tempo de vida.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Com MeetingUxUseCdn Skype for Business Server Atualização Cumulativa 5 de 2015, o valor padrão é definido como False. Isso causa um problema em que Skype for Business para Mac cliente não consegue ingressar em reuniões de parceiros não federados como convidado, mesmo que o administrador do Skype for Business tenha definido MeetingUxUseCdn como True. Para que isso funcione, Skype for Business Server 2015 deve ter a Atualização Cumulativa 7, 6.0.9319.534 ou posterior. Consulte [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Confira também
<a name="SMA_Enable"> </a>

[Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar a página de junção de reunião Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Declaração de Privacidade dos Serviços Online da Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Termos de licenciamento e documentação](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)