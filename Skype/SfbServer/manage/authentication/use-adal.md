---
title: Como usar a Autenticação do modem (ADAL) com o Skype for Business
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: Este artigo explica como usar a autenticação moderno (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e OAuth 2.0) que podem ser encontradas no de 2016 março atualização cumulativa do Skype for Business para Skype para Business Server 2015.
ms.openlocfilehash: d6e78d60371b56c3a2cc959ded0ec7d7394d82cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32191520"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>How to use Modern Authentication (ADAL) with Skype for Business
 
Este artigo explica como usar a autenticação moderno (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e OAuth 2.0) que podem ser encontradas no de 2016 março atualização cumulativa do Skype for Business para Skype para Business Server 2015 ou inicial versão do Skype Business Server 2019.
  
## <a name="whats-in-this-article"></a>O que há neste artigo?

[Configurar ADAL em seu pool e definir o AD FS como servidor de token de segurança](use-adal.md#BKMK_Config)
  
[Outras opções para habilitar a entrada na ADAL (como aplicativos cliente do Office)](use-adal.md#BKMK_Options)
  
[Clientes onde a Autenticação Moderna/ADAL não é compatível](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>Configurar ADAL em seu pool e definir o AD FS como servidor de token de segurança
<a name="BKMK_Config"> </a>

Nesse processo, você pode conectar sua instalação do AD FS para uma Skype para pool de servidores de negócios que está configurado para ADAL.
  
1. Instalar o de 2016 março atualização cumulativa (ou mais recente) para Skype para negócios 2015 de servidor para seu Skype para pool de servidores corporativos ou servidor Standard Edition. (Agende as janelas de manutenção, conforme necessário, para executar o Windows Update para a instalação automática.)
    
2. Em seu local do AD FS servidor (es), [Baixe](https://aka.ms/sfbadalscripts) o programa de instalação-AdfsOAuthTrustForSfB script. (Isso precisa ser feito por farm AD FS ou servidor (es) independente do AD FS. Ele não precisa ser feito em Proxies de aplicativo da Web ou de Proxies do AD FS.)
    
3. Anote o interna e externa do serviço Web totalmente qualificados nomes de domínio (FQDNs) para sua Skype para o pool de servidores corporativos ou servidor Standard Edition. Isso precisa ser feito para todos os Pools do Skype for Business.
    
4. A partir do PowerShell em todos os servidores do AD FS, execute `Setup-AdfsOAuthTrustForSfB.ps1` (para o Windows Server 2012 R2) ou `Setup-Adfs2016OAuthTrustForSfB.ps1` (para Windows Server 2016 ou posterior). Você precisará digitar as URLs adequadas para nomes de domínio totalmente qualificado Web Service (FQDNs) internos e externos. Veja um exemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Para qualquer pools adicionais, você precisará adicionar URLs de serviços Web do Pool manualmente para o Skype para Business Server confiança da terceira parte no AD FS.
    
    > [!IMPORTANT]
    > Não é possível usar a Autenticação Passiva para um Pool e usar também a ADAL. Você deve desabilitar a Autenticação Passiva para poder usar a ADAL. Para cmdlets do PowerShell sobre como configurar a autenticação de um Pool, consulte [Este](https://technet.microsoft.com/en-us/library/gg398396.aspx) artigo.
  
    > [!TIP]
    > Se você tiver pools adicionais, que você precisa adicioná-los como [identificadores](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) para a confiança da terceira parte no AD FS.> vá para seu servidor AD FS e abra o gerenciamento do AD FS. Expanda relações de confiança \> objetos de confiança de terceiros. Clique com o botão a confiança da terceira parte que está listada e o botão direito do mouse para propriedades \> identificadores \> digite as URLs de Pool adicionais \> clique em Adicionar. 
  
5. Retorne à sua Skype para negócios servidor Front-End ou servidor Standard Edition server. A partir daqui, você deve executar cmdlets que crie um servidor OAuth e modificar essa configuração OAuth para trabalhar com Skype para negócios. Você precisará executar esta etapa uma vez por Skype para implantação de servidor de negócios. Veja um exemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > A URL de 'Identidade' você vê neste comando é realmente o AD FS Federation nome do serviço pode ser visto no gerenciamento do AD FS quando você do mouse em serviço \> propriedades. O tipo é sempre 'ADFS' e 'MetadataURL' é sempre \<seu nome de serviço do AD FS\> + "/ FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Ainda na sua Skype para negócios servidor Front-End ou servidor Standard Edition, teste a nova configuração inserindo o endereço SIP do usuário e o FQDN do pool. Você precisará executar esta etapa uma vez por Skype para implantação de servidor de negócios. Veja um exemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Quando solicitado, certifique-se de inserir as credenciais do usuário de teste. Verifique se o teste é concluído com sucesso.
    
    > [!NOTE]
    > Quando sua URL STS é resolvida para o AD FS *internamente* , o prompt que você verá será um aviso de **Segurança do Windows** . Se a URL for resolvida externamente, você verá um prompt denominado **Entrar**. Normalmente, desejamos um prompt de **Segurança do Windows** aqui. Observe que esse comportamento varia, particularmente se você implementou A Autenticação Baseada em Formulários (ou FBA).
  
Além disso, esteja ciente, quando a URL do STS resolve para um servidor interno do AD FS e a autenticação integrada do Windows está habilitada em navegadores, onde muitos usuários diferentes entram em aplicativos cliente de computadores podem ter falhas de autenticação, a menos que o navegador é explicitamente configurado para solicitar aos usuários suas credenciais em um determinado navegador zona de segurança. Como exemplo, pense em um quiosque. A conta que está conectada no sistema operacional pode ser diferente da conta que o usuário fez logon no cliente Skype for Business. Se for esse o caso, talvez você veja as falhas descritas aqui.
    
Você pode visualizar e alterar essa configuração do navegador no Internet Explorer clicando \> ferramentas (ou a engrenagem) \> opções da Internet \> guia Segurança \> e a zona de segurança (por exemplo, Intranet Local). Nessa caixa de diálogo, clique no botão Nível Personalizado e percorrer até o final da lista na caixa de diálogo Configurações. Em autenticação do usuário \> Login \> você verá uma opção para 'Prompt para nome de usuário e senha'. Se você tiver tiver quiosques nos quais o usuário que inicia o cliente Skype for Business seja diferente (possui uma conta diferente) do usuário conectado no computador, você poderá testar configurar essa opção como 'ATIVA' para essas máquinas em uma Política de Grupo.
    
Finalmente, e o mais importante, você pode experimentar mais do que um aviso uma vez que o sistema de segurança coleta as informações necessárias para autenticar ou autorizar sua conta.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Outras opções para habilitar a entrada na ADAL (como aplicativos cliente do Office)
<a name="BKMK_Options"> </a>

Agora que ADAL está configurado para seu Skype para negócios e (automaticamente) para aplicativos de cliente do Office 2016 em todas as plataformas, talvez você queira aproveitar o Exchange Online (onde ele não está 'Em' por padrão) ou nos clientes do Office 2013.
  
> [!IMPORTANT]
> Precisa saber o que esperar de entradas na Autenticação Moderna de seus aplicativos cliente? Dê uma olhada [moderno como funciona a autenticação para aplicativos de cliente do Office 2013 e Office 2016](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Para ativar a autenticação moderno para Exchange Online, você precisará executar alguns cmdlets do PowerShell. No caso de aplicativos de cliente do Office 2013, você precisará alterar algumas chaves do registro em computadores clientes.
  
- Conectar-se ao Exchange Online e execute os seguintes cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Defina essas chaves do Registro para cada dispositivo ou computador no qual você deseja habilitar a Autenticação Moderna. Você precisará de um GPO em organizações de maior porte. Para obter informações sobre como tornar um GPO, consulte a 'criar um objeto de diretiva de grupo para modificar o registro em um computador que ingressou domínio' [deste ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)artigo.
    
|Chave de Registro  <br/> |Tipo  <br/> |Valor  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Depois que essas chaves estiverem definidas, defina seus aplicativos do Office para [usar a autenticação (MFA Multifactor) com o Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Para desabilitar autenticação moderno em dispositivos do Office 2013, defina a chave de registro HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL como um valor igual a zero. Lembre-se de que uma chave de registro semelhante (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) também pode ser usada para desativar a autenticação moderno em dispositivos para 2016 do Office.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes onde a Autenticação Moderna/ADAL não é compatível
<a name="BKMK_Support"> </a>

Algumas versões de cliente não oferecem suporte a OAuth. Você pode verificar se a versão do cliente Office no Painel de Controle no qual você Adiciona e Remove programas para comparar seu número de versão com as versões (ou intervalos de versões) está listada a seguir:
  
- Cliente do Office 15.0. [0000-4766].\*
    
- Cliente do Office 16.0. [0000-4293].\*
    
- Office Client 16.0.6001.[0000-1032]
    
- Cliente do Office 16.0. [6000-6224].\*
    
> [!NOTE]
> Híbrido de autenticação moderno também está disponível com Skype For Business no local, se você deseja saber mais, visite [como configurar Skype for Business no local para usar a autenticação híbrida moderno](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)
