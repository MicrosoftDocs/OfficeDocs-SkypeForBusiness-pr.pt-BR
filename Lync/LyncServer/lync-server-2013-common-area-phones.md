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
ms.openlocfilehash: 154d079d3a485297dd17239d77cd8aa5e269f365
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="ba999-102">Telefones de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba999-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba999-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ba999-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ba999-104">Telefones de área comum são telefones IP que não estão associados a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="ba999-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="ba999-105">Em vez de estar localizado no escritório de alguém, os telefones de área comum geralmente estão localizados na criação de lobbies, lanchonetes, descansos de funcionários, salas de reunião e outros locais onde um grande número de pessoas provavelmente será coletado.</span><span class="sxs-lookup"><span data-stu-id="ba999-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="ba999-106">Diferentemente de outros telefones no Lync Server, que normalmente são mantidos usando políticas de voz e planos de discagem atribuídos a usuários individuais, os telefones de área comum não têm usuários individuais atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="ba999-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="ba999-107">Isso significa que eles devem ser gerenciados de forma diferente dos outros telefones.</span><span class="sxs-lookup"><span data-stu-id="ba999-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="ba999-108">Para gerenciar telefones de área comum, você cria objetos de contato dos serviços de domínio do Active Directory para todos os telefones de área comum que, como contas de usuário, podem ser atribuídos a políticas e planos de voz.</span><span class="sxs-lookup"><span data-stu-id="ba999-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="ba999-109">Essa abordagem permite que você mantenha o controle sobre telefones de área comum, mesmo que esses telefones não estejam associados a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="ba999-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="ba999-110">Use os tópicos desta seção para saber como criar objetos de contato para telefones de área comum, modificá-los e excluí-los e configurar e exibir informações de configuração sobre os telefones de área comum em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="ba999-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba999-111">Você tem três opções para telefones de área comum: o telefone de área comum do Aastra 6721ip, o telefone IP HP 4110 e o telefone de área comum IP do Polycom CX500.</span><span class="sxs-lookup"><span data-stu-id="ba999-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="ba999-112">O telefone de conferência IP do Polycom CX3000 é outro telefone de área comum variante.</span><span class="sxs-lookup"><span data-stu-id="ba999-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="ba999-113">No entanto, ele deve ser usado em salas de conferência.</span><span class="sxs-lookup"><span data-stu-id="ba999-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="ba999-114">Para obter detalhes sobre telefones de área comum, consulte a seção telefones de área comum de <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">escolher novos dispositivos</A>.</span><span class="sxs-lookup"><span data-stu-id="ba999-114">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ba999-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ba999-115">In This Section</span></span>

  - [<span data-ttu-id="ba999-116">Exibir informações de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba999-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="ba999-117">Criar ou modificar um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba999-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="ba999-118">Habilitar ou desabilitar o hot desk no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba999-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="ba999-119">Excluir um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba999-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="ba999-120">Atribuir políticas no Lync Server 2013 a um telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="ba999-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

