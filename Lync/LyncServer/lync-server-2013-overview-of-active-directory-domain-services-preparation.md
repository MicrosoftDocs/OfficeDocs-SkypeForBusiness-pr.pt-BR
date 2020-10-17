---
title: 'Lync Server 2013: visão geral da preparação dos serviços de domínio do Active Directory'
description: 'Lync Server 2013: visão geral da preparação dos serviços de domínio do Active Directory.'
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
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566837"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="7d895-103">Visão geral da preparação dos serviços de domínio do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d895-103">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d895-104">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="7d895-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="7d895-105">Para preparar os serviços de domínio do Active Directory para a implantação do Lync Server 2013, você deve executar três etapas em uma sequência específica.</span><span class="sxs-lookup"><span data-stu-id="7d895-105">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="7d895-106">A tabela a seguir descreve as etapas necessárias para preparar o AD DS para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d895-106">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="7d895-107">Etapas da preparação do Active Directory</span><span class="sxs-lookup"><span data-stu-id="7d895-107">Active Directory Preparation Steps</span></span>

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
<th><span data-ttu-id="7d895-108">Etapa</span><span class="sxs-lookup"><span data-stu-id="7d895-108">Step</span></span></th>
<th><span data-ttu-id="7d895-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d895-109">Description</span></span></th>
<th><span data-ttu-id="7d895-110">Onde executar</span><span class="sxs-lookup"><span data-stu-id="7d895-110">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="7d895-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparando o esquema do Active Directory no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d895-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7d895-112">Estende o esquema do Active Directory adicionando novas classes e atributos que são usados pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d895-112">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="7d895-113">Executar uma vez para cada floresta em sua implantação onde o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="7d895-113">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="7d895-114">No mestre de esquema no domínio raiz de cada floresta onde o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="7d895-114">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7d895-p101">Não é necessário executar essa etapa no domínio raiz se você tiver permissões no esquema mestre, mas é necessário ser membro do grupo Administradores de Esquema no domínio raiz e membro do grupo Administradores de Empresa no esquema mestre. Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, e não nas florestas de usuários. Em uma topologia de floresta central, execute esta etapa somente na floresta central, e não nas florestas de usuários.</span><span class="sxs-lookup"><span data-stu-id="7d895-p101">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master. In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="7d895-118"><a href="lync-server-2013-preparing-the-forest.md">Preparando a floresta para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d895-118"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7d895-119">Cria configurações globais e grupos universais usados pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d895-119">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="7d895-120">Executar uma vez para cada floresta em sua implantação onde o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="7d895-120">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="7d895-121">No domínio raiz de cada floresta onde o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="7d895-121">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="7d895-122">Para executar essa etapa, você precisa ser membro do grupo Administradores de Empresa.</span><span class="sxs-lookup"><span data-stu-id="7d895-122">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7d895-p103">Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, não em florestas de qualquer usuário. Em uma topologia de floresta central, execute esta etapa somente na floresta central, não em florestas de qualquer usuário.</span><span class="sxs-lookup"><span data-stu-id="7d895-p103">In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="7d895-125"><a href="lync-server-2013-preparing-domains.md">Preparando domínios para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d895-125"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7d895-126">Adiciona permissões sobre objetos a serem usados por membros de grupos universais.</span><span class="sxs-lookup"><span data-stu-id="7d895-126">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="7d895-127">Execute uma vez por domínio de usuário ou domínio de servidor.</span><span class="sxs-lookup"><span data-stu-id="7d895-127">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7d895-128">Se você estiver migrando do Lync Server 2010 para o Lync Server 2013, o assistente de implantação poderá indicar que a preparação do domínio já foi concluída.</span><span class="sxs-lookup"><span data-stu-id="7d895-128">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="7d895-129">Não é necessário executar a preparação do domínio novamente.</span><span class="sxs-lookup"><span data-stu-id="7d895-129">You do not need to run domain preparation again.</span></span> <span data-ttu-id="7d895-130">As permissões não foram alteradas do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d895-130">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="7d895-131">Em um servidor membro em cada domínio em que o Lync Server será implantado.</span><span class="sxs-lookup"><span data-stu-id="7d895-131">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="7d895-132">Para executar esta etapa, você deve ser membro do grupo Administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="7d895-132">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="7d895-133">O Lync Server 2013, como o Lync Server 2010, armazena muitas das informações de configuração no repositório de gerenciamento central, em vez de no AD DS, como era o caso no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7d895-133">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="7d895-134">No entanto, as seguintes informações são armazenadas no AD DS:</span><span class="sxs-lookup"><span data-stu-id="7d895-134">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="7d895-135">**Extensões de esquema**:</span><span class="sxs-lookup"><span data-stu-id="7d895-135">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="7d895-136">Extensões do objeto do usuário</span><span class="sxs-lookup"><span data-stu-id="7d895-136">User object extensions</span></span>
    
      - <span data-ttu-id="7d895-137">Extensões para o Office Communications Server 2007 R2 classes para manter a compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="7d895-137">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="7d895-138">**Dados** (armazenados no esquema estendido do Lync Server e nas classes de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="7d895-138">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="7d895-139">URI (Uniform Resource Identifier) SIP do usuário e outras configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="7d895-139">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="7d895-140">Objetos de contato para aplicativos, como Grupo de Respostas e Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="7d895-140">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="7d895-141">Um ponteiro para o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="7d895-141">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="7d895-142">Conta de autenticação Kerberos (um objeto de computador opcional)</span><span class="sxs-lookup"><span data-stu-id="7d895-142">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="7d895-143">No Lync Server 2013, você delega a instalação e administração, concedendo permissões de configuração ao grupo universal RTCUniversalServerAdmins para que os membros desse grupo possam instalar e ativar o Lync Server 2013 em um servidor local (após o servidor ter sido adicionado à topologia, publicado e habilitado).</span><span class="sxs-lookup"><span data-stu-id="7d895-143">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="7d895-144">Os usuários delegados devem ser administradores locais no computador onde estão instalando e ativando o Lync Server 2013, mas não precisam ser membros do grupo de administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="7d895-144">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="7d895-145">Você também pode conceder permissões para objetos em unidades organizacionais (UOs) especificadas, de forma que os membros dos grupos universais criados durante a preparação da floresta possam acessar esses objetos sem ser membros do grupo Administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="7d895-145">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="7d895-146">Para novas implantações do Lync Server 2013, as configurações globais devem ser armazenadas no contêiner de configuração.</span><span class="sxs-lookup"><span data-stu-id="7d895-146">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="7d895-147">Se sua organização estiver atualizando de uma versão anterior e você ainda tiver configurações globais no contêiner do sistema, o contêiner do sistema ainda terá suporte.</span><span class="sxs-lookup"><span data-stu-id="7d895-147">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d895-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="7d895-148">See Also</span></span>


[<span data-ttu-id="7d895-149">Preparando o esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d895-149">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="7d895-150">Extensões, classes e atributos do esquema do Active Directory usados pelo Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d895-150">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="7d895-151">Preparando a floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d895-151">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="7d895-152">Preparando domínios para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d895-152">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

