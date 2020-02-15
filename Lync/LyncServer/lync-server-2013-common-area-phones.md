---
title: 'Lync Server 2013: telefones de área comum'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736aa12c9de027aa485cfc89a6f5cd820a460833
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="1b8c4-102">Telefones de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b8c4-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b8c4-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1b8c4-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1b8c4-104">Telefones de área comum são telefones IP que não estão associados a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="1b8c4-105">Em vez de estar localizado no escritório de alguém, os telefones de área comum geralmente estão localizados na criação de lobbies, lanchonetes, descansos de funcionários, salas de reunião e outros locais onde um grande número de pessoas provavelmente será coletado.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="1b8c4-106">Diferentemente de outros telefones no Lync Server, que normalmente são mantidos usando políticas de voz e planos de discagem atribuídos a usuários individuais, os telefones de área comum não têm usuários individuais atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="1b8c4-107">Isso significa que eles devem ser gerenciados de forma diferente dos outros telefones.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="1b8c4-108">Para gerenciar telefones de área comum, você cria objetos de contato dos serviços de domínio do Active Directory para todos os telefones de área comum que, como contas de usuário, podem ser atribuídos a políticas e planos de voz.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="1b8c4-109">Essa abordagem permite que você mantenha o controle sobre telefones de área comum, mesmo que esses telefones não estejam associados a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="1b8c4-110">Use os tópicos desta seção para saber como criar objetos de contato para telefones de área comum, modificá-los e excluí-los e configurar e exibir informações de configuração sobre os telefones de área comum em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b8c4-111">Você tem três opções para telefones de área comum: o telefone de área comum do Aastra 6721ip, o telefone IP HP 4110 e o telefone de área comum IP do Polycom CX500.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="1b8c4-112">O telefone de conferência IP do Polycom CX3000 é outro telefone de área comum variante.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="1b8c4-113">No entanto, ele deve ser usado em salas de conferência.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="1b8c4-114">Para obter detalhes sobre telefones de área comum, consulte a seção telefones de área comum de <A href="http://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">escolher novos dispositivos</A>.</span><span class="sxs-lookup"><span data-stu-id="1b8c4-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1b8c4-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1b8c4-115">In This Section</span></span>

  - [<span data-ttu-id="1b8c4-116">Exibir informações de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b8c4-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="1b8c4-117">Criar ou modificar um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b8c4-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="1b8c4-118">Habilitar ou desabilitar o hot desk no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b8c4-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="1b8c4-119">Excluir um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b8c4-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="1b8c4-120">Atribuir políticas no Lync Server 2013 a um telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="1b8c4-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

