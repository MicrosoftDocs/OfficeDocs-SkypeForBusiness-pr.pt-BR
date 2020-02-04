---
title: 'Lync Server 2013: Visão geral da preparação do Serviços de Domínio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51d0fec8f36749f52acf3272bf83dee3170da8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="46c03-102">Visão geral da preparação do Serviços de Domínio Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c03-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c03-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="46c03-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="46c03-104">Para preparar os serviços de domínio do Active Directory para a implantação do Lync Server 2013, você deve executar três etapas em uma sequência específica.</span><span class="sxs-lookup"><span data-stu-id="46c03-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="46c03-105">A tabela a seguir descreve as etapas necessárias para preparar o AD DS para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46c03-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="46c03-106">Etapas de preparação do Active Directory</span><span class="sxs-lookup"><span data-stu-id="46c03-106">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="46c03-107">Etapa</span><span class="sxs-lookup"><span data-stu-id="46c03-107">Step</span></span></th>
<th><span data-ttu-id="46c03-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="46c03-108">Description</span></span></th>
<th><span data-ttu-id="46c03-109">Onde executar</span><span class="sxs-lookup"><span data-stu-id="46c03-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="46c03-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparando o esquema do Active Directory no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46c03-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="46c03-111">Estende o esquema do Active Directory adicionando novas classes e atributos que são usados pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46c03-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="46c03-112">Executar uma vez para cada floresta na sua implantação em que o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="46c03-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="46c03-113">Em relação ao mestre de esquema no domínio raiz de cada floresta em que o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="46c03-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="46c03-114">Você não precisará executar esta etapa no domínio raiz se tiver permissões no mestre de esquema, mas você deve ser um membro do grupo de administradores de esquemas no domínio raiz e um membro do grupo Administradores de empresa no mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="46c03-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="46c03-115">Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, não em nenhuma floresta de usuário.</span><span class="sxs-lookup"><span data-stu-id="46c03-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="46c03-116">Em uma topologia de floresta central, execute esta etapa somente na floresta central, e não em qualquer floresta de usuário.</span><span class="sxs-lookup"><span data-stu-id="46c03-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="46c03-117"><a href="lync-server-2013-preparing-the-forest.md">Preparando a floresta para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46c03-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="46c03-118">Cria configurações globais e grupos universais usados pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46c03-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="46c03-119">Executar uma vez para cada floresta na sua implantação em que o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="46c03-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="46c03-120">No domínio raiz de cada floresta em que o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="46c03-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="46c03-121">Para executar esta etapa, você deve ser membro do grupo Administradores da empresa.</span><span class="sxs-lookup"><span data-stu-id="46c03-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="46c03-122">Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, não em nenhuma floresta de usuário.</span><span class="sxs-lookup"><span data-stu-id="46c03-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="46c03-123">Em uma topologia de floresta central, execute esta etapa somente na floresta central, e não em qualquer floresta de usuário.</span><span class="sxs-lookup"><span data-stu-id="46c03-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="46c03-124"><a href="lync-server-2013-preparing-domains.md">Preparando domínios para Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46c03-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="46c03-125">Adiciona permissões em objetos a serem usadas por membros de grupos universais.</span><span class="sxs-lookup"><span data-stu-id="46c03-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="46c03-126">Executar uma vez por domínio do usuário ou domínio do servidor.</span><span class="sxs-lookup"><span data-stu-id="46c03-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="46c03-127">Se você estiver migrando do Lync Server 2010 para o Lync Server 2013, o assistente de implantação poderá indicar que a preparação do domínio já está concluída.</span><span class="sxs-lookup"><span data-stu-id="46c03-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="46c03-128">Você não precisa executar a preparação do domínio novamente.</span><span class="sxs-lookup"><span data-stu-id="46c03-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="46c03-129">As permissões não foram alteradas do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46c03-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="46c03-130">Em um servidor membro em cada domínio em que o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="46c03-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="46c03-131">Para executar esta etapa, você deve ser membro do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="46c03-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="46c03-132">O Lync Server 2013, como o Lync Server 2010, armazena muitas das informações de configuração no repositório de gerenciamento central em vez de no AD DS como era o caso no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="46c03-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="46c03-133">No entanto, as seguintes informações são armazenadas no AD DS:</span><span class="sxs-lookup"><span data-stu-id="46c03-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="46c03-134">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="46c03-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="46c03-135">Extensões de objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="46c03-135">User object extensions</span></span>
    
      - <span data-ttu-id="46c03-136">Extensões para as classes do Office Communications Server 2007 R2 para manter a compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="46c03-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="46c03-137">**Dados** (armazenados no esquema estendido do Lync Server e em classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="46c03-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="46c03-138">URI (Uniform Resource Identifier) do usuário SIP e outras configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="46c03-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="46c03-139">Objetos de contato para aplicativos como o assistente de grupo de resposta e conferência</span><span class="sxs-lookup"><span data-stu-id="46c03-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="46c03-140">Um ponteiro para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="46c03-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="46c03-141">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="46c03-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="46c03-142">No Lync Server 2013, você delega a instalação e a administração concedendo permissões de instalação ao grupo universal RTCUniversalServerAdmins para que os membros desse grupo possam instalar e ativar o Lync Server 2013 em um servidor local (após a adição do servidor ao topologia, publicada e habilitada).</span><span class="sxs-lookup"><span data-stu-id="46c03-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="46c03-143">Os usuários delegados devem ser administradores locais no computador em que estão instalando e ativando o Lync Server 2013, mas não precisam ser membros do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="46c03-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="46c03-144">Você também pode conceder permissões para objetos em unidades organizacionais (UOs) especificadas para que os membros dos grupos universais criados durante a preparação da floresta possam acessar esses objetos sem serem membros do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="46c03-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="46c03-145">Para novas implantações do Lync Server 2013, as configurações globais devem ser armazenadas no contêiner de configuração.</span><span class="sxs-lookup"><span data-stu-id="46c03-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="46c03-146">Se a sua organização estiver atualizando de uma versão anterior e ainda houver configurações globais no contêiner do sistema, o contêiner do sistema ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="46c03-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46c03-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="46c03-147">See Also</span></span>


[<span data-ttu-id="46c03-148">Preparando o esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c03-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="46c03-149">Extensões, classes e atributos do esquema do Active Directory usado pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c03-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="46c03-150">Preparando a floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c03-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="46c03-151">Preparando domínios para Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c03-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

