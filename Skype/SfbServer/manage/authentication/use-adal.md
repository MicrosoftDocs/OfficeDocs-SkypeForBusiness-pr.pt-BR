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
description: Este artigo explica como usar a autenticação moderno (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e OAuth 2.0) que podem ser encontradas no de 2016 março atualização cumulativa do Skype for Business para Skype para Business Server 2015.
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Como usar a Autenticação do modem (ADAL) com o Skype for Business
 
Este artigo explica como usar a autenticação moderno (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e OAuth 2.0) que podem ser encontradas no de 2016 março atualização cumulativa do Skype for Business para Skype para Business Server 2015.
  
## <a name="whats-in-this-article"></a>O que há neste artigo?

[O que é ADAL?](use-adal.md#BKMK_ADAL)
  
[Configurar ADAL em seu pool e definir o ADFS como servidor de token de segurança](use-adal.md#BKMK_Config)
  
[Outras opções para habilitar a entrada na ADAL (como aplicativos cliente do Office)](use-adal.md#BKMK_Options)
  
[Clientes onde a Autenticação Moderna/ADAL não é compatível](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>O que é ADAL?
<a name="BKMK_ADAL"> </a>

ADAL é o acrônimo de “Biblioteca de Autenticação do Active Directory" e, junto com o OAuth 2.0, constitui a base da Autenticação Moderna. Esta biblioteca de código foi projetada para disponibilizar recursos protegidos em seu diretório para aplicativos de cliente (como Skype para negócios) por meio de tokens de segurança. A ADAL interage com o OAuth 2.0 para habilitar mais cenários de autenticação e autorização, como MFA (Multi-factor Authentication), bem como mais formas de Autenticação de SAML.
  
Vários aplicativos que atuam como clientes podem aproveitar a Autenticação Moderna para obter recursos seguros. No Skype para Business Server 2015, essa tecnologia é usada entre clientes locais e servidores locais para fornecer aos usuários um nível adequado de autorização para recursos.
  
As conversas de Autenticação Moderna (que se baseiam em ADAL e OAuth 2.0) têm alguns elementos em comum.
  
- Não há um cliente fazendo uma solicitação para um recurso, nesse caso, o cliente for Skype para negócios.
    
- Não há um recurso no qual o cliente precisa de um nível específico de acesso, e esse recurso esteja protegido por um serviço de diretório, nesse caso, o recurso é Skype para Business Server 2015.
    
- Não há uma conexão de OAuth, em outras palavras, uma conexão que é dedicada a *autorização de* um usuário para acessar um recurso. (OAuth também é conhecido pelo nome mais descritivo, autenticação "Servidor a Servidor' e é frequentemente abreviado como S2S.)
    
Skype para conversas Business Server 2015 moderno autenticação (ADAL), Skype para Business Server 2015 comunica-se por meio do ADFS (ADFS 3.0 no Windows Server 2012 R2). A autenticação pode ser feita usando algum outro IdP (Provedor de Identidade), mas o servidor do Skype for Business precisa ser configurado para se comunicar com o ADFS diretamente. Se você ainda não tiver configurado o ADFS para trabalhar com Skype para Business Server 2015 complete a [instalação do ADFS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL está incluído no de 2016 março atualização cumulativa do Skype para Business Server 2015 e o de 2016 março atualização cumulativa do Skype para negócios **deve** ser instalada e é necessária para que a configuração bem-sucedida.
  
> [!NOTE]
> Durante a versão inicial, a autenticação moderna em um ambiente local é suportada apenas se não houver nenhuma topologia mista do Skype envolvidos. Por exemplo, se o ambiente é puramente Skype para Business Server 2015. Esta declaração pode ser está sujeita a alterações. 
  
Um pacote do PowerShell incluindo arquivos .ps1 com os comandos usados por ADAL deve ser baixado para a configuração com êxito.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Configurar ADAL em seu pool e definir o ADFS como servidor de token de segurança
<a name="BKMK_Config"> </a>

Nesse processo, você pode conectar sua instalação do ADFS para um Skype para Business Server 2015 pool que está configurado para ADAL.
  
1. Instalar o de 2016 março atualização cumulativa do Skype para negócios 2015 de servidor para seu Skype para Business Server 2015 pool ou servidor Standard Edition. (Agende as janelas de manutenção, conforme necessário, para executar o Windows Update para a instalação automática.)
    
2. Em seu local ADFS servidor (es), [Baixe](https://aka.ms/sfbadalscripts) o programa de instalação-AdfsOAuthTrustForSfB script. Isso precisa ser feito por farm de ADFS ou por servidores ADFS independentes. Não precisa ser feito nos proxies ADFS.
    
3. Anote o interno e o serviço Web externo totalmente qualificados (FQDNs) nomes de domínio para seu Skype para Business Server 2015 pool ou servidor Standard Edition. Isso precisa ser feito para todos os Pools do Skype for Business.
    
4. Do PowerShell nos Servidores ADFS(s), execute o Setup-AdfsOAuthTrustForSfB. Será necessário inserir as devidas URLs dos FQDNs dos Serviços Web internos e externos. Veja um exemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Para qualquer pools adicionais, você precisará adicionar URLs de serviços Web do Pool manualmente para o Skype para Business Server 2015 confiança da terceira parte no ADFS.
    
    > [!IMPORTANT]
    > Não é possível usar a Autenticação Passiva para um Pool e usar também a ADAL. Você deve desabilitar a Autenticação Passiva para poder usar a ADAL. Para cmdlets do PowerShell sobre como configurar a autenticação de um Pool, consulte [Este](https://technet.microsoft.com/en-us/library/gg398396.aspx) artigo.
  
    > [!TIP]
    > Se você tiver pools adicionais você precisa adicioná-los como [identificadores](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) para a confiança da terceira parte in ADFS. > Ir para seu servidor ADFS e abra o gerenciamento do ADFS. Expanda relações de confiança \> objetos de confiança de terceiros. Clique com o botão a confiança da terceira parte que está listada e o botão direito do mouse para propriedades \> identificadores \> digite as URLs de Pool adicionais \> clique em Adicionar. 
  
5. Retorne à sua Skype para negócios 2015 Front-End Server ou servidor Standard Edition server. A partir daqui, você deve executar cmdlets que crie um servidor OAuth e modificar essa configuração OAuth para trabalhar com Skype para negócios. Você precisará executar esta etapa uma vez por Skype para implantação Business Server 2015. Veja um exemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > A URL de 'Identidade' você vê neste comando é realmente o ADFS federação nome serviço você pode ver no gerenciamento do ADFS, quando você do mouse em serviço \> propriedades. O tipo é sempre ADFS e 'MetadataURL' é sempre \<nome do serviço ADFS Your\> + "/ FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Ainda na sua Skype para negócios 2015 Front-End Server ou servidor Standard Edition, teste a nova configuração inserindo o endereço SIP do usuário e o FQDN do pool. Você precisará executar esta etapa uma vez por Skype para implantação Business Server 2015. Veja um exemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Quando solicitado, certifique-se de inserir as credenciais do usuário de teste. Verifique se o teste é concluído com sucesso.
    
    > [!NOTE]
    > Quando sua URL STS é resolvida para o ADFS *internamente* , o prompt que você verá será um aviso de **Segurança do Windows** . Se a URL for resolvida externamente, você verá um prompt denominado **Entrar**. Normalmente, desejamos um prompt de **Segurança do Windows** aqui. Observe que esse comportamento varia, particularmente se você implementou A Autenticação Baseada em Formulários (ou FBA).
  
Saiba ainda que, quando a URL STS for resolvida para um servidor ADFS interno e a autenticação do Windows Integrada estiver habilitada nos navegadores, os computadores nos quais vários usuários diferentes se conectam a aplicativos cliente poderão apresentar falhas ao autenticar a menos que o navegador tenha sido explicitamente configurado para solicitar aos usuários suas credenciais em uma determinada Zona de Segurança do navegador. Como exemplo, pense em um quiosque. A conta que está conectada no sistema operacional pode ser diferente da conta que o usuário fez logon no cliente Skype for Business. Se for esse o caso, talvez você veja as falhas descritas aqui.
    
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
    
||||
|:-----|:-----|:-----|
|Chave de Registro  <br/> |Tipo  <br/> |Valor  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Depois que essas chaves estiverem definidas, defina seus aplicativos do Office 2013 para [usar a autenticação (MFA Multifactor) com o Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Para desabilitar autenticação moderno em dispositivos do Office 2013, defina a chave de registro HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL como um valor igual a zero. Lembre-se de que uma chave de registro semelhante (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) também pode ser usada para desativar a autenticação moderno em dispositivos para 2016 do Office.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes onde a Autenticação Moderna/ADAL não é compatível
<a name="BKMK_Support"> </a>

Algumas versões de cliente não oferecem suporte a OAuth. Você pode verificar se a versão do cliente Office no Painel de Controle no qual você Adiciona e Remove programas para comparar seu número de versão com as versões (ou intervalos de versões) está listada a seguir:
  
- Cliente do Office 15.0. [0000-4766].\*
    
- Cliente do Office 16.0. [0000-4293].\*
    
- Office Client 16.0.6001.[0000-1032]
    
- Cliente do Office 16.0. [6000-6224].\*
    

