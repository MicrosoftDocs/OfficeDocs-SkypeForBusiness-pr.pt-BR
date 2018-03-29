---
title: Como usar a Autenticação do modem (ADAL) com o Skype for Business
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Como usar a Autenticação do modem (ADAL) com o Skype for Business
 
This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
  
## <a name="whats-in-this-article"></a>O que há neste artigo?

[O que é ADAL?](use-adal.md#BKMK_ADAL)
  
[Configurar ADAL em seu pool e definir o ADFS como servidor de token de segurança](use-adal.md#BKMK_Config)
  
[Outras opções para habilitar a entrada na ADAL (como aplicativos cliente do Office)](use-adal.md#BKMK_Options)
  
[Clientes onde a Autenticação Moderna/ADAL não é compatível](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>O que é ADAL?
<a name="BKMK_ADAL"> </a>

ADAL é o acrônimo de “Biblioteca de Autenticação do Active Directory" e, junto com o OAuth 2.0, constitui a base da Autenticação Moderna. This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens. A ADAL interage com o OAuth 2.0 para habilitar mais cenários de autenticação e autorização, como MFA (Multi-factor Authentication), bem como mais formas de Autenticação de SAML.
  
Vários aplicativos que atuam como clientes podem aproveitar a Autenticação Moderna para obter recursos seguros. In Skype for Business Server 2015, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.
  
As conversas de Autenticação Moderna (que se baseiam em ADAL e OAuth 2.0) têm alguns elementos em comum.
  
- There is a client making a request for a resource, in this case, the client is Skype for Business.
    
- There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server 2015.
    
- There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource. (OAuth também é conhecido pelo nome mais descritivo, autenticação "Servidor a Servidor' e é frequentemente abreviado como S2S.)
    
In Skype for Business Server 2015 Modern Authentication (ADAL) conversations, Skype for Business Server 2015 communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2). A autenticação pode ser feita usando algum outro IdP (Provedor de Identidade), mas o servidor do Skype for Business precisa ser configurado para se comunicar com o ADFS diretamente. If you haven't configured ADFS to work with Skype for Business Server 2015 please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.
  
> [!NOTE]
> During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved. For example, if the environment is purely Skype for Business Server 2015. This statement may be subject to change. 
  
Um pacote do PowerShell incluindo arquivos .ps1 com os comandos usados por ADAL deve ser baixado para a configuração com êxito.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Configurar ADAL em seu pool e definir o ADFS como servidor de token de segurança
<a name="BKMK_Config"> </a>

In this process, you connect your installation of ADFS to a Skype for Business Server 2015 pool that is configured for ADAL.
  
1. Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server 2015 pool or Standard Edition server. (Agende as janelas de manutenção, conforme necessário, para executar o Windows Update para a instalação automática.)
    
2. On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script. Isso precisa ser feito por farm de ADFS ou por servidores ADFS independentes. Não precisa ser feito nos proxies ADFS.
    
3. Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server 2015 pool or Standard Edition server. Isso precisa ser feito para todos os Pools do Skype for Business.
    
4. Do PowerShell nos Servidores ADFS(s), execute o Setup-AdfsOAuthTrustForSfB. Será necessário inserir as devidas URLs dos FQDNs dos Serviços Web internos e externos. Veja um exemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server 2015 Relying Party Trust in ADFS.
    
    > [!IMPORTANT]
    > Não é possível usar a Autenticação Passiva para um Pool e usar também a ADAL. Você deve desabilitar a Autenticação Passiva para poder usar a ADAL. For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.
  
    > [!TIP]
    > If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management. Expand Trust Relationships \> Relying Party Trusts. Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add. 
  
5. Return to your Skype for Business Server 2015 Front End or Standard Edition server server. From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business. You only need to do this step once per Skype for Business Server 2015 deployment. Veja um exemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties. The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Still on your Skype for Business Server 2015 Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN. You only need to do this step once per Skype for Business Server 2015 deployment. Veja um exemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Quando solicitado, certifique-se de inserir as credenciais do usuário de teste. Verifique se o teste é concluído com sucesso.
    
    > [!NOTE]
    > When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt. Se a URL for resolvida externamente, você verá um prompt denominado **Entrar**. Normalmente, desejamos um prompt de **Segurança do Windows** aqui. Observe que esse comportamento varia, particularmente se você implementou A Autenticação Baseada em Formulários (ou FBA).
  
Saiba ainda que, quando a URL STS for resolvida para um servidor ADFS interno e a autenticação do Windows Integrada estiver habilitada nos navegadores, os computadores nos quais vários usuários diferentes se conectam a aplicativos cliente poderão apresentar falhas ao autenticar a menos que o navegador tenha sido explicitamente configurado para solicitar aos usuários suas credenciais em uma determinada Zona de Segurança do navegador. Como exemplo, pense em um quiosque. A conta que está conectada no sistema operacional pode ser diferente da conta que o usuário fez logon no cliente Skype for Business. Se for esse o caso, talvez você veja as falhas descritas aqui.
    
You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet). Nessa caixa de diálogo, clique no botão Nível Personalizado e percorrer até o final da lista na caixa de diálogo Configurações. Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'. Se você tiver tiver quiosques nos quais o usuário que inicia o cliente Skype for Business seja diferente (possui uma conta diferente) do usuário conectado no computador, você poderá testar configurar essa opção como 'ATIVA' para essas máquinas em uma Política de Grupo.
    
Finalmente, e o mais importante, você pode experimentar mais do que um aviso uma vez que o sistema de segurança coleta as informações necessárias para autenticar ou autorizar sua conta.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Outras opções para habilitar a entrada na ADAL (como aplicativos cliente do Office)
<a name="BKMK_Options"> </a>

Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.
  
> [!IMPORTANT]
> Precisa saber o que esperar de entradas na Autenticação Moderna de seus aplicativos cliente? Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets. In the case of Office 2013 client apps, you will need to change some registry keys on client machines.
  
- Connect to Exchange Online and run the following cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Defina essas chaves do Registro para cada dispositivo ou computador no qual você deseja habilitar a Autenticação Moderna. Você precisará de um GPO em organizações de maior porte. For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.
    
||||
|:-----|:-----|:-----|
|Chave de Registro  <br/> |Tipo  <br/> |Valor  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Once these keys are set, set your Office 2013 apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero. Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes onde a Autenticação Moderna/ADAL não é compatível
<a name="BKMK_Support"> </a>

Algumas versões de cliente não oferecem suporte a OAuth. Você pode verificar se a versão do cliente Office no Painel de Controle no qual você Adiciona e Remove programas para comparar seu número de versão com as versões (ou intervalos de versões) está listada a seguir:
  
- Office Client 15.0.[0000-4766].\*
    
- Office Client 16.0.[0000-4293].\*
    
- Office Client 16.0.6001.[0000-1032]
    
- Office Client 16.0.[6000-6224].\*
    

