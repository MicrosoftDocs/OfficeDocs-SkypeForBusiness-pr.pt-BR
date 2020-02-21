---
title: 'Lync Server 2013: Configurando serviços de Federação do Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9daaec9cbe32f031c7ee99731b1d7c7c9ec10ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configurando os serviços de Federação do Active Directory (AD FS 2,0) para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-03_

A seção a seguir descreve como configurar os serviços de Federação do Active Directory (AD FS 2,0) para suportar a autenticação multifator. Para obter informações sobre como instalar o AD FS 2,0, consulte AD FS 2,0 passo-a-passo e como fazer guias [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374)em.

<div class="">


> [!NOTE]  
> Ao instalar o AD FS 2,0, não use o Gerenciador do Windows Server para adicionar a função de serviços de Federação do Active Directory. Em vez disso, baixe e instale o pacote de serviços de Federação do <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory 2,0 RTW em.



</div>

<div>


**Para configurar o AD FS para autenticação de dois fatores**

1.  Faça logon no computador do AD FS 2,0 usando uma conta de administrador de domínio.

2.  Inicie o Windows PowerShell.

3.  Na linha de comando do Windows PowerShell, execute o seguinte comando:
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Estabeleça uma parceria com cada Lync Server 2013 com atualizações cumulativas para Lync Server 2013: diretor de 2013 de julho, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comando, substituindo o nome do servidor específico para sua implantação:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  No menu Ferramentas administrativas, inicie o console de gerenciamento do AD FS 2,0.

6.  Expanda **relações** \> de confiança **confianças**de terceira parte confiável.

7.  Verifique se uma nova relação de confiança foi criada para o Lync Server 2013 com as atualizações cumulativas do Lync Server 2013: julho de 2013 Enterprise pool ou Standard Edition Server.

8.  Crie e atribua uma regra de autorização de emissão para seu confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Crie e atribua uma regra de transformação de emissão para seu confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. No console de gerenciamento do AD FS 2,0, clique com o botão direito do mouse em sua confiança de terceira parte confiável e selecione **Editar regras de declaração**.

11. Selecione a guia **regras de autorização de emissão** e verifique se a nova regra de autorização foi criada com êxito.

12. Selecione a guia **regras de transformação de emissão** e verifique se a nova regra de transformação foi criada com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

