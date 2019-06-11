---
title: 'Lync Server 2013: Configurando os serviços de Federação do Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configurar os serviços de Federação do Active Directory (AD FS 2,0) para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-03_

A seção a seguir descreve como configurar o Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifator. Para obter informações sobre como instalar o AD FS 2,0, consulte guias do AD FS 2,0 passo a passo e como fazer guias [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)em.

<div class="">


> [!NOTE]  
> Ao instalar o AD FS 2.0, não use o Windows Server Manager para adicionar a função do Active Directory Federation. Em vez disso, baixe e instale o pacote de serviços de Federação do <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory 2,0 RTW em.



</div>

<div>


**Para configurar o AD FS para autenticação de dois fatores**

1.  Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.

2.  Inicie o Windows PowerShell.

3.  Na linha de comando do Windows PowerShell, execute o seguinte comando:
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Estabeleça uma parceria com cada Lync Server 2013 com atualizações cumulativas para o Lync Server 2013: Director de julho de 2013, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o comando a seguir, substituindo o nome do servidor específico da sua implantação:
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  No menu Ferramentas Administrativas, inicie o Console de Gerenciamento do AD FS 2.0.

6.  Expanda **relações** \> de confiança **confiança de terceira parte confiável**.

7.  Verifique se uma nova confiança foi criada para o Lync Server 2013 com atualizações cumulativas para o Lync Server 2013: julho de 2013 Enterprise pool ou Standard Edition Server.

8.  Crie e atribua uma Regra de Autorização de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Crie e atribua uma Regra de Transformação de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. No Console de Gerenciamento do AD FS 2.0, clique com o botão direito no seu objeto de confiança de terceira parte confiável e selecione **Editar Regras de Declaração**.

11. Selecione a guia **Regras de Autorização de Emissão** e verifique se a nova regra de autorização foi criada com sucesso.

12. Selecione a guia **Regras de Transformação de Emissão** e verifique se a nova regra de transformação foi criada com sucesso.

</div>

</div>

<span> </span>

</div>

</div>

</div>

