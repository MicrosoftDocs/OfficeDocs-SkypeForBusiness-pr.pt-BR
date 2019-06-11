---
title: 'Lync Server 2013: Preparando a floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="7ede5-102">Preparando a floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ede5-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ede5-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7ede5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7ede5-104">A preparação da floresta cria configurações e objetos globais do Active Directory e grupos universais do Active Directory para uso pelo Lync Server 2013 e concede permissões de acesso adequadas nos objetos do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ede5-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="7ede5-105">Para obter uma descrição dos grupos universais e das configurações globais e dos objetos criados pela preparação da floresta, consulte [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span><span class="sxs-lookup"><span data-stu-id="7ede5-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="7ede5-106">A preparação da floresta também cria objetos que contêm conjuntos de propriedades e especificadores de exibição que são usados pelo Lync Server 2013 e os armazena no contêiner de configuração.</span><span class="sxs-lookup"><span data-stu-id="7ede5-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7ede5-107">Verifique se as alterações de preparação do esquema foram duplicadas para todos os controladores de domínio antes de executar o procedimento de preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="7ede5-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="7ede5-108">Se a duplicação não for completada, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="7ede5-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="7ede5-109">Se você estiver executando uma nova implantação do Lync Server, deverá armazenar as configurações globais no contêiner de configuração.</span><span class="sxs-lookup"><span data-stu-id="7ede5-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="7ede5-110">Se você estiver atualizando de uma versão anterior e ainda armazenar configurações globais no contêiner do sistema, poderá continuar a usar o contêiner do sistema.</span><span class="sxs-lookup"><span data-stu-id="7ede5-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="7ede5-111">Você deve ser membro do grupo Administradores da empresa ou administradores de domínio do domínio raiz da floresta para executar esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="7ede5-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ede5-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7ede5-112">In This Section</span></span>

  - [<span data-ttu-id="7ede5-113">Executando preparação de floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ede5-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="7ede5-114">Usando cmdlets para reverter preparação da floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ede5-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

