---
title: 'Lync Server 2013: preparando domínios'
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
ms.openlocfilehash: a37c365732785198e45a546f2352c51ccb42f9dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506938"
---
# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="64dde-102">Preparando domínios para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64dde-102">Preparing domains for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64dde-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="64dde-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="64dde-104">A preparação do domínio é a etapa final da preparação dos serviços de domínio do Active Directory para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64dde-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="64dde-105">A etapa de preparação do domínio adiciona ACEs (entradas de controle de acesso) a grupos universais que concedem permissões para hospedar e gerenciar usuários dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="64dde-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="64dde-106">A preparação de domínio cria ACEs na raiz do domínio e três contêineres internos: Usuários, Computadores e Controladores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="64dde-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="64dde-107">Você pode executar a preparação do domínio em qualquer computador no domínio em que você está implantando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64dde-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="64dde-108">Você deve preparar todos os domínios que serão hospedados no Lync Server ou usuários.</span><span class="sxs-lookup"><span data-stu-id="64dde-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="64dde-109">Se a herança de permissões estiver desabilitada ou se as permissões de usuário autenticado estiverem desabilitadas em sua organização, você deverá executar etapas adicionais durante a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="64dde-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="64dde-110">Para obter detalhes, consulte [preparação de serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="64dde-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="64dde-111">Se sua organização usa unidades organizacionais (OU) em vez de três contêineres internos (ou seja, usuários, computadores e controladores de domínio), você deve conceder acesso de leitura às UOs para o grupo de usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="64dde-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="64dde-112">O acesso de leitura aos contêineres é necessário para a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="64dde-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="64dde-113">Se o grupo usuários autenticados não tiver acesso de leitura à OU, execute o cmdlet **Grant-CsOuPermission** conforme ilustrado nos exemplos de código a seguir para conceder permissões de leitura para cada ou.</span><span class="sxs-lookup"><span data-stu-id="64dde-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="64dde-114">Para obter detalhes sobre o cmdlet **Grant-CsOuPermission** , consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64dde-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="64dde-115">Para obter detalhes sobre as ACEs criadas na raiz do domínio e nos contêineres usuários, computadores e controladores de domínio, confira <A href="lync-server-2013-changes-made-by-domain-preparation.md">as alterações feitas pela preparação do domínio no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="64dde-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="64dde-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="64dde-116">In This Section</span></span>

  - [<span data-ttu-id="64dde-117">Executando a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64dde-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="64dde-118">Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64dde-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

