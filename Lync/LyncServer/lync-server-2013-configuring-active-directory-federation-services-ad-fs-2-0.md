---
title: 'Lync Server 2013: Configurando serviços de Federação do Active Directory (AD FS 2,0)'
description: 'Lync Server 2013: Configurando os serviços de Federação do Active Directory (AD FS 2,0).'
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
ms.openlocfilehash: bc21500273d8576f54f6110783e61764ec9723a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567837"
---
# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="ba737-103">Configurando os serviços de Federação do Active Directory (AD FS 2,0) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba737-103">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba737-104">_**Última modificação do tópico:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="ba737-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="ba737-105">A seção a seguir descreve como configurar os serviços de Federação do Active Directory (AD FS 2,0) para suportar a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="ba737-105">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="ba737-106">Para obter informações sobre como instalar o AD FS 2,0, consulte AD FS 2,0 passo-a-passo e como fazer guias em [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374) .</span><span class="sxs-lookup"><span data-stu-id="ba737-106">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ba737-107">Ao instalar o AD FS 2,0, não use o Gerenciador do Windows Server para adicionar a função de serviços de Federação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ba737-107">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="ba737-108">Em vez disso, baixe e instale o pacote de serviços de Federação do Active Directory 2,0 RTW em <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A> .</span><span class="sxs-lookup"><span data-stu-id="ba737-108">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="ba737-109">**Para configurar o AD FS para autenticação de dois fatores**</span><span class="sxs-lookup"><span data-stu-id="ba737-109">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="ba737-110">Faça logon no computador do AD FS 2,0 usando uma conta de administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="ba737-110">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="ba737-111">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba737-111">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="ba737-112">Na linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="ba737-112">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="ba737-113">Estabeleça uma parceria com cada Lync Server 2013 com atualizações cumulativas para Lync Server 2013: diretor de 2013 de julho, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comando, substituindo o nome do servidor específico para sua implantação:</span><span class="sxs-lookup"><span data-stu-id="ba737-113">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="ba737-114">No menu Ferramentas administrativas, inicie o console de gerenciamento do AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="ba737-114">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="ba737-115">Expanda **relações de confiança** \> **confianças**de terceira parte confiável.</span><span class="sxs-lookup"><span data-stu-id="ba737-115">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="ba737-116">Verifique se uma nova relação de confiança foi criada para o Lync Server 2013 com as atualizações cumulativas do Lync Server 2013: julho de 2013 Enterprise pool ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="ba737-116">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="ba737-117">Crie e atribua uma regra de autorização de emissão para seu confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="ba737-117">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="ba737-118">Crie e atribua uma regra de transformação de emissão para seu confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="ba737-118">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="ba737-119">No console de gerenciamento do AD FS 2,0, clique com o botão direito do mouse em sua confiança de terceira parte confiável e selecione **Editar regras de declaração**.</span><span class="sxs-lookup"><span data-stu-id="ba737-119">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="ba737-120">Selecione a guia **regras de autorização de emissão** e verifique se a nova regra de autorização foi criada com êxito.</span><span class="sxs-lookup"><span data-stu-id="ba737-120">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="ba737-121">Selecione a guia **regras de transformação de emissão** e verifique se a nova regra de transformação foi criada com êxito.</span><span class="sxs-lookup"><span data-stu-id="ba737-121">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

