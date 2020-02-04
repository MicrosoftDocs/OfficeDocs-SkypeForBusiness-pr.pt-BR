---
title: 'Lync Server 2013: Preparando domínios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a6897ae45964f3f179e951916dfb6bf7180641
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="c9ea4-102">Preparando domínios para Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ea4-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ea4-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c9ea4-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c9ea4-104">Preparação do domínio é a etapa final na preparação dos serviços de domínio Active Directory para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="c9ea4-105">A etapa de preparação do domínio adiciona entradas de controle de acesso (ACEs) necessárias aos grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="c9ea4-106">A preparação do domínio cria ACEs no domínio raiz e três contêiners integrados: Usuário, Computadores e Controladores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="c9ea4-107">Você pode executar a preparação do domínio em qualquer computador do domínio no qual você está implantando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="c9ea4-108">Você deve preparar cada domínio que hospedará o Lync Server ou os usuários.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="c9ea4-109">Se a herança de permissões estiver desabilitada ou as permissões de usuário autenticadas estiverem desabilitadas em sua organização, você deverá executar etapas adicionais durante a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="c9ea4-110">Para obter detalhes, consulte [preparando um serviço de domínio do Active Directory bloqueado no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9ea4-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="c9ea4-111">Se sua organização usa unidades organizacionais (OU) em vez de três recipientes internos (ou seja, usuários, computadores e controladores de domínio), você deve conceder acesso de leitura às UOs do grupo usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="c9ea4-112">O acesso de leitura aos recipientes é necessário para a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="c9ea4-113">Se o grupo usuários autenticados não tiver acesso de leitura à OU, execute o cmdlet **Grant-CsOuPermission** conforme ilustrado nos exemplos de código a seguir para conceder permissões de leitura para cada UO.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="c9ea4-114">Para obter detalhes sobre o cmdlet **Grant-CsOuPermission** , consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="c9ea4-115">Para obter detalhes sobre os ases criados na raiz do domínio e nos contêineres usuários, computadores e controladores de domínio, consulte <A href="lync-server-2013-changes-made-by-domain-preparation.md">alterações feitas pela preparação do domínio no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c9ea4-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9ea4-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c9ea4-116">In This Section</span></span>

  - [<span data-ttu-id="c9ea4-117">Executando preparação de domínio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ea4-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="c9ea4-118">Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ea4-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

