---
title: 'Lync Server 2013: Implantando o Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2156466e0238a061f2358127c75408fa37e3b823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507528"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Implantando o Lync Web App no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-18_

O Lync Web App é um cliente da Web do IIS (serviços de informações da Internet) que é instalado com o Lync Server 2013 e é habilitado por padrão. Nenhuma etapa adicional é necessária para habilitar o Lync Web App no servidor ou implantar o cliente Web para os usuários. Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente Lync 2013 instalado, o usuário recebe a opção de participar da reunião usando a versão mais recente do Lync Web App.

Os recursos de voz, vídeo e compartilhamento no Lync Web App requerem um controle ActiveX da Microsoft. Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, que ocorre na primeira vez em que usam o Lync Web App ou na primeira vez que acessam um recurso que requer o controle ActiveX.

<div class=" ">


> [!NOTE]  
> Nas implantações do servidor de borda do Lync Server 2013, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso do cliente do Lync Web App. Também é necessário publicar URLs simples. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</A> e <A href="lync-server-2013-planning-for-simple-urls.md">planejando URLs simples no Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Habilitando a autenticação multifator para o Lync Web App

A versão do Lync Server 2013 do Lync Web App oferece suporte à autenticação multifator. Além de nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários que estão participando de redes externas quando eles entram nas reuniões do Lync. Você pode habilitar a autenticação multifator implantando o servidor de Federação do serviço de Federação do Active Directory (AD FS) e habilitando a autenticação passiva no Lync Server 2013. Após a configuração do AD FS, os usuários externos que tentarem ingressar em reuniões do Lync serão apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e o desafio de senha juntamente com quaisquer métodos de autenticação adicionais que você tenha configurado.

<div class=" ">


> [!IMPORTANT]  
> As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator: 
> <UL>
> <LI>
> <P>A autenticação do ADFS multifator funcionará se o participante da reunião e o organizador estiverem na mesma organização ou ambos de uma organização federada do AD FS. A autenticação ADFS multifator não funciona para usuários federados do Lync porque a infraestrutura da Web do Lync Server atualmente não oferece suporte a ele.</P>
> <LI>
> <P>Se você usar balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as solicitações do cliente do Lync Web App sejam tratadas pelo mesmo servidor de front-end.</P>
> <LI>
> <P>Ao estabelecer uma confiança de terceira parte confiável entre os servidores do Lync Server e do AD FS, atribua uma vida útil de token que seja longa o suficiente para abranger o tamanho máximo de suas reuniões do Lync. Normalmente, uma vida de token de 240 minutos é suficiente.</P>
> <LI>
> <P>Essa configuração não se aplica aos clientes móveis do Lync.</P></LI></UL>



</div>

**Configurar a autenticação multifator**

1.  Instale uma função de servidor de federação do AD FS. Para obter detalhes, consulte o guia de implantação do serviços de Federação do Active Directory 2,0 em <https://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Criar certificados para o AD FS. Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o logon único em [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .

3.  Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Estabeleça uma parceria executando o seguinte comando:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Defina as seguintes regras de confiabilidade de parte:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>Configuração de BranchCache

O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes Web do Lync Web App. Para evitar problemas para usuários do Lync Web App, verifique se o BranchCache não está habilitado.

Para obter detalhes sobre como desabilitar o BranchCache, consulte o guia de implantação do BranchCache, que está disponível no formato Word no centro de download da Microsoft em [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) e no formato HTML na biblioteca técnica do Windows Server 2008 R2 em [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) .

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Verificando a implantação do Lync Web App

Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API). Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) na documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Solucionando problemas de instalação de plug-in no Windows Server 2008 R2

Se a instalação do plug-in falhar em um computador executando o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do registro DisableMSI.

**Modificar a configuração de segurança no Internet Explorer**

1.  Abra o Internet Explorer.

2.  Clique em **Ferramentas**, **Opções da Internet** e em **Avançado**.

3.  Role até a seção **Segurança**.

4.  Desmarque **Não salvar páginas criptografadas no disco** e clique em **OK**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Se for selecionada, esta configuração também causará um erro ao tentar baixar um anexo do Lync Web App.

    
    </div>

5.  Reingresse na reunião. O download do plug-in deve ocorrer sem erros.

**Modificar a configuração do Registro DisableMSI**

1.  Clique em **Iniciar** e em **Executar**.

2.  Para acessar o Editor de registro, digite **regedit**.

3.  Navegue até HKEY \_ local \_ Machine \\ software \\ Policies \\ Microsoft \\ Windows \\ Installer.

4.  Edite ou adicione a chave do registro DisableMSI do tipo REG \_ DWORD e defina-a como 0.

5.  Reingresse na reunião.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando a página de ingresso na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Plataformas com suporte do Lync Web App para o Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

