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

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="f7a6a-102">Configurar os serviços de Federação do Active Directory (AD FS 2,0) para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7a6a-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a6a-103">_**Tópico da última modificação:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="f7a6a-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="f7a6a-104">A seção a seguir descreve como configurar o Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="f7a6a-105">Para obter informações sobre como instalar o AD FS 2,0, consulte guias do AD FS 2,0 passo a passo e como fazer guias [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)em.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f7a6a-106">Ao instalar o AD FS 2.0, não use o Windows Server Manager para adicionar a função do Active Directory Federation.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="f7a6a-107">Em vez disso, baixe e instale o pacote de serviços de Federação do <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory 2,0 RTW em.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="f7a6a-108">**Para configurar o AD FS para autenticação de dois fatores**</span><span class="sxs-lookup"><span data-stu-id="f7a6a-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="f7a6a-109">Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="f7a6a-110">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="f7a6a-111">Na linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f7a6a-111">From the Windows PowerShell command-line, run the following command:</span></span>
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  <span data-ttu-id="f7a6a-112">Estabeleça uma parceria com cada Lync Server 2013 com atualizações cumulativas para o Lync Server 2013: Director de julho de 2013, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o comando a seguir, substituindo o nome do servidor específico da sua implantação:</span><span class="sxs-lookup"><span data-stu-id="f7a6a-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  <span data-ttu-id="f7a6a-113">No menu Ferramentas Administrativas, inicie o Console de Gerenciamento do AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="f7a6a-114">Expanda **relações** \> de confiança **confiança de terceira parte confiável**.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="f7a6a-115">Verifique se uma nova confiança foi criada para o Lync Server 2013 com atualizações cumulativas para o Lync Server 2013: julho de 2013 Enterprise pool ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="f7a6a-116">Crie e atribua uma Regra de Autorização de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="f7a6a-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="f7a6a-117">Crie e atribua uma Regra de Transformação de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="f7a6a-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="f7a6a-118">No Console de Gerenciamento do AD FS 2.0, clique com o botão direito no seu objeto de confiança de terceira parte confiável e selecione **Editar Regras de Declaração**.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="f7a6a-119">Selecione a guia **Regras de Autorização de Emissão** e verifique se a nova regra de autorização foi criada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="f7a6a-120">Selecione a guia **Regras de Transformação de Emissão** e verifique se a nova regra de transformação foi criada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="f7a6a-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

