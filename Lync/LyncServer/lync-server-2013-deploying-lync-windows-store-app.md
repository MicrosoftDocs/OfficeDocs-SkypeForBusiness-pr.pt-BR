---
title: 'Lync Server 2013: Implantando o aplicativo Lync da Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b22880b230acda74c7485010550d5576ea200c61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Implantando o aplicativo Lync da Windows Store no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-03_

Antes de disponibilizar o aplicativo Lync da Windows Store para os usuários, certifique-se de que sua implantação atenda aos [requisitos do aplicativo Lync da Windows Store para o Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Para obter detalhes sobre como configurar o Lync Server 2013 para dar suporte ao aplicativo Lync da Windows Store, consulte o artigo "NextHop" do Lync Server e o aplicativo Lync da [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Windows Store "em. Após a configuração correta do ambiente do servidor, você pode direcionar os usuários para baixar o aplicativo Lync da Windows Store ao procurar por "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Habilitando a autenticação multifator para o aplicativo Lync da Windows Store

Atualizações cumulativas do Lync Server 2013:2013 de junho adiciona suporte para a autenticação multifator para os clientes do aplicativo Lync da Windows Store. Além do nome de usuário e da senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários externos quando eles entrarem em reuniões do Lync. Para habilitar a autenticação multifator, implante o serviço de Federação do Active Directory (AD FS) e habilite a autenticação passiva no Lync Server 2013. Após a configuração do AD FS, os usuários externos que tentam ingressar em reuniões do Lync são apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e o desafio da senha, juntamente com qualquer método de autenticação adicional que você tenha configurado .

<div class=" ">


> [!IMPORTANT]  
> Veja a seguir considerações importantes se você planeja configurar o AD FS para autenticação multifator para o aplicativo Lync da Windows Store: 
> <UL>
> <LI>
> <P>Lync Server 2013 com atualizações cumulativas do Lync Server 2013:2013 de junho é necessário no mínimo. Os clientes de desktop do Lync 2013 não exigem atualizações cumulativas do Lync Server 2013:2013 de junho, portanto, pode parecer que a autenticação passiva está funcionando porque os clientes do Lync 2013 são capazes de se autenticar. No entanto, o processo de autenticação para os clientes do aplicativo Lync da Windows Store falhará em concluir, e nenhuma mensagem de erro será exibida.</P>
> <LI>
> <P>O servidor deve ser configurado para que a autenticação passiva seja o único tipo de autenticação oferecido.</P>
> <LI>
> <P>Se você usar balanceadores de carga de hardware, habilite a persistência de cookies nos balanceadores de carga para que todas as solicitações do cliente do aplicativo Lync da Windows Store sejam manipuladas pelo mesmo servidor front-end.</P>
> <LI>
> <P>Quando você estabelece uma relação de confiança entre terceira parte confiável entre os servidores do Lync Server e do AD FS, atribua uma vida de token longa o suficiente para abranger o tamanho máximo de suas reuniões do Lync. Normalmente, uma vida de token de 240 minutos é suficiente.</P></LI></UL>



</div>

**Para configurar a autenticação multifator**

1.  Instale uma função de servidor de federação AD FS. Para obter detalhes, consulte o guia de implantação do serviços de Federação <http://go.microsoft.com/fwlink/p/?linkid=267511>do Active Directory 2,0 em.

2.  Crie certificados para o AD FS. Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o tópico logon [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)único em.

3.  Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Estabeleça uma parceria executando o seguinte comando:
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Defina as seguintes regras de confiabilidade de parte:
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Problemas conhecidos que podem impedir a entrada

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>A hora e a data não estão definidas com precisão no dispositivo que está executando o aplicativo Lync da Windows Store

A configuração de hora no dispositivo deve ser sincronizada com a configuração de hora no servidor. Isso é especialmente importante para dispositivos como Microsoft Surface e outros dispositivos que executam o Windows RT que não fazem parte de um domínio. Para definir o tempo desses dispositivos automaticamente a partir de um servidor de horário, execute o seguinte comando em um prompt de comando elevado no dispositivo:

    w32tm /resync

</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>O aplicativo Lync da Windows Store não pode acessar o servidor ou serviços do Lync

O aplicativo Lync da Windows Store pode não conseguir acessar o servidor ou serviços do Lync por meio de adaptadores de rede, como modems USB 4G LTE, que não se registram no Windows 8 como dispositivos físicos. O aplicativo Lync da Windows Store pode ter esse problema mesmo quando os aplicativos da área de trabalho e navegadores são capazes de acessar outros servidores e sites.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>O aplicativo Lync da Windows Store não pode entrar com o Lync Server 2010 e o Office Communications Server 2007 R2 Edge Server

Se a sua topologia consistir no Lync Server 2010 com o Office Communications Server 2007 R2 Edge Server, será necessário executar a versão atualizada do construtor de topologias disponível na atualização cumulativa do Lync Server 2010: julho de 2013. As versões anteriores do construtor de topologias não criam o mapeamento obrigatório para o servidor de borda do Office Communications Server 2007, portanto, os clientes do aplicativo Lync da Windows Store não conseguem entrar. As seguintes etapas são necessárias:

1.  Instale a atualização cumulativa do Lync Server 2010:2013 de julho no Lync Server 2010 pools e nos directors do Lync Server 2010.

2.  Atualize a configuração de descoberta automática do Lync para indicar que o ponto de entrada SIP externo é o endereço do servidor de borda fazendo o seguinte:
    
    1.  Abra o Shell de Gerenciamento do Lync Server.
    
    2.  Execute o seguinte comando:
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>O aplicativo Lync da Windows Store não pode entrar devido a uma falha na validação do nome do certificado

Pode ocorrer um problema de entrada para os usuários do Office 365 que não estão executando a versão mais recente do aplicativo Lync da Windows Store. Geralmente, esse problema ocorre ao usar vários domínios (por exemplo, quando o URI SIP é **UserA@domainZ.com** , mas o servidor de borda é **SIP.domainX.com**). Para corrigir o problema, os usuários devem instalar a versão mais recente do aplicativo Lync da Windows Store, que também requer o Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Usar os logs do aplicativo Lync da Windows Store para solucionar problemas

Você pode usar os logs gerados no dispositivo para solucionar problemas. Os logs são armazenados na seguinte pasta:

% LocalAppData%\\pacotes\\Microsoft. LyncMX\_8wekyb3d8bbwe\\o\\rastreamento localstate

Antes de obter os logs de um usuário, verifique se o registro em log está ativado e peça para o usuário salvar os logs para que todas as informações armazenadas na memória também sejam salvas em arquivos no disco rígido.

**Para ativar o registro em log**

1.  Abra o aplicativo Lync da Windows Store no dispositivo.

2.  Passe o dedo do lado direito da tela. Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.

3.  Selecione **configurações**, selecione **Opções**e, em seguida, defina **os logs de diagnóstico** como **ativado**.

4.  Se **os logs de diagnóstico** tiverem sido desativados anteriormente, reinicie o Lync. Para reiniciar o Lync, siga um destes procedimentos:
    
      - Reinicie o dispositivo.
    
      - Encerre a tarefa do Lync e inicie o aplicativo novamente. Para finalizar a tarefa, abra o Gerenciador de tarefas do Windows, selecione **Lync**e, em seguida, toque em **Finalizar tarefa**. Se o Lync não estiver listado, toque em **mais detalhes** e procure o Lync em **processos em segundo plano**.

**Para salvar os logs**

1.  Abra o aplicativo Lync da Windows Store no dispositivo.

2.  Tente entrar.

3.  Passe o dedo do lado direito da tela. Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.

4.  Selecione **configurações**, selecionar **sobre**e, em seguida, selecione **salvar logs**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

