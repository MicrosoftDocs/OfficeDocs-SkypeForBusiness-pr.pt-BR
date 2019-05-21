---
title: Como usar a Autenticação do modem (ADAL) com o Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: Este artigo explica como usar a autenticação moderna (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e no OAuth 2,0) que pode ser encontrada na atualização cumulativa 2016 de março para o Skype for Business para Skype for Business Server 2015.
ms.openlocfilehash: 9fe4470e1f8f6e2cd345cd176250fb1ffb16448f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286120"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>How to use Modern Authentication (ADAL) with Skype for Business
 
Este artigo explica como usar a autenticação moderna (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e no OAuth 2,0) que pode ser encontrada na atualização cumulativa 2016 de março para o Skype for Business para Skype for Business Server 2015 ou a partir da inicial lançamento do Skype for Business Server 2019.
  
## <a name="whats-in-this-article"></a>O que há neste artigo?

[Configurar o ADAL em seu pool e configurar o AD FS como servidor de token de segurança](use-adal.md#BKMK_Config)
  
[Outras opções para habilitar a entrada na ADAL (como aplicativos cliente do Office)](use-adal.md#BKMK_Options)
  
[Clientes onde a Autenticação Moderna/ADAL não é compatível](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>Configurar o ADAL em seu pool e configurar o AD FS como servidor de token de segurança
<a name="BKMK_Config"> </a>

Nesse processo, você conecta a instalação do AD FS a um pool de servidores do Skype for Business que está configurado para o ADAL.
  
1. Instale a atualização cumulativa de março de 2016 (ou mais recente) do Skype for Business Server 2015 em seu servidor do Skype for Business Server ou Standard Edition. (Agende as janelas de manutenção, conforme necessário, para executar o Windows Update para a instalação automática.)
    
2. Em seu (s) servidor (es) do AD FS local, [Baixe](https://aka.ms/sfbadalscripts) o script setup-AdfsOAuthTrustForSfB. (Isso precisa ser feito por farm do AD FS ou servidor (es) independente do AD FS. Ele não precisa ser feito em proxies do aplicativo Web ou proxies do aplicativo Web.)
    
3. Anote os nomes de domínio totalmente qualificados dos serviços Web internos e externos para o pool do Skype for Business Server ou o servidor Standard Edition. Isso precisa ser feito para todos os Pools do Skype for Business.
    
4. Do PowerShell no (s) servidor (es) do AD `Setup-AdfsOAuthTrustForSfB.ps1` FS, executar (para windows Server 2012 `Setup-Adfs2016OAuthTrustForSfB.ps1` R2) ou (para Windows Server 2016 ou posterior). Você precisará inserir as URLs adequadas para os nomes de domínio totalmente qualificados dos serviços Web internos e externos (FQDNs). Veja um exemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Para outros pools adicionais, você precisará adicionar o pool de URLs de serviços Web manualmente para a confiança de terceira parte confiável do Skype for Business Server no AD FS.
    
    > [!IMPORTANT]
    > Não é possível usar a Autenticação Passiva para um Pool e usar também a ADAL. Você deve desabilitar a Autenticação Passiva para poder usar a ADAL. Para cmdlets do PowerShell sobre como definir a autenticação para um pool, consulte [este](https://technet.microsoft.com/en-us/library/gg398396.aspx) artigo.
  
    > [!TIP]
    > Se você tiver pools adicionais, precisará adicioná- [](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) los como identificadores à confiança da terceira parte confiável no AD FS. _GT_ acesse seu servidor do AD FS e abra o gerenciamento do AD FS. Expanda relações \> de confiança confiança de terceira parte confiável. Clique com o botão direito do mouse na terceira parte confiável listada e clique com o \> botão direito \> do mouse para obter os identificadores de \> Propriedades, digite as URLs de pool adicionais e clique em Adicionar. 
  
5. Retorne ao servidor de front-end do Skype for Business Server ou do servidor Standard Edition. Aqui, você deve executar cmdlets que criam um servidor OAuth e modificar a configuração do OAuth para funcionar com o Skype for Business. Você só precisa fazer esta etapa uma vez por implantação do Skype for Business Server. Veja um exemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > Na verdade, a URL ' identidade ' que você vê nesse comando é o nome do serviço de Federação do AD FS que você pode ver no gerenciamento do AD \> FS ao clicar com o botão direito do mouse em Propriedades do serviço. O ' tipo ' é sempre ' ADFS ' e o ' MetadataURL ' sempre \<é o nome\> do seu serviço AD FS + "/FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Ainda em seu servidor front-end ou Standard Edition do Skype for Business Server, teste a nova configuração inserindo o endereço SIP de um usuário e o FQDN do pool. Você só precisa fazer esta etapa uma vez por implantação do Skype for Business Server. Veja um exemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Quando solicitado, certifique-se de inserir as credenciais do usuário de teste. Verifique se o teste é concluído com sucesso.
    
    > [!NOTE]
    > Quando a URL do STS é resolvida *internamente* , o prompt será exibido será um prompt de segurança do **Windows** . Se a URL for resolvida externamente, você verá um prompt denominado **Entrar**. Normalmente, desejamos um prompt de **Segurança do Windows** aqui. Observe que esse comportamento varia, particularmente se você implementou A Autenticação Baseada em Formulários (ou FBA).
  
Além disso, lembre-se de que, quando a URL do STS é resolvida para um servidor interno do AD FS e a autenticação integrada do Windows está habilitada nos navegadores, os computadores em que muitos usuários diferentes entram em aplicativos cliente podem ter falhas para autenticar, a menos que o navegador seja explicitamente configurado para solicitar aos usuários as credenciais de uma determinada zona de segurança do navegador. Como exemplo, pense em um quiosque. A conta que está conectada no sistema operacional pode ser diferente da conta que o usuário fez logon no cliente Skype for Business. Se for esse o caso, talvez você veja as falhas descritas aqui.
    
Você pode ver e alterar essa configuração do navegador no Internet Explorer clicando \> em ferramentas (ou na guia \> \> de segurança \> opções da Internet de engrenagem) e na zona de segurança (como intranet local). Nessa caixa de diálogo, clique no botão Nível Personalizado e percorrer até o final da lista na caixa de diálogo Configurações. Em login \> de \> autenticação do usuário, você verá uma opção para "solicitar o nome de usuário e senha". Se você tiver tiver quiosques nos quais o usuário que inicia o cliente Skype for Business seja diferente (possui uma conta diferente) do usuário conectado no computador, você poderá testar configurar essa opção como 'ATIVA' para essas máquinas em uma Política de Grupo.
    
Finalmente, e o mais importante, você pode experimentar mais do que um aviso uma vez que o sistema de segurança coleta as informações necessárias para autenticar ou autorizar sua conta.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Outras opções para habilitar a entrada na ADAL (como aplicativos cliente do Office)
<a name="BKMK_Options"> </a>

Agora que o ADAL está configurado para seu Skype for Business e (automaticamente) para aplicativos cliente do Office 2016 entre plataformas, você pode querer aproveitá-lo para o Exchange Online (onde ele não está ativado "por padrão) ou nos clientes do Office 2013.
  
> [!IMPORTANT]
> Precisa saber o que esperar de entradas na Autenticação Moderna de seus aplicativos cliente? Dê uma olhada em [como a autenticação moderna funciona para os aplicativos cliente do office 2013 e do office 2016](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Para ativar a autenticação moderna no Exchange Online, você precisará executar alguns cmdlets do PowerShell. No caso dos aplicativos cliente do Office 2013, você precisará alterar algumas chaves do registro nos computadores cliente.
  
- Conecte-se ao Exchange Online e execute os seguintes cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Defina essas chaves do Registro para cada dispositivo ou computador no qual você deseja habilitar a Autenticação Moderna. Você precisará de um GPO em organizações de maior porte. Para obter informações sobre como criar um GPO, consulte o artigo ' criar um objeto de política de grupo para modificar o registro em um computador associado [ ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)a um domínio ' deste artigo.
    
|Chave de Registro  <br/> |Tipo  <br/> |Valor  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Depois que essas chaves estiverem definidas, configure seus aplicativos do Office para [usar autenticação multifator (MFA) com o Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Para desabilitar a autenticação moderna em dispositivos do Office 2013, defina a chave do registro HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL para um valor igual a zero. Lembre-se de que uma chave do registro semelhante (HKCU\SOFTWARE\Microsoft\Office\ **16,0** \Common\Identity\EnableADAL) também pode ser usada para desabilitar a autenticação moderna em dispositivos do Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes onde a Autenticação Moderna/ADAL não é compatível
<a name="BKMK_Support"> </a>

Algumas versões de cliente não oferecem suporte a OAuth. Você pode verificar se a versão do cliente Office no Painel de Controle no qual você Adiciona e Remove programas para comparar seu número de versão com as versões (ou intervalos de versões) está listada a seguir:
  
- Cliente do Office 15,0. [0000-4766].\*
    
- Cliente do Office 16,0. [0000-4293].\*
    
- Office Client 16.0.6001.[0000-1032]
    
- Cliente do Office 16,0. [6000-6224].\*
    
> [!NOTE]
> A autenticação moderna híbrida também está disponível com o Skype for Business local, se você quiser saber mais, acesse [como configurar o Skype for Business no local para usar a autenticação moderna híbrida](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)
