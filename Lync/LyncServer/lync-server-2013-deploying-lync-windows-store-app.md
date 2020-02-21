---
title: 'Lync Server 2013: Implantando o aplicativo Lync da Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de478ddf104f36fc208f2773c26c772b2cc0addd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Implantando o aplicativo Lync da Windows Store no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-03_

Antes de tornar o aplicativo Lync da Windows Store disponível para os usuários, certifique-se de que sua implantação atenda aos [requisitos de aplicativo do Lync Windows Store para Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Para obter detalhes sobre como configurar o Lync Server 2013 para oferecer suporte ao aplicativo Lync da Windows Store, consulte o artigo de blog NextHop, "descoberta automática do Lync Server e [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966)o aplicativo Lync da Windows Store" em. Após a configuração correta do ambiente de servidor, você pode direcionar os usuários para baixar o aplicativo Lync da Windows Store pesquisando por "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Habilitando a autenticação multifator para o aplicativo Lync da Windows Store

Atualizações cumulativas do Lync Server 2013: junho de 2013 adiciona suporte para a autenticação multifator para clientes de aplicativos Lync Windows Store. Além de nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários externos quando eles entrarem em reuniões do Lync. Para habilitar a autenticação multifator, implante o servidor de Federação do AD FS (serviço de Federação do Active Directory) e habilite a autenticação passiva no Lync Server 2013. Após a configuração do AD FS, os usuários externos que tentarem ingressar em reuniões do Lync serão apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e o desafio de senha, juntamente com quaisquer métodos de autenticação adicionais que você tenha configurado .

<div class=" ">


> [!IMPORTANT]  
> As considerações a seguir são importantes se você planeja configurar o AD FS para a autenticação multifator para o aplicativo Lync da Windows Store: 
> <UL>
> <LI>
> <P>Lync Server 2013 com atualizações cumulativas para Lync Server 2013: o 2013 de junho é necessário no mínimo. Os clientes do Lync 2013 desktop não exigem atualizações cumulativas do Lync Server 2013:2013 de junho, portanto, pode parecer que a autenticação passiva está funcionando porque os clientes do Lync 2013 podem autenticar. No entanto, o processo de autenticação para os clientes do aplicativo Lync da Windows Store não será concluído e nenhuma notificação ou mensagem de erro será exibida.</P>
> <LI>
> <P>O servidor deve ser configurado para que a autenticação passiva seja o único tipo de autenticação oferecido.</P>
> <LI>
> <P>Se você usar balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as solicitações do cliente de aplicativo do Lync Windows Store sejam tratadas pelo mesmo servidor de front-end.</P>
> <LI>
> <P>Ao estabelecer uma confiança de terceira parte confiável entre os servidores do Lync Server e do AD FS, atribua uma vida útil de token que seja longa o suficiente para abranger o tamanho máximo de suas reuniões do Lync. Normalmente, uma vida de token de 240 minutos é suficiente.</P></LI></UL>



</div>

**Configurar a autenticação multifator**

1.  Instale uma função de servidor de federação do AD FS. Para obter detalhes, consulte o guia de implantação do serviços de Federação <https://go.microsoft.com/fwlink/p/?linkid=267511>do Active Directory 2,0 em.

2.  Criar certificados para o AD FS. Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o logon único [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)em.

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
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Problemas conhecidos que podem impedir a entrada

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>A hora e a data não estão definidas com precisão no dispositivo que está executando o aplicativo Lync da Windows Store

A configuração de hora do dispositivo deve ser sincronizada com a configuração de hora no servidor. Isso é particularmente importante para dispositivos como Microsoft Surface e outros dispositivos que executam o Windows RT que não fazem parte de um domínio. Para definir a hora desses dispositivos automaticamente a partir de um servidor de horário, execute o seguinte comando em um prompt de comando com privilégios elevados no dispositivo:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Aplicativo Lync da Windows Store não pode acessar o Lync Server ou serviços

O aplicativo Lync da Windows Store pode não conseguir acessar o Lync Server ou os serviços por meio de adaptadores de rede, como modems USB 4G LTE, que não são registrados com o Windows 8 como dispositivos físicos. O aplicativo Lync da Windows Store pode ter esse problema, mesmo quando os aplicativos e navegadores de desktop podem acessar outros servidores e sites.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Aplicativo Lync da Windows Store não é possível entrar com o Lync Server 2010 e o servidor de borda do Office Communications Server 2007 R2

Se sua topologia consistir no Lync Server 2010 com o servidor de borda do Office Communications Server 2007 R2, será necessário executar a versão atualizada do construtor de topologias disponível na atualização cumulativa do Lync Server 2010: julho de 2013. Versões anteriores do construtor de topologias não criam o mapeamento necessário para o servidor de borda do Office Communications Server 2007, portanto, os clientes do aplicativo do Lync Windows Store não conseguem entrar. As etapas a seguir são necessárias:

1.  Instalar a atualização cumulativa do Lync Server 2010:2013 de julho no Lync Server 2010 pools e nos diretores do Lync Server 2010.

2.  Atualize a configuração de descoberta automática do Lync para indicar que o ponto de entrada SIP externo é o endereço do servidor de borda, fazendo o seguinte:
    
    1.  Abra o Shell de gerenciamento do Lync Server.
    
    2.  Execute o seguinte comando:
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>Aplicativo Lync da Windows Store não é possível entrar devido a uma falha de validação de nome de certificado

Pode ocorrer um problema de entrada para os usuários do Office 365 que não estão executando a versão mais recente do aplicativo Lync da Windows Store. Esse problema geralmente ocorre ao usar vários domínios (por exemplo, quando o URI do SIP é **UserA@domainZ.com** , mas o servidor de borda é **SIP.domainX.com**). Para corrigir o problema, os usuários devem instalar a versão mais recente do aplicativo Lync da Windows Store, que também requer o Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Usar logs de aplicativos do Lync Windows Store para solucionar problemas

Você pode usar os logs gerados no dispositivo para solucionar problemas. Os logs são armazenados na seguinte pasta:

% LocalAppData%\\pacotes\\Microsoft. LyncMX\_8wekyb3d8bbwe\\localstate\\de rastreamento

Antes de obter os logs de um usuário, verifique se o registro em log está ativado e peça ao usuário para salvar os logs de modo que todas as informações armazenadas na memória também sejam salvas em arquivos no disco rígido.

**Para ativar o registro em log**

1.  Abra o aplicativo Lync da Windows Store no dispositivo.

2.  Passe o dedo a partir do lado direito da tela. Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.

3.  Selecione **configurações**, selecione **Opções**e, em seguida, defina **logs de diagnóstico** como **ativado**.

4.  Se **os logs de diagnóstico** estiverem desativados anteriormente, você deverá reiniciar o Lync. Para reiniciar o Lync, siga um destes procedimentos:
    
      - Reinicie o dispositivo.
    
      - Finalize a tarefa do Lync e inicie o aplicativo novamente. Para finalizar a tarefa, abra o Gerenciador de tarefas do Windows, selecione **Lync**e, em seguida, toque em **Finalizar tarefa**. Se o Lync não estiver listado, toque em **mais detalhes** e procure Lync em **processos em segundo plano**.

**Para salvar os logs**

1.  Abra o aplicativo Lync da Windows Store no dispositivo.

2.  Tente entrar.

3.  Passe o dedo a partir do lado direito da tela. Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.

4.  Selecione **configurações**, selecione **sobre**e, em seguida, selecione **salvar logs**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

